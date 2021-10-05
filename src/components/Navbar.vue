<template>
  <nav class="navbar fixed-top navbar-expand-lg navbar-dark bg-dark">
    <div class="container-fluid">
      <a class="navbar-brand" href="#"
        ><i class="bi bi-person-lines-fill"></i> {{ brand }}</a
      >
      <button
        class="navbar-toggler bg-success"
        type="button"
        data-bs-toggle="collapse"
        data-bs-target="#navbar"
      >
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="navbar-collapse text-center collapse" id="navbar">
        <ul class="navbar-nav ml-auto">
          <li class="nav-item">
            <a class="nav-link" href="https://dkatsios.ml" target="_blank"
              >made by damian</a
            >
          </li>
        </ul>
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