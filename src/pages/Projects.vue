<template>
  <section class="projects py-5">
    <div class="container">
      <h2 class="text-center mb-4">Portfolio</h2>
       <!-- Navegación de categorías -->
       <div class="text-center mb-4">
        <button
          class="btn btn-outline-secondary me-2"
          :class="{ active: selectedCategory === 'frontend' }"
          @click="selectedCategory = 'frontend'"
        >
          Frontend
        </button>
        <button
          class="btn btn-outline-secondary me-2"
          :class="{ active: selectedCategory === 'backend' }"
          @click="selectedCategory = 'backend'"
        >
          Backend
        </button>
        <button
          class="btn btn-outline-secondary"
          :class="{ active: selectedCategory === 'all' }"
          @click="selectedCategory = 'all'"
        >
          All
        </button>
      </div>
      <!-- Grid de proyectos -->
      <div class="row g-4">
        <div
          class="col-xl-4 col-lg-4 col-md-6 col-sm-12"
          v-for="(project, index) in filteredProjects"
          :key="index"
        >
          <ProjectCard :project="project" />
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import data from "../data/data.json";
import ProjectCard from "../components/ProjectCard.vue";
export default {
  components: { ProjectCard },
  data() {
    return {
      projects: data.projects,
      selectedCategory: "all" // default
    };
  },
  computed: {
    filteredProjects() {
      if (this.selectedCategory === "all") {
        return this.projects;
      }
      return this.projects.filter(
        (project) => project.category === this.selectedCategory
      );
    }
  }
};
</script>

<style scoped>
.projects {
  background-color: #f9f9f9;
}

.projects .container {
  max-width: 1140px;
}

.projects h2 {
  font-weight: bold;
  color: var(--bs-dark);
}

.projects p {
  color: #6c757d;
}

button.active {
  background-color: #28c986;
  color: white;
}
</style>