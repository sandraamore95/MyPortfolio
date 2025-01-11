<template>
  <div>
   
    <section id="about">
      <About />
    </section>
    <section id="skills">
      <Skills />
    </section>
    <section id="projects">
      <Projects />
    </section>
    <section id="contact">
      <Contact />
    </section>
  
  </div>
</template>

<script>
import About from './About.vue';
import Projects from './Projects.vue';
import Contact from './Contact.vue';
import Skills from './Skills.vue';

export default {
  components: { About,Skills, Projects, Contact },
};
</script>
