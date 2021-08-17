<template>
  <div class="cascadedropdown">
    <div v-if="node.children && node.children.length">
      <div v-for="(jpidx, jpindex) in jp" v-bind:key="jpindex">
        <select
          :style="cssProps"
          class="selectBox"
          v-model="selectedLabelByDepth[jpindex + 1]"
          v-on:change="handleDDClick($event, jpindex)"
          :depth="jpindex"
          :disabled="!enabledArray[jpindex]"
        >
          <option class="optionBox" value="">Select a value</option>
          <option
            class="optionBox"
            v-for="(child_obj, index) in selectedChildren[jpindex]"
            v-bind:key="index"
            :value="child_obj"
          >
            {{ child_obj }}
          </option>
        </select>
      </div>
    </div>
  </div>
</template>

<script>
import jsonpath from "jsonpath";

export default {
  name: "cascadedropdown",
  props: {
    node: Object,
    parent: Object,
    jp: Array,
    height: {
      type: Number,
      default: 30,
    },
    width: {
      type: Number,
      default: 200,
    },
    backgroundColor: {
      type: String,
      default: 'gray',
    },
    fontColor: {
      type: String,
      default: 'black',
    },
    borderRadius: {
      type: Number,
      default: 20,
    },
    border: {
      type: String,
      default: '0 0 0 2px rgba(#0077ff, 0.2)',
    },
    margin: {
      type: String,
      default: '10px',
    },
    hoverBackgroundColor:{
      type:String,
      default:'white'
    }
  },
  data() {
    return {
      selectedNode: Object,
      depth: Number(0),
      enabledArray: [],
      selectedChildren: {},
      selectedLabelByDepth: {},
    };
  },
  created() {
    this.methodJSONPLabels();
  },
  computed: {
    cssProps() {
      return {
        "--height": this.height + "px",
        "--width": this.width + "px",
        "--bg-color": this.backgroundColor,
        "--text-color": this.fontColor,
        "--border-radius": this.borderRadius + "px",
        "-border": this.border,
        "--margin": this.margin,
        "--hover-background-color": this.hoverBackgroundColor
      };
    },
  },
  mounted() {
    this.enabledArray.push(true);
    for (let i = 1; i < this.jp.length; i++) {
      this.enabledArray.push(false);
    }
  },
  methods: {
    methodJSONPLabels: function (index = 1) {
      let newJsonPath = this.jp[this.depth];
      if (!newJsonPath) {
        newJsonPath = "";
      }
      let step = Object.keys(this.selectedLabelByDepth).length;
      for (var i = 1; i <= step; i++) {
        newJsonPath = newJsonPath.replace(
          "SELECTED" + i,
          "'" + this.selectedLabelByDepth[i] + "'"
        );
      }
      let results = {};
      if (newJsonPath && !(newJsonPath === "")) {
        results = jsonpath.query(this.node, newJsonPath);
      }
      this.selectedChildren[this.depth] = results;
      for (var j = index + 1; j < this.jp.length; j++) {
        delete this.selectedChildren[j];
      }
      return results;
    },
    handleDDClick: function (event, index) {
      this.depth = index + 1;
      this.enabledArray[this.depth] = true;
      if (this.selectedNode && this.selectedNode.children) {
        for (let i = 0; i < this.selectedNode.children.length; i++) {
          this.selectedNode.children[i].enabled = true;
        }
      }
      this.selectedLabelByDepth[index + 1] = event.target.value;
      if (index + 1 != this.jp.length) {
        this.methodJSONPLabels(index + 1);
      }
      this.$emit("change-path", [event.target.value, this.depth]);
    },
  },
};
</script>
<style scoped>
.selectBox {
  border-radius: var(--border-radius);
  position: relative;
  height: var(--height);
  width: var(--width);
  margin: var(--margin);
  /* font-weight: bold !important; */
  text-transform: uppercase;
  background: var(--bg-color);
  color: var(--text-color);
}
.optionBox {
  color: var(--text-color);
}

.selectBox:focus {
  outline: none;
  border-color: #0077ff;
  box-shadow: 0 0 0 2px rgba(#0077ff, 0.2);
  background:var(--hover-background-color);
}
</style>