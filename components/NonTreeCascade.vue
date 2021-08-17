<template>
  <div class="nontree-cascade">
    <cascadedropdown
      :height="height"
      :width="width"
      :backgroundColor="backgroundColor"
      :hoverBackgroundColor="hoverBackgroundColor"
      :fontColor="fontColor"
      :borderRadius="borderRadius"
      :margin="margin"
      :border="border"
      :node="treeData"
      :depth="0"
      v-bind:path="{}"
      v-on:change-path="handleNewPath"
      v-bind:jp="jp"
    ></cascadedropdown>
    Selected path: {{ path }}
  </div>
</template>

<script>
import cascadedropdown from "./CascadeDD.vue";

export default {
  name: "NonTreeCascade",
  props: {
    treeData: Object,
    keyValues: Array,
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
      default: 10,
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
  components: {
    cascadedropdown,
  },
  data() {
    return {
      path: {},
      jp: [],
    };
  },
  created() {
    let finalArray = [];
    for (let i = 0; i < this.keyValues.length; i++) {
      let stringAppend = ".children[*].label";
      if (i == 0) {
        finalArray.push("$" + stringAppend.replace("label", this.keyValues[i]));
      } else {
        let jString = "";
        let dummyString = ".children[?(@.label==SELECTED)]";
        for (let j = 1; j <= i; j++) {
          jString += dummyString
            .replace("label", this.keyValues[j - 1])
            .replace("SELECTED", "SELECTED" + j);
        }
        jString += stringAppend;
        finalArray.push("$" + jString);
      }
    }
    console.log(finalArray)
    this.jp = finalArray;
  },

  methods: {
    handleNewPath: function (eventData) {
      let selectedLabel = eventData[0];
      let depth = eventData[1];
      this.path[depth] = selectedLabel;
      Object.keys(this.path).sort((a, b) => {
        return a - b;
      });

      for (let j = Object.keys(this.path).length; j >= depth + 1; j--) {
        if (this.path[j]) {
          delete this.path[j];
        }
      }
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.tree-list ul {
  padding-left: 16px;
  margin: 6px 0;
}
</style>
