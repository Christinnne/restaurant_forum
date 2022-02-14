// ./src/views/UsersTop.vue
// ./src/views/UsersTop.vue
<template>
  <div class="container py-5">
    <NavTabs />
    <h1 class="mt-5">美食達人</h1>
    <hr />
    <UserTopCards v-for="topUser in topUsers" :key="topUser.id" :initialTopUser="topUser" />
  </div>
</template>

<script>
import NavTabs from "./../components/NavTabs";
import UserTopCards from "./../components/UserTopCards";

const mummyData = {
  users: [
    {
      id: 1,
      name: "root",
      email: "root@example.com",
      password: "$2a$10$wkuQT8wtThezNRS1CtKQ0Olor3ZtNSAR0eM2PqNqWX9FTktBVRt8q",
      isAdmin: true,
      image: "https://hips.hearstapps.com/hmg-prod.s3.amazonaws.com/images/244943289-550596389377843-4686628598412395138-n-1-1636211757.jpg?resize=320:*",
      createdAt: "2022-02-02T02:48:46.000Z",
      updatedAt: "2022-02-02T02:48:46.000Z",
      Followers: [],
      FollowerCount: 0,
      isFollowed: false,
    },
    {
      id: 2,
      name: "user1",
      email: "user1@example.com",
      password: "$2a$10$LipP8RQ9rz0NF6j8Ffcgn.3vIn8S5zdrS9hcitP5AYRMpME4jRHtO",
      isAdmin: false,
      image: "https://hips.hearstapps.com/hmg-prod.s3.amazonaws.com/images/245268288-2590813344396802-5103702027470446767-n-1-1636218208.jpg?crop=1xw:1xh;center,top&resize=480:*",
      createdAt: "2022-02-02T02:48:46.000Z",
      updatedAt: "2022-02-02T02:48:46.000Z",
      Followers: [],
      FollowerCount: 0,
      isFollowed: false,
    },
    {
      id: 3,
      name: "user2",
      email: "user2@example.com",
      password: "$2a$10$qO/qgzAvlu/FlBRF2pTo9OloBaxR9X5QxnRafBdGbhefvuaeypkB6",
      isAdmin: false,
      image: "https://hips.hearstapps.com/hmg-prod.s3.amazonaws.com/images/245083708-403124851251547-8620694350855699042-n-1-1636218209.jpg?crop=1xw:1xh;center,top&resize=480:*",
      createdAt: "2022-02-02T02:48:47.000Z",
      updatedAt: "2022-02-02T02:48:47.000Z",
      Followers: [],
      FollowerCount: 0,
      isFollowed: false,
    },
  ],
};

export default {
  components: {
    NavTabs,
    UserTopCards,
  },
  data() {
    return {
      topUsers: [],
    };
  },
  created() {
    this.fetchData();
  },
  methods: {
    fetchData() {
      this.topUsers = mummyData.users;
    },
  },
};
</script>