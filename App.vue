<template>
  <div>
    <NonTreeCascade
      :tree-data="tree"
      :keyValues="valuesArray"
      :height="35"
      :width="200"
      :backgroundColor="backgroundColor"
      :border="border"
      :borderRadius="borderRadius"
      :fontColor="fontColor"
      :margin="margin"
    ></NonTreeCascade>
  </div>
</template>

<script>
import NonTreeCascade from "./components/NonTreeCascade";

export default {
  label: "App",
  props: {
    treeData: Object,
  },
  components: {
    NonTreeCascade,
  },
  data: function () {
    return {
      valuesArray: ["continentName", "label", "label", "label"],
      backgroundColor: "white",
      border: "0 0 0 10px rgba(#0077ff, 0.2)",
      fontColor: "black",
      borderRadius: 13,
      margin:"5px",
      hoverBackgroundColor:"#fefae0",
      tree: {
        itemType: "Planet",
        label: "Earth",
        childrenType: "Continent",
        enabled: true,
        children: [
          {
            itemType: "Continent",
            continentName: "Asia",
            childrenType: "Country",
            enabled: false,
            children: [
              {
                itemType: "Country",
                label: "India",
                childrenType: "City",
                enabled: false,
                children: [
                  {
                    itemType: "City",
                    label: "New Delhi",
                    enabled: false,
                    children: [
                      {
                        itemType: "Area",
                        label: "Patel Nagar",
                        enabled: false,
                        children: [],
                      },
                      {
                        itemType: "Area",
                        label: "Shivaji Place",
                        enabled: false,
                        children: [],
                      },
                    ],
                  },
                  {
                    itemType: "City",
                    label: "Mumbai",
                    enabled: false,
                    children: [
                      {
                        itemType: "Area",
                        label: "Andheri",
                        enabled: false,
                        children: [],
                      },
                      {
                        itemType: "Area",
                        label: "Bandra",
                        enabled: false,
                        children: [],
                      },
                    ],
                  },
                  {
                    itemType: "City",
                    label: "Bangalore",
                    enabled: false,
                    children: [
                      {
                        itemType: "Area",
                        label: "Marathahalli",
                        enabled: false,
                        children: [],
                      },
                      {
                        itemType: "Area",
                        label: "Indiranagar",
                        enabled: false,
                        children: [],
                      },
                    ],
                  },
                  {
                    itemType: "City",
                    label: "Chennai",
                    enabled: false,
                    children: [
                      {
                        itemType: "Area",
                        label: "Teynampet",
                        enabled: false,
                        children: [],
                      },
                      {
                        itemType: "Area",
                        label: "Adyar",
                        enabled: false,
                        children: [],
                      },
                    ],
                  },
                ],
              },
              {
                itemType: "Country",
                label: "China",
                childrenType: "City",
                children: [
                  {
                    itemType: "City",
                    label: "Beijing",
                    enabled: false,
                    children: [
                      {
                        itemType: "Area",
                        label: "Chaoyang Park",
                        enabled: false,
                        children: [],
                      },
                      {
                        itemType: "Area",
                        label: "Hutong Area",
                        enabled: false,
                        children: [],
                      },
                    ],
                  },
                  {
                    itemType: "City",
                    label: "Shanghai",
                    enabled: false,
                    children: [
                      {
                        itemType: "Area",
                        label: "Gubei",
                        enabled: false,
                        children: [],
                      },
                      {
                        itemType: "Area",
                        label: "Lujiazui",
                        enabled: false,
                        children: [],
                      },
                    ],
                  },
                  {
                    itemType: "City",
                    label: "Guangzhou",
                    enabled: false,
                    children: [
                      {
                        itemType: "Area",
                        label: "Yuexiu",
                        enabled: false,
                        children: [],
                      },
                      {
                        itemType: "Area",
                        label: "Xiguan",
                        enabled: false,
                        children: [],
                      },
                    ],
                  },
                  {
                    itemType: "City",
                    label: "Tianjin",
                    enabled: false,
                    children: [
                      {
                        itemType: "Area",
                        label: "Baodi",
                        enabled: false,
                        children: [],
                      },
                      {
                        itemType: "Area",
                        label: "Wuqing",
                        enabled: false,
                        children: [],
                      },
                    ],
                  },
                ],
              },
              {
                itemType: "Country",
                label: "Japan",
                childrenType: "City",
                enabled: false,
                children: [
                  {
                    itemType: "City",
                    label: "Tokyo",
                    enabled: false,
                    children: [
                      {
                        itemType: "Area",
                        label: "Akihabara",
                        enabled: false,
                        children: [],
                      },
                      {
                        itemType: "Area",
                        label: "Asakusa",
                        enabled: false,
                        children: [],
                      },
                    ],
                  },
                  {
                    itemType: "City",
                    label: "Kyoto",
                    enabled: false,
                    children: [
                      {
                        itemType: "Area",
                        label: "Nishijin",
                        enabled: false,
                        children: [],
                      },
                      {
                        itemType: "Area",
                        label: "Arashiyama",
                        enabled: false,
                        children: [],
                      },
                    ],
                  },
                  {
                    itemType: "City",
                    label: "Nagoya",
                    enabled: false,
                    children: [
                      {
                        itemType: "Area",
                        label: "Naka-ku",
                        enabled: false,
                        children: [],
                      },
                      {
                        itemType: "Area",
                        label: "Atsuta-ku",
                        enabled: false,
                        children: [],
                      },
                    ],
                  },
                  {
                    itemType: "City",
                    label: "Hiroshima",
                    enabled: false,
                    children: [
                      {
                        itemType: "Area",
                        label: "Fudoin",
                        enabled: false,
                        children: [],
                      },
                      {
                        itemType: "Area",
                        label: "Shukkei-en",
                        enabled: false,
                        children: [],
                      },
                    ],
                  },
                ],
              },
              {
                itemType: "Country",
                label: "Malaysia",
                childrenType: "City",
                enabled: false,
                children: [
                  {
                    itemType: "City",
                    label: "Kuala Lumpur",
                    enabled: false,
                    children: [
                      {
                        itemType: "Area",
                        label: "Chinatown",
                        enabled: false,
                        children: [],
                      },
                      {
                        itemType: "Area",
                        label: "Petaling Jaya",
                        enabled: false,
                        children: [],
                      },
                    ],
                  },
                  {
                    itemType: "City",
                    label: "Johor Bahru",
                    enabled: false,
                    children: [
                      {
                        itemType: "Area",
                        label: "Kempas",
                        enabled: false,
                        children: [],
                      },
                      {
                        itemType: "Area",
                        label: "Larkin",
                        enabled: false,
                        children: [],
                      },
                    ],
                  },
                  {
                    itemType: "City",
                    label: "George Town",
                    enabled: false,
                    children: [],
                  },
                  {
                    itemType: "City",
                    label: "Kota Kinabalu",
                    enabled: false,
                    children: [],
                  },
                ],
              },
              {
                itemType: "Country",
                label: "Singapore",
                childrenType: "City",
                enabled: false,
                children: [
                  {
                    itemType: "City",
                    label: "Singapore City",
                    enabled: false,
                    children: [],
                  },
                ],
              },
            ],
          },
          {
            itemType: "Continent",
            continentName: "Europe",
            childrenType: "Country",
            enabled: false,
            children: [
              {
                itemType: "Country",
                label: "Germany",
                childrenType: "City",
                enabled: false,
                children: [
                  {
                    itemType: "City",
                    label: "Berlin",
                    enabled: false,
                    children: [
                      {
                        itemType: "Area",
                        label: "Lichtenberg",
                        enabled: false,
                        children: [],
                      },
                      {
                        itemType: "Area",
                        label: "Mitte",
                        enabled: false,
                        children: [],
                      },
                    ],
                  },
                  {
                    itemType: "City",
                    label: "Hamburg",
                    enabled: false,
                    children: [
                      {
                        itemType: "Area",
                        label: "HafenCity",
                        enabled: false,
                        children: [],
                      },
                      {
                        itemType: "Area",
                        label: "Ottensen",
                        enabled: false,
                        children: [],
                      },
                    ],
                  },
                  {
                    itemType: "City",
                    label: "Munich",
                    enabled: false,
                    children: [
                      {
                        itemType: "Area",
                        label: "Marienplatz",
                        enabled: false,
                        children: [],
                      },
                      {
                        itemType: "Area",
                        label: "Altstadt",
                        enabled: false,
                        children: [],
                      },
                    ],
                  },
                  {
                    itemType: "City",
                    label: "Cologne",
                    enabled: false,
                    children: [
                      {
                        itemType: "Area",
                        label: "Lindenthal",
                        enabled: false,
                        children: [],
                      },
                      {
                        itemType: "Area",
                        label: "Rodenkirchen",
                        enabled: false,
                        children: [],
                      },
                    ],
                  },
                  {
                    itemType: "City",
                    label: "Stuttgart",
                    enabled: false,
                    children: [
                      {
                        itemType: "Area",
                        label: "Ludwigsburg",
                        enabled: false,
                        children: [],
                      },
                      {
                        itemType: "Area",
                        label: "Esslingen",
                        enabled: false,
                        children: [],
                      },
                    ],
                  },
                  {
                    itemType: "City",
                    label: "Frankfurt",
                    enabled: false,
                    children: [
                      {
                        itemType: "Area",
                        label: "Ostend",
                        enabled: false,
                        children: [],
                      },
                      {
                        itemType: "Area",
                        label: "Bornheim",
                        enabled: false,
                        children: [],
                      },
                    ],
                  },
                ],
              },
              {
                itemType: "Country",
                label: "UK",
                childrenType: "City",
                enabled: false,
                children: [
                  {
                    itemType: "City",
                    label: "London",
                    enabled: false,
                    children: [
                      {
                        itemType: "Area",
                        label: "Bloomsbury",
                        enabled: false,
                        children: [],
                      },
                      {
                        itemType: "Area",
                        label: "Piccadilly",
                        enabled: false,
                        children: [],
                      },
                    ],
                  },
                  {
                    itemType: "City",
                    label: "Birmingham",
                    enabled: false,
                    children: [
                      {
                        itemType: "Area",
                        label: "Harborne",
                        enabled: false,
                        children: [],
                      },
                      {
                        itemType: "Area",
                        label: "Edgbaston",
                        enabled: false,
                        children: [],
                      },
                    ],
                  },
                  {
                    itemType: "City",
                    label: "Liverpool",
                    enabled: false,
                    children: [
                      {
                        itemType: "Area",
                        label: "Vauxhall",
                        enabled: false,
                        children: [],
                      },
                      {
                        itemType: "Area",
                        label: "Walton",
                        enabled: false,
                        children: [],
                      },
                    ],
                  },
                  {
                    itemType: "City",
                    label: "Bristol",
                    enabled: false,
                    children: [
                      {
                        itemType: "Area",
                        label: "Harbourside",
                        enabled: false,
                        children: [],
                      },
                      {
                        itemType: "Area",
                        label: "Hotwells",
                        enabled: false,
                        children: [],
                      },
                    ],
                  },
                ],
              },
              {
                itemType: "Country",
                label: "France",
                childrenType: "City",
                enabled: false,
                children: [
                  {
                    itemType: "City",
                    label: "Paris",
                    enabled: false,
                    children: [
                      {
                        itemType: "Area",
                        label: "Latin Quarter",
                        enabled: false,
                        children: [],
                      },
                      {
                        itemType: "Area",
                        label: "Montmartre",
                        enabled: false,
                        children: [],
                      },
                    ],
                  },
                  {
                    itemType: "City",
                    label: "Marseille",
                    enabled: false,
                    children: [
                      {
                        itemType: "Area",
                        label: "Vieux Port",
                        enabled: false,
                        children: [],
                      },
                      {
                        itemType: "Area",
                        label: "Euromed",
                        enabled: false,
                        children: [],
                      },
                    ],
                  },
                  {
                    itemType: "City",
                    label: "Bordeaux",
                    enabled: false,
                    children: [
                      {
                        itemType: "Area",
                        label: "La Bastide",
                        enabled: false,
                        children: [],
                      },
                      {
                        itemType: "Area",
                        label: "Grands Hommes",
                        enabled: false,
                        children: [],
                      },
                    ],
                  },
                  {
                    itemType: "City",
                    label: "Toulouse",
                    enabled: false,
                    children: [
                      {
                        itemType: "Area",
                        label: "Basilique",
                        enabled: false,
                        children: [],
                      },
                      {
                        itemType: "Area",
                        label: "Bemberg",
                        enabled: false,
                        children: [],
                      },
                    ],
                  },
                ],
              },
            ],
          },
        ],
      },
    };
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
