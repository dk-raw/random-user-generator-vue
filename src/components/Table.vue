<template>
  <table class="table table-dark table-bordered table-hover">
    <colgroup>
      <col span="1" style="width: 15%" />
      <col span="1" style="width: 85%" />
    </colgroup>
    <tbody>
      <tr>
        <th scope="row">Name</th>
        <td>{{ name }}</td>
      </tr>
      <tr>
        <th scope="row">Gender</th>
        <td>{{ gender }}</td>
      </tr>
      <tr>
        <th scope="row">Email</th>
        <td>{{ email }}</td>
      </tr>
      <tr>
        <th scope="row">Phone Number</th>
        <td>{{ phone }}</td>
      </tr>
      <tr>
        <th scope="row">Residence</th>
        <td>{{ location }}</td>
      </tr>
      <tr>
        <th scope="row">Age</th>
        <td>{{ age }}</td>
      </tr>
      <tr>
        <th scope="row">Username</th>
        <td>{{ username }}</td>
      </tr>
    </tbody>
  </table>
</template>

<script>
export default {
  name: "Table",
  props: {
    name: {
      type: String,
      required: true,
    },
    gender: {
      type: String,
      required: true,
    },
    email: {
      type: String,
      required: true,
    },
    phone: {
      type: String,
      required: true,
    },
    location: {
      type: String,
      required: true,
    },
    age: {
      type: Number,
      required: true,
    },
    username: {
      type: String,
      required: true,
    },
  },
};
</script>