<template>
  <q-page>
    <q-card style="width: 100%" flat>
      <q-card-section class="q-ma-lg">
        <div class="text-h3 q-my-lg">
          List of Professors
        </div>
        <q-table
          :data="data"
          :columns="columns"
          row-key="name"
          flat
        />
      </q-card-section>
    </q-card>
  </q-page>
</template>

<script>
export default {
  name: 'PageIndex',
  data() {
    return {
      search: '',
      columns: [
        {
          name: 'name',
          required: true,
          label: 'Name',
          field: 'name',
          align: 'left',
          sortable: true,
        },
        {
          name: 'rating',
          align: 'center',
          label: 'Rating',
          field: 'rating',
          sortable: true,
        },
      ],
      data: [
        {
          name: 'Test Professor 1',
          rating: 4.59,
        },
        {
          name: 'Test Professor 2',
          rating: 4.21,
        },
      ],
    };
  },
};
</script>
