<template>
  <q-layout view="lHh Lpr lFf" class="fit row wrap justify-center items-start">
    <q-header class="row wrap justify-center items-start">
      <q-toolbar class="col-7">
        <q-toolbar-title class="col-2">
          Rate AdDU Profs
        </q-toolbar-title>
        <q-input class="q-ma-sm col-10" rounded dark standout
          v-model="search" placeholder="Search Professor/Class"
        >
          <template v-slot:append>
            <q-icon name="search" />
          </template>
        </q-input>
      </q-toolbar>
      <q-tabs
        v-model="tab"
        inline-label
        class="bg-primary text-white col-7"
      >
        <q-tab name="home"  label="Home" />
        <q-tab name="allProfessors"  label="All Professors" />
        <q-tab name="professorsNeedingReview" label="Professors Needing Review" />
        <q-tab name="addProfessor" label="Add Professor" />
        <q-tab name="contactDev" label="Contact Dev" />
      </q-tabs>
    </q-header>
    <q-page-container class="fit row wrap justify-center items-start ripple-background">
      <router-view class="col-7" />
      <div class="circle xxlarge shade1"></div>
      <div class="circle xlarge shade2"></div>
      <div class="circle large shade3"></div>
      <div class="circle mediun shade4"></div>
      <div class="circle small shade5"></div>
    </q-page-container>

  </q-layout>
</template>

<script>
export default {
  name: 'MyLayout',

  data() {
    return {
      tab: 'home',
      search: '',
    };
  },
};
</script>

<style scoped>
.circle{
  position: absolute;
  border-radius: 50%;
  background: #003a6c;
  animation: ripple 15s infinite;
  box-shadow: 0px 0px 1px 0px #508fb9;
  z-index: -1;
}

.small{
  width: 200px;
  height: 200px;
  left: -100px;
  top: 0px;
}

.medium{
  width: 400px;
  height: 400px;
  left: -200px;
  top: -100px;
}

.large{
  width: 600px;
  height: 600px;
  left: -300px;
  top: -200px;
}

.xlarge{
  width: 800px;
  height: 800px;
  left: -400px;
  top: -300px;
}

.xxlarge{
  width: 1000px;
  height: 1000px;
  left: -500px;
  top: -400px;
}

.shade1{
  opacity: 0.2;
}
.shade2{
  opacity: 0.5;
}

.shade3{
  opacity: 0.7;
}

.shade4{
  opacity: 0.8;
}

.shade5{
  opacity: 0.9;
}

@keyframes ripple{
  0%{
    transform: scale(0.8);
  }
  
  50%{
    transform: scale(1.2);
  }
  
  100%{
    transform: scale(0.8);
  }
}

</style>
