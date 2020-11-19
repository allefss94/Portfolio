<template>
  <div class="container">
    <h1>Opsss, ocorreu um erro, tente novamente! 😭</h1>
    <router-link tag="button" to="/contact">Voltar</router-link>
  </div>
</template>

<script>
export default {
  name: 'Error 404',
};
</script>

<style lang="scss" scoped>
.container {
  height: 100vh;
  width: 100vw;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  color: #eee;
  text-align: center;

  h1 {
    font-size: 3rem;
    width: 80%;
  }
  button {
    padding: 0.6rem 2rem;
    margin: 1.2rem 0;
    border: none;
    outline: none;

    font-size: 1.4rem;
    font-weight: bolder;
    color: #39376b;

    cursor: pointer;
    transition: all 0.4s;

    &:hover {
      box-shadow: 0 0 10px 5px #2a295c;
      background: #39376b;
      color: #eee;
    }
  }
}
</style>
