<template>
  <div class="projects">
    <TopNav id="top" />
    <div class="projects">
      <h1>Projects</h1>
      <div class="cards">
        <div class="card first">
          <div class="info">
            <h3>Spending Bill´s Money</h3>
            <p>
              O Spending Bill´s Money é um projeto criado para atender um teste
              para vaga de desenvolvedor Front-end Junior, e consiste na criação
              de uma aplicação web seguindo os padrões da web moderna.
            </p>
          </div>
          <img src="@/assets/images/spend.webp" alt="Spend Bills Money" />
        </div>

        <div class="card-2 second">
          <img src="@/assets/images/super-task.webp" alt="Super Tasks" />
          <div class="info">
            <h3>Super Tasks</h3>
            <p>
              Super Tasks é um gerenciador de tarefas super intuitivo. O projeto
              foi desenvolvido com o intuito de praticar e adquirir novos
              conhecimentos tanto no Front-end como na criação de APIs.
            </p>
          </div>
        </div>

        <div class="card third">
          <div class="info">
            <h3>Title</h3>
            <p>
              Lorem ipsum dolor sit amet consectetur adipisicing elit. Cum
              aliquam tempora in dolorem quasi ipsum harum, odio eius voluptate
              molestias modi saepe illo natus enim neque perspiciatis iste iure
              quas?
            </p>
          </div>
          <img src="@/assets/images/spend.webp" alt="Spend Bills Money" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { gsap } from 'gsap/dist/gsap';
const TopNav = () => import('@/components/TopNav');
export default {
  components: { TopNav },
  beforeMount() {
    document.body.scrollTop = document.documentElement.scrollTop = 0;
  },
  mounted() {
    const tl = gsap.timeline();
    tl.from('.first', { x: -200, duration: 0.7, opacity: 0, ease: 'power2' });
    tl.from('.second', { x: 200, duration: 0.7, opacity: 0, ease: 'power2' });
    tl.from('.third', { x: -200, duration: 0.7, opacity: 0, ease: 'power2' });
  },
};
</script>

<style src="@/assets/scss/projects.scss" lang="scss" scoped />
