<template>
    <div>
        <KTCodePreview v-bind:title="'Release Order Pembelian'">
            <template v-slot:preview>
                <div>
                <b-table striped hover :items="items"></b-table>
                </div>
            </template>
        </KTCodePreview>
    </div>
</template>

<script>
import KTCodePreview from "@/view/content/CodePreview.vue";
import { SET_BREADCRUMB } from "@/core/services/store/breadcrumbs.module";

export default {
  data() {
    return{
        items: [
          { age: 40, first_name: "Dickerson", last_name: "Macdonald" },
          { age: 21, first_name: "Larsen", last_name: "Shaw" },
          { age: 89, first_name: "Geneva", last_name: "Wilson" },
          { age: 38, first_name: "Jami", last_name: "Carney" }
        ]
    }
  },
  components: {
    KTCodePreview
  },
  mounted() {
    this.$store.dispatch(SET_BREADCRUMB, [
      { title: "Purchase", route: "employee" },
      { title: "Release Order Pembelian" }
    ]);
  },
  created () {
    document.title = 'EBS | Release Order Pembelian';
  },
};
</script>