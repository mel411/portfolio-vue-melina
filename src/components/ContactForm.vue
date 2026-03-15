<template>
  <form class="contact-form" @submit.prevent="submitForm">
    <div class="form-group">
      <label>Nom</label>
      <input type="text" v-model="name" required />
    </div>

    <div class="form-group">
      <label>Email</label>
      <input type="email" v-model="email" required />
    </div>

    <div class="form-group">
      <label>Message</label>
      <textarea v-model="message" required></textarea>
    </div>

    <button type="submit">Envoyer</button>

    <p v-if="sent" class="success">Message envoyé avec succès !</p>
  </form>
</template>

<script>
export default {
  name: 'ContactForm',

  data() {
    return {
      name: '',
      email: '',
      message: '',
      sent: false,
    }
  },

  methods: {
    submitForm() {
      console.log('Nom:', this.name)
      console.log('Email:', this.email)
      console.log('Message:', this.message)

      this.sent = true

      this.name = ''
      this.email = ''
      this.message = ''
    },
  },
}
</script>

<style scoped>
.contact-form {
  max-width: 500px;
  margin: 40px auto;
  text-align: left;
}

.form-group {
  margin-bottom: 20px;
}

label {
  display: block;
  margin-bottom: 6px;
}

input,
textarea {
  width: 100%;
  padding: 10px;
  border: 1px solid #ddd;
  border-radius: 5px;
}

textarea {
  height: 120px;
}

button {
  background: #222;
  color: white;
  padding: 10px 18px;
  border: none;
  cursor: pointer;
}

.success {
  margin-top: 15px;
  color: green;
}
</style>
