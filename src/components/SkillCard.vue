<template>
  <div class="card h-100">
    <div class="card-body text-center">
      <i :class="[skill.icon, 'fa-3x mb-3']"></i>
      <h5 class="card-title">{{ skill.title }}</h5>
      <ul class="list-group list-group-flush">
        <li v-for="item in skill.info" :key="item" class="list-group-item">
          <i :class="[getIconForSkill(item), 'me-2']"></i>{{ item }}
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    skill: {
      type: Object,
      required: true
    }
  },
  methods: {
    getIconForSkill(skillName) {
      const iconMap = {
        'Python': 'fab fa-python',
        'JavaScript': 'fab fa-js-square',
        'TypeScript': 'fas fa-code',
        'Java': 'fab fa-java',
        'Angular': 'fab fa-angular',
        'React': 'fab fa-react',
        'Vue': 'fab fa-vuejs',
        'Bootstrap': 'fab fa-bootstrap',
        'SpringBoot': 'fas fa-leaf',
        'Express': 'fab fa-node-js',
        'FastAPI': 'fas fa-bolt'
        // Añade más mapeos según sea necesario
      };
      return iconMap[skillName] || 'fas fa-code'; // Icono por defecto
    }
  }
}

</script>

<style scoped>
  .card{
   border: none;
  }
</style>