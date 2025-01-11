<template>
  <div class="card shadow-sm hover-effect project-card">
    <img v-if="project.image" :src="project.image" class="card-img-top" :alt="`Imagen del proyecto ${project.title}`" />
    <div class="card-body">
      <div class="d-flex justify-content-between align-items-center mb-2">
        <h3 class="card-title h5 mb-0">{{ project.title }}</h3>
        <span class="badge" :class="project.category === 'backend' ? 'bg-success' : 'bg-primary'">
          {{ project.category }}
        </span>
      </div>

      <!-- Tecnologías usadas -->
      <div class="mt-3">
        <span v-for="tec in project.technologies" :key="tec" class="badge bg-secondary me-2 mb-2">
          {{ tec }}
        </span>
      </div>
      <p class="card-text">{{ project.description }}</p>
      <div class="mt-auto pt-3">
        <a :href="project.url_git" target="_blank" class="btn btn-outline-dark w-100">
          <i class="fab fa-github me-2"></i>Ver en GitHub
        </a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    project: {
      type: Object,
      required: true,
    },
  },
};
</script>

<style scoped>
.project-card {
  border-radius: 10px;
  overflow: hidden;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}
.bg-success{
  background-color:rgb(50, 142, 196) !important;
}
.bg-primary{
    background-color:rgb(34, 194, 114) !important;
}

.project-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
}

.card-img-top {
  object-fit: cover;
  height: 180px;
}

.badge {
  font-size: 0.85rem;
}

.card-body {
  padding: 1.25rem;
}

.hover-effect {
  cursor: pointer;
}
</style>
