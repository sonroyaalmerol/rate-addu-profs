<template>
  <q-page>
    <q-card style="width: 100%" class="q-my-lg" flat>
      <div class="row">
        <q-card class="col-md-8 col-sm-12" flat>
          <q-card-section class="q-ma-sm">
            <div class="text-h4 q-my-lg">
              Test Professor 1
            </div>
            <div>
              Email: N/A
            </div>
            <div>
              Department: N/A
            </div>
            <q-separator class="q-my-lg" />
            <div class="row">
              <q-card flat class="rating bg-secondary text-white q-ma-xs">
                <q-card-section>
                  <div class="text-h4"><b>3.58</b></div>
                  <div class="text-subtitle1">Overall</div>
                </q-card-section>
              </q-card>

              <q-card flat class="sub-rating bg-secondary text-white q-ma-xs">
                <q-card-section>
                  <div class="text-h6">3.78</div>
                  <div class="text-subtitle3">Helpfulness</div>
                </q-card-section>
              </q-card>

              <q-card flat class="sub-rating bg-secondary text-white q-ma-xs">
                <q-card-section>
                  <div class="text-h6">3.78</div>
                  <div class="text-subtitle3">Pedagogy</div>
                </q-card-section>
              </q-card>

              <q-card flat class="sub-rating bg-secondary text-white q-ma-xs">
                <q-card-section>
                  <div class="text-h6">3.17</div>
                  <div class="text-subtitle3">Easiness</div>
                </q-card-section>
              </q-card>
            </div>
          </q-card-section>

          <q-card-actions align="right">
            <q-btn color="primary" size="md">Rate Professor</q-btn>
          </q-card-actions>
        </q-card>
        <q-card class="col-md-4 gt-sm" flat>
          <q-card-section>
            <div class="q-my-lg">
              <b>Other Professors teaching the same subjects</b>
            </div>
            <q-table
              :data="otherProfs"
              :columns="otherProfColumns"
              row-key="name"
              flat
            />
          </q-card-section>
        </q-card>
      </div>
      <q-table
        class="q-ma-lg"
        :data="data"
        :columns="columns"
        row-key="name"
        flat
        wrap-cells
      >
        <template v-slot:body-cell-rating="props">
          <q-td :props="props" style="width:250px">
            <div class="row">
              <div class="text-h6">Overall: {{ props.value.overall }}</div>
            </div>
            <div class="row">
              <div class="q-mr-xs">Easiness:</div>
              <q-rating
                v-model="props.value.easiness"
                size="1.5em"
                color="orange"
                readonly
              />
            </div>
            <div class="row">
              <div class="q-mr-xs">Helpfulness:</div>
              <q-rating
                v-model="props.value.helpfulness"
                size="1.5em"
                color="orange"
                readonly
              />
            </div>
            <div class="row">
              <div class="q-mr-xs">Pedagogy:</div>
              <q-rating
                v-model="props.value.pedagogy"
                size="1.5em"
                color="orange"
                readonly
              />
            </div>
          </q-td>
        </template>
      </q-table>
      <q-card class="lt-md" flat>
        <q-card-section>
          <div class="q-my-lg">
            <b>Other Professors teaching the same subjects</b>
          </div>
          <q-table
            :data="otherProfs"
            :columns="otherProfColumns"
            row-key="name"
            flat
          />
        </q-card-section>
      </q-card>
    </q-card>
  </q-page>
</template>

<script>
export default {
  name: 'PageIndex',
  data() {
    return {
      search: '',
      otherProfColumns: [
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
      otherProfs: [
        {
          name: 'Test Professor 1',
          rating: 4.59,
        },
        {
          name: 'Test Professor 2',
          rating: 4.21,
        },
      ],
      columns: [
        {
          name: 'date',
          required: true,
          label: 'Date',
          field: 'date',
          align: 'left',
          sortable: true,
        },
        {
          name: 'class',
          align: 'center',
          label: 'Class',
          field: 'class',
          sortable: true,
        },
        {
          name: 'rating',
          align: 'center',
          label: 'Rating',
          field: 'rating',
          sortable: true,
        },
        {
          name: 'comment',
          align: 'center',
          label: 'Comment',
          field: 'comment',
          sortable: true,
        },
      ],
      data: [
        {
          date: '2018',
          class: 'ASF 1000',
          rating: {
            overall: 4.56,
            easiness: 4,
            helpfulness: 5,
            pedagogy: 5,
          },
          comment: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Donec fermentum erat a eros ultrices facilisis. Nam quis nunc mollis, efficitur orci nec, feugiat tortor. Pellentesque eget justo a urna efficitur scelerisque. Nulla eu mi at elit efficitur auctor. Vestibulum in tristique nunc, et molestie justo. Nunc scelerisque pretium felis ac molestie. Duis nibh massa, sollicitudin eget purus sit amet, hendrerit mollis libero. Phasellus tempus nisl eget rutrum ultricies. Ut vel quam at tellus pellentesque mattis vitae id dui. Maecenas nec tempus magna. Quisque faucibus, dui at tincidunt consequat, magna mi sodales nunc, sed vulputate enim nisi et elit. Etiam mattis eu est sit amet placerat.',
        },
      ],
    };
  },
};
</script>

<style scoped>
  .rating {
    width: 100%;
    max-width: 120px;
    text-align: center;
  }
  .sub-rating {
    width: 100%;
    max-width: 100px;
    max-height: 80px;
    text-align: center;
  }
</style>
