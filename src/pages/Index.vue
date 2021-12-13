<template>
  <q-page class="">
    <q-table title="Notas" :rows="rows" :columns="columns" row-key="name">
      <template v-slot:body-cell-actions="props">
        <q-td :props="props" class="q-gutter-x-sm">
          <q-btn icon="edit" color="primary" dense />
          <q-btn icon="delete" color="negative" dense />
        </q-td>
      </template>
    </q-table>
    <q-page-sticky position="bottom-right" :offset="[18, 18]">
      <q-btn fab icon="add" color="primary" @click="goToForm" />
    </q-page-sticky>
  </q-page>
</template>
<script>
import { useRouter } from "vue-router";
export default {
  setup() {
    const router = useRouter();

    const columns = [
      {
        name: "name",
        field: "title",
        required: true,
        label: "Titulo",
        align: "left",
        sortable: true,
      },
      {
        name: "actions",
        field: "actions",
        align: "right",
      },
    ];

    const rows = [
      {
        title: "Nota 1",
      },
      {
        title: "Nota 2",
      },
      {
        title: "Nota 3",
      },
      {
        title: "Nota 4",
      },
      {
        title: "Nota 5",
      },
      {
        title: "Nota 6",
      },
      {
        title: "Nota 7",
      },
      {
        title: "Nota 8",
      },
    ];

    const goToForm = () => {
      router.push('/form')
    };

    return {
      columns,
      rows,
      goToForm,
    };
  },
};
</script>

<!--<script>
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'PageIndex'
})
</script>-->
