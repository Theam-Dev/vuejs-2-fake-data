<template>
  <div id="app">
    <pre>{{personas}}</pre>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      persona: {
        firstName: "",
        lastName: "",
        email: "",
        dateOfBirth: "",
        country: "",
        companyName: "",
        occupation: "",
        avatar: "",
        client: false,
        internet: 1,
        socialMedia: 1,
        mobileApps: 1,
        software: 1
      },
      personas: {}
    };
  },
  created() {
    this.personas.data = [];
    for (let i = 0; i < 10; i++) {
      this.createPersona();
      this.personas.data.push(this.persona);
    }
  },
  methods: {
    createPersona() {
      this.persona = {};
      this.persona.firstName = this.$faker().name.firstName();
      this.persona.lastName = this.$faker().name.lastName();
      this.persona.email = this.$faker().internet.email();
      this.persona.dateOfBirth = this.$faker().date.past(
        Math.floor(Math.random() * (100 - 18 + 1) + 18),
        "2019-07-26"
      );
      this.persona.country = this.$faker().address.country();
      this.persona.companyName = this.$faker().company.companyName();
      this.persona.occupation = this.$faker().name.jobTitle();
      this.persona.avatar = this.$faker().image.imageUrl(32, 32, "people");
      this.persona.client = this.$faker().random.boolean();
      this.persona.internet = Math.floor(Math.random() * 5 + 1);
      this.persona.socialMedia = Math.floor(Math.random() * 5 + 1);
      this.persona.mobileApps = Math.floor(Math.random() * 5 + 1);
      this.persona.software = Math.floor(Math.random() * 5 + 1);
    }
  }
};
</script>