<template>
  <section class="about py-5 text-center">
    <div class="container">
      <div class="row align-items-center">
        <div class="col-md-4 mb-4 mb-md-0">
          <img :src="info.avatar" :alt="info.name" class="img-fluid rounded-circle shadow">
        </div>
        <div class="col-md-8">
          <h1 class="display-4 mb-4">Bienvenidos a mi Portfolio!</h1>
          <p class="lead mb-4">
            {{ info.description }}
          </p>
          <div class="mt-3">
            <a :href="info.url_git" target="_blank" class="me-3">
              <i class="fab fa-github fa-2x"></i>
            </a>
            <a :href="info.url_linkedin" target="_blank">
              <i class="fab fa-linkedin fa-2x"></i>
            </a>
          </div>

        </div>
      </div>
    </div>
  </section>
</template>
<script>
import data from '../data/data.json'

export default {
  name: 'About',
  data() {
    return {
      info: data.info
    };
  },
  methods: {
    goToDetails(id) {
      this.$router.push(`/projects/${id}`);
    },
  },
};



</script>

<style scoped>
.about {
  padding: 20px;
  margin: 0 auto;
  background-color: rgb(224, 224, 224);
 
  margin: 0 auto;
}

h1,
h2 {
  color: #42b983;
}

ul {
  padding-left: 20px;
}

ul li {
  margin-bottom: 8px;
}

p {
  line-height: 1.6;
}
.shadow{
  background-color: rgb(108, 255, 165);

}
</style>