<template>
  <section class="skills py-5">
    <div class="container">
      <h2 class="text-center mb-4">Skills</h2>
      <div class="row g-4">
        <div class="col-12 col-sm-6 col-md-4 " v-for="(skill, index) in skills" :key="index">
          <SkillCard :skill="skill" />
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.skills {
  background-color: #f9f9f9;
}

.skills .container {
  max-width: 1140px;
}

.skills h2 {
  font-weight: bold;
  color: var(--bs-dark);
}

.skills p {
  color: #6c757d;
}
</style>

<script>
import SkillCard from '../components/SkillCard.vue';
import data from '../data/data.json';

export default {
  components: { SkillCard },
  data() {
    return {
      skills: data.skills
    };
  },
  methods: {
    goToDetails(id) {
      this.$router.push(`/skills/${id}`);
    },
  },
};
</script>