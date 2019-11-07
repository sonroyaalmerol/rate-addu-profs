<template>
  <q-page>
    <q-card style="width: 100%" flat>
      <q-card-section class="q-ma-lg">
        <div class="text-h3 q-my-lg">
          Add Professor
        </div>
        <q-banner rounded class="bg-orange text-white">
          Search and make sure the professor is not yet in our database!
        </q-banner>
        <q-form
          @submit="recaptcha"
          class="q-gutter-md q-my-lg"
        >
          <q-input
            outlined
            v-model="form.firstName"
            label="First Name"
            lazy-rules
            :rules="[ val => val && val.length > 0 || 'First name is required']"
          />
          <q-input
            outlined
            v-model="form.lastName"
            label="Last Name"
            lazy-rules
            :rules="[ val => val && val.length > 0 || 'Last name is required']"
          />
          <q-input
            outlined
            v-model="form.email"
            label="Professor Email"
            hint="Optional"
          />
          <q-input
            outlined
            v-model="form.department"
            label="Department"
            hint="Optional"
          />

          <q-toggle
            v-model="accept"
            label="I am sure that this professor is not yet in the database."
          />

          <div>
            <q-btn label="Submit" type="submit" color="primary"/>
          </div>

        </q-form>
      </q-card-section>
    </q-card>
  </q-page>
</template>

<script>
export default {
  name: 'PageIndex',
  data() {
    return {
      form: {
        firstName: '',
        lastName: '',
        email: '',
        department: '',
      },
      accept: false,
      token: '',
    };
  },
  methods: {
    recaptcha() {
      this.$recaptcha('login').then((token) => {
        this.token = token // Will print the token
      })
    },
  },
};
</script>
