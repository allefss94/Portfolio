<template>
  <div class="container">
    <div class="home">
      <Logo />
      <a href="#info">saiba mais</a>
    </div>
    <div class="about">
      <div class="info" id="info">
        <h1>Sobre mim</h1>
        <p>
          Olá, me chamo Allef Sousa. Sou estudante de Sistemas de Informação
          pela Universidade Federal de Alagoas e desenvolvedor com ênfase em
          tecnologias Front-End.
        </p>
        <div class="buttons">
          <router-link tag="button" to="/projects">projetos</router-link>
          <router-link tag="button" to="/projects">contato</router-link>
        </div>
      </div>
      <img src="@/assets/images/notebook.webp" alt="laptop" />
    </div>
  </div>
</template>

<script>
const Logo = () => import('@/components/Logo');

export default {
  name: 'Home',
  components: { Logo },
};
</script>
<style src="@/assets/scss/home.scss" lang="scss" scoped />
