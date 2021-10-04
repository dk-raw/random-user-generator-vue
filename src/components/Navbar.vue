<template>
  <nav class="navbar fixed-top navbar-expand-lg navbar-dark bg-dark">
    <div class="container-fluid">
      <a class="navbar-brand" href="#">{{brand}}</a>
      <div class="collapse navbar-collapse">
        <div class="navbar-nav"></div>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  name: "Navbar",
  props: {
    brand: {
      type: String,
      required: true,
    },
  },
};
</script>