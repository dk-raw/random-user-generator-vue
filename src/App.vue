<template>
  <Navbar brand="Random User Generator" />
  <section class="header">
    <h1 class="text-center">Random User Generator</h1>
    <p class="text-center text-muted">generate a random user!</p>
  </section>
  <div class="container">
    <button
      class="btn btn-outline-success btn-lg center my-4"
      @click="generateUser"
    >
      Generate
    </button>
    <img
      :src="thumbnailUrl"
      :alt="fname + ' ' + lname"
      class="img-fluid rounded border border-white my-3"
    />
    <p class="text-break">Name: {{ fname }} {{ lname }}</p>
    <p class="text-break">Gender: {{ gender }}</p>
    <p class="text-break">Location: {{ city }}, {{ country }}</p>
    <p class="text-break">Email: {{ email }}</p>
    <p class="text-break">Phone: {{ phone }}</p>
    <p class="text-break">Age: {{ age }}</p>
    <p class="text-break">Social Username: {{ username }}</p>
  </div>
</template>

<script>
import Navbar from "./components/Navbar.vue";
import defaultPicture from "./assets/default-picture.jpg";

export default {
  name: "App",
  components: {
    Navbar,
  },
  data() {
    return {
      counter: 0,
      fname: "Jonh",
      lname: "Doe",
      email: "jdoe2000@gmail.com",
      phone: "000-000-000",
      city: "Athens",
      country: "Greece",
      gender: "Male",
      age: "30",
      thumbnailUrl: defaultPicture,
      username: "johnTheRipper3000",
    };
  },
  methods: {
    async generateUser() {
      const response = await fetch("https://randomuser.me/api/");
      const res = await response.json();
      console.log(res.results[0]);
      this.fname = res.results[0].name.first;
      this.lname = res.results[0].name.last;
      this.email = res.results[0].email;
      this.phone = res.results[0].phone;
      this.city = res.results[0].location.city;
      this.country = res.results[0].location.country;
      this.gender = res.results[0].gender;
      this.age = res.results[0].dob.age;
      this.thumbnailUrl = res.results[0].picture.large;
      this.username = res.results[0].login.username;
    },
  },
};
</script>
