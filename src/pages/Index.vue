<template>
  <q-page>
    <q-card style="width: 100%" flat>
      <q-card-section class="q-ma-lg">
        <div class="text-h3">
          Hello Students!
        </div>
        <div class="text-subtitle2">
          Welcome to Rate AdDU Profs, a comprehensive database for knowing your professors
        </div>
        <q-input class="q-my-lg col-12" rounded standout
          v-model="search" placeholder="Search Professor/Class in Ateneo de Davao University"
        >
          <template v-slot:append>
            <q-icon name="search" />
          </template>
        </q-input>
      </q-card-section>
    </q-card>
    <q-card class="row" flat>
      <div class="col-4">
        <q-card-section>
          <div class="text-h6">Completely Secure</div>
          <q-separator />
        </q-card-section>
        <q-card-section>
          We are not going to collect or share your IP address or
          email to anyone. All reviews are anonymous so do not fear
          of them knowing who you are!
        </q-card-section>
      </div>
      <div class="col-4">
        <q-card-section>
          <div class="text-h6">By AdDU Students, for AdDU Students</div>
          <q-separator />
        </q-card-section>
        <q-card-section>
          Rate AdDU Profs is created by a student of AdDU as a service
          to find the best professors in the university. The purpose of
          this application is for the students to have a better learning
          experience and give constructive criticisms to their professors.
        </q-card-section>
      </div>
      <div class="col-4">
        <q-card-section>
          <div class="text-h6">More Features!</div>
          <q-separator />
        </q-card-section>
        <q-card-section>
          Rate AdDU Profs is continuously improving and gaining new features.
          Any ideas are greatly appreciated. Feel free to request more
          features through my email on the Contact Dev tab.
        </q-card-section>
      </div>
    </q-card>
  </q-page>
</template>

<script>
export default {
  name: 'PageIndex',
  data() {
    return {
      search: '',
    };
  },
};
</script>
