<template>
  <section id="contact" class="bg-contact">
    <div class="title">
      <h2>CONTACT</h2>
    </div>
    <div class="contact-row">
      <div class="contact-info column">
        <ul class="list-group list-group-flush">
          <li v-if="contact.city !== ''" class="list-group-item">
            <h3 class="d-inline">
              <i class="fas fa-map-marker-alt"></i> Location:
            </h3>
            <br class="d-md-none" />
            <span> {{ contact.city }}</span>
          </li>
          <br class="d-md-none" />

          <li class="list-group-item" v-if="contact.email !== ''">
            <h3 class="d-inline"><i class="fa fa-envelope"></i> Email:</h3>
            <br class="d-md-none" />

            <span>{{ contact.email }}</span>
          </li>

          <br class="d-md-none" />

          <li class="list-group-item" v-if="contact.phone !== ''">
            <h3 class="d-inline"><i class="fas fa-phone"></i> Phone:</h3>
            <br class="d-md-none" />

            <span>{{ contact.phone }}</span>
          </li>
          <br class="d-md-none" />
          <li class="list-group-item" v-if="contact.github !== ''">
            <h3 class="d-inline"><i class="fab fa-github"></i> Github: </h3>
            <br class="d-md-none" />
            <a :href="contact.github" target="_blank"> {{ contact.github }}</a>
          </li>
          <br class="d-md-none" />
          <li class="list-group-item" v-if="contact.github !== ''">
            <h3 class="d-inline"><i class="fab fa-github"></i> LinkedIn: </h3>
            <br class="d-md-none" />
            <a :href="contact.linkedin" target="_blank"> Fatma Gül Yurtseven </a>
          </li>
        </ul>
      </div>
      <div class="contact-form column">
        <h1 class="contact-form-title">Send me a message</h1>

        <div v-if="isSending" class="loading">Sending...</div>

        <form class="form" @submit="onSubmit">
          <input
            required
            name="name"
            v-model="contact.name"
            placeholder="Name"
            type="text"
            autocomplete="off"
          />
          <input
            required
            name="email"
            v-model="contact.email"
            placeholder="E-mail"
            type="email"
            autocomplete="off"
          />
          <textarea
            name="message"
            v-model="contact.message"
            rows="4"
            placeholder="Message"
          ></textarea>
          <button class="button">Send</button>
        </form>
      </div>
    </div>
  </section>
</template>
<script>
export default {
  data() {
    return {
      contact: {
        city: "Bursa, TURKEY",
        email: "yurtsevenfatmagul@gmail.com",
        phone: "0534 123 44 55",
        github : "https://github.com/Fatmagul13",
        linkedin: "https://www.linkedin.com/in/fatma-g%C3%BCl-yurtseven-a8a32b145/"
      },

      isSending: false,
    };
  },
  methods:{
    onSubmit(){
      this.isSending = true;
    }
  }
};
</script>
<style scoped lang="scss">
@import "@/styles/contact.scss";
</style>