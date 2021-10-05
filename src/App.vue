<template>
  <Navbar brand="Random User Generator" />
  <section class="header">
    <h1 class="text-center">Random User Generator</h1>
    <p class="lead text-center">generate a random person!</p>
    <button class="btn btn-success btn-lg center my-4" @click="generateUser">
      <i class="bi bi-arrow-repeat"></i> Generate
    </button>
  </section>
  <div class="container">
    <img
      :src="thumbnailUrl"
      :alt="fname + ' ' + lname"
      class="img-fluid rounded border border-white my-3 center"
    />
    <Table
      :name="fname + ' ' + lname"
      :email="email"
      :phone="phone"
      :gender="gender"
      :age="age"
      :username="username"
      :location="city + ', ' + country"
    />
  </div>
</template>

<script>
import Navbar from "./components/Navbar.vue";
import Table from "./components/Table.vue";
import defaultPicture from "./assets/default-picture.jpg";

export default {
  name: "App",
  components: {
    Navbar,
    Table,
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
