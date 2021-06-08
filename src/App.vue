<template>
  <v-app>
    <v-main>
      <ResizablePage>
        <template v-slot:header>
          <h1 class="text-center">Header</h1>
        </template>
        <template v-slot:toolbar>
          <h3 class="text-center">Toolbar</h3>
        </template>
        <template v-slot:filter>
          <p>Filter</p>
        </template>
        <!-- <template v-slot:table="tableProps">
          <v-data-table
            :height="tableProps.tableHeight"
            :headers="tableHeaders"
            :items="tableItems"
            :items-per-page="20"
            :footer-props="{ itemsPerPageOptions: [20, 30, 50] }"
          >
          </v-data-table>
        </template> -->
        <template v-slot:table="tableProps">
          <DataTable v-bind:tableProps="tableProps" />
        </template>
      </ResizablePage>
    </v-main>
  </v-app>
</template>

<script>
import ResizablePage from "./components/resizable-page";
import DataTable from "./components/data-table";

export default {
  name: "App",
  components: {
    ResizablePage,
    DataTable,
  },
  computed: {
    parentProps() {
      return {};
    },
  },
  // data() {
  //   return {
  //     tableHeaders: [
  //       { text: "Name", value: "name" },
  //       { text: "Value", value: "val" },
  //     ],
  //     tableItems: [],
  //   };
  // },
  // mounted() {
  //   for (let i = 0; i < 50; i++) {
  //     let obj = {};
  //     obj.name = "Item " + (i + 1);
  //     obj.val = (i + 1) * 10;
  //     this.tableItems.push(obj);
  //   }
  // },
};
</script>

