<template>
  <div class="main-wrapper">
    <MyHeader appName="Course Catalog" />
    <AllCourses :courses=courses />
  </div>
</template>

<script>
import MyHeader from './components/MyHeader.vue'
import AllCourses from './components/AllCourses.vue'


export default {
  name: 'App',

  components: {
    MyHeader,
    AllCourses
  },
  data() {
    return {
      courses: []
    }
  },
  methods: {
    async fetchAllCourses() {
      const res = await fetch('https://courses-catalog-node.onrender.com/api');
      const data = await res.json()
      console.log(data.courses)
      return data.courses
    }
  },
  async created() {
    this.courses = await this.fetchAllCourses();
  }
}
</script>


<style>
@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@300&display=swap');

* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: 'Montserrat', sans-serif;
}


.main-wrapper {
  color: black;
  padding: 0 1em;
}

@media screen and (max-width: 476px) {
  .main-container {
    width: 100%;
  }
}
</style>
