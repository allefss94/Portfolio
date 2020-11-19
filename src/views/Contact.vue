<template>
  <div class="container">
    <TopNav />
    <div class="form">
      <h1>Contato</h1>
      <form
        name="contact"
        method="POST"
        netlify
        netlify-honeypot="bot-field"
        @submit.prevent="handleSubmit"
      >
        <input type="hidden" name="form-name" value="contact" />
        <input
          type="text"
          name="name"
          v-model="form.name"
          placeholder="Nome"
          required
        />
        <input
          type="email"
          name="email"
          v-model="form.email"
          placeholder="Email"
          required
        />
        <input
          type="text"
          name="phone"
          v-model="form.phone"
          placeholder="Telefone"
          required
        />
        <input
          type="textarea"
          name="message"
          v-model="form.message"
          placeholder="Sua Menssagem"
          required
        />
        <button type="submit">Enviar</button>
      </form>
    </div>
  </div>
</template>

<script>
const TopNav = () => import('@/components/TopNav');
export default {
  components: { TopNav },
  data() {
    return {
      form: {
        name: '',
        email: '',
        phone: '',
        message: '',
      },
    };
  },
  methods: {
    clearData() {
      this.name = '';
      this.email = '';
      this.phone = '';
      this.message = '';
    },
    encode(data) {
      return Object.keys(data)
        .map(
          key => `${encodeURIComponent(key)}=${encodeURIComponent(data[key])}`,
        )
        .join('&');
    },
    handleSubmit() {
      fetch('/', {
        method: 'POST',
        headers: { 'Content-Type': 'application/x-www-form-urlencoded' },
        body: this.encode({ 'form-name': 'contact', ...this.form }),
      })
        .then(() => {
          this.clearData();
          return this.$router.push('/thanks');
        })
        .catch(() => {
          this.clearData();
          return this.$router.push('/404');
        });
    },
  },
};
</script>

<style src="@/assets/scss/contact.scss" lang="scss" scoped />


