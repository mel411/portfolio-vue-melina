<template>
  <form class="contact-form" @submit.prevent="submitForm">
    <div class="form-group">
      <label for="fullname">Nom / Prénom</label>
      <input id="fullname" type="text" v-model="fullName" required />
    </div>

    <div class="form-group">
      <label for="subject">Objet</label>
      <input id="subject" type="text" v-model="subject" required />
    </div>

    <div class="form-group">
      <label for="message">Message</label>
      <textarea id="message" v-model="message" required></textarea>
    </div>

    <button type="submit">Envoyer</button>

    <p v-if="sent" class="success">
      Votre messagerie s’est ouverte avec le message prêt à être envoyé.
    </p>
  </form>
</template>

<script>
export default {
  name: "ContactForm",
  data() {
    return {
      fullName: "",
      subject: "",
      message: "",
      sent: false,
      contactEmail: import.meta.env.VITE_CONTACT_EMAIL || "",
    };
  },
  methods: {
    submitForm() {
      if (!this.contactEmail) {
        alert("Aucune adresse email n’a été définie dans le fichier .env.");
        return;
      }

      const body = `Nom / Prénom : ${this.fullName}\n\nMessage :\n${this.message}`;
      const mailtoLink = `mailto:${this.contactEmail}?subject=${encodeURIComponent(
        this.subject
      )}&body=${encodeURIComponent(body)}`;

      window.location.href = mailtoLink;

      this.sent = true;
      this.fullName = "";
      this.subject = "";
      this.message = "";
    },
  },
};
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
  color: #3f3832;
  font-weight: 600;
}

input,
textarea {
  width: 100%;
  padding: 12px;
  border: 1px solid #ddd0c2;
  border-radius: 10px;
  background: #fff;
}

textarea {
  height: 140px;
  resize: vertical;
}

button {
  background: #1f1c19;
  color: white;
  padding: 12px 20px;
  border: none;
  border-radius: 999px;
  cursor: pointer;
  font-weight: 600;
}

.success {
  margin-top: 15px;
  color: #6e5640;
  line-height: 1.6;
}
</style>