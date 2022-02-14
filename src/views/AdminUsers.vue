<template>
  <div class="container py-5">
    <!-- AdminNav Component -->
    <AdminNav />
    <table class="table">
      <thead class="thead-dark">
        <tr>
          <th scope="col">#</th>
          <th scope="col">Email</th>
          <th scope="col">Role</th>
          <th scope="col" width="140">Action</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="user in users" :key="user.id">
          <th scope="row">{{ user.id }}</th>
          <td>{{ user.email }}</td>
          <td>{{ user.isAdmin ? "admin" : "user" }}</td>
          <td>
            <button
              type="button"
              class="btn btn-link"
              @click="toggleUserRole(user.id)"
            >
              {{ user.isAdmin ? "set as user" : "set as admin" }}
            </button>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
import AdminNav from "./../components/AdminNav";
const dummyData = {
  users: [
    {
      id: 1,
      name: "root",
      email: "root@example.com",
      password: "$2a$10$wkuQT8wtThezNRS1CtKQ0Olor3ZtNSAR0eM2PqNqWX9FTktBVRt8q",
      isAdmin: true,
      image: null,
      createdAt: "2022-02-02T02:48:46.000Z",
      updatedAt: "2022-02-02T02:48:46.000Z",
    },
    {
      id: 2,
      name: "user1",
      email: "user1@example.com",
      password: "$2a$10$LipP8RQ9rz0NF6j8Ffcgn.3vIn8S5zdrS9hcitP5AYRMpME4jRHtO",
      isAdmin: false,
      image: null,
      createdAt: "2022-02-02T02:48:46.000Z",
      updatedAt: "2022-02-02T02:48:46.000Z",
    },
    {
      id: 3,
      name: "user2",
      email: "user2@example.com",
      password: "$2a$10$qO/qgzAvlu/FlBRF2pTo9OloBaxR9X5QxnRafBdGbhefvuaeypkB6",
      isAdmin: false,
      image: null,
      createdAt: "2022-02-02T02:48:47.000Z",
      updatedAt: "2022-02-02T02:48:47.000Z",
    },
  ],
};
export default {
  components: {
    AdminNav,
  },
  data() {
    return {
      users: [],
    };
  },
  created() {
    this.fetchData();
  },
  methods: {
    fetchData() {
      const { users } = dummyData;
      this.users = users;
    },
    toggleUserRole(userId) {
      this.users = this.users.map((user) => {
        if (user.id === userId) {
          return {
            ...user,
            isAdmin: !user.isAdmin,
          };
        }
        return user;
      });
    },
  },
};
</script>
