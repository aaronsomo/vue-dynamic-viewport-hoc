<template>
  <v-data-table
    :height="tableProps.tableHeight"
    :headers="tableHeaders"
    :items="tableItems"
    :items-per-page="20"
    :footer-props="{ itemsPerPageOptions: [20, 30, 50] }"
  >
  </v-data-table>
</template>

<script>
export default {
  name: "DataTable",
  // props: ["tableProps"],
  props: {
    tableProps: { type: Object },
  },
  data() {
    return {
      tableHeaders: [
        { text: "Name", value: "name" },
        { text: "Value", value: "val" },
      ],
      tableItems: [],
      // tableHeight: 300,
    };
  },
  mounted() {
    for (let i = 0; i < 50; i++) {
      let obj = {};
      obj.name = "Item " + (i + 1);
      obj.val = (i + 1) * 10;
      this.tableItems.push(obj);
    }
  },
  // computed: {
  //   calcHeight() {
  //     return {
  //       height: this.tableHeight
  //     }
  //   }
  // }
};
</script>