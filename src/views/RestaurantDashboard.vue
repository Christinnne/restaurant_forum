<template>
  <div class="container py-5">
    <div>
      <h1>{{ restaurant.name }}</h1>
      <span class="badge badge-secondary mt-1 mb-3">
        {{ restaurant.categoryName }}
      </span>
    </div>

    <hr />

    <ul>
      <li>評論數： {{ restaurant.commentsLength }} </li>
      <li>瀏覽次數： {{ restaurant.viewCounts }} </li>
    </ul>

    <button type="button" class="btn btn-link" @click="$router.back()">
      回上一頁
    </button>
  </div>
</template>

<script>
const dummyData = {
  restaurant: {
    id: 1,
    name: "Brandon Trantow",
    tel: "1-748-466-4588 x2170",
    address: "12121 Wendell Lakes",
    opening_hours: "08:00",
    description:
      "Adipisci saepe alias recusandae harum consequatur in hic rerum. Aliquam ut et error quos rerum adipisci est rerum qui. Aut quibusdam accusantium ab voluptatem. Recusandae non distinctio nemo enim ullam quia asperiores. Ut ullam quidem saepe non est a quo aliquid. Veniam numquam totam sint esse qui quo.",
    image:
      "https://loremflickr.com/320/240/restaurant,food/?random=63.26051580842733",
    viewCounts: 1,
    createdAt: "2022-02-02T02:48:47.000Z",
    updatedAt: "2022-02-08T05:55:36.000Z",
    CategoryId: 1,
    Category: {
      id: 1,
      name: "中式料理",
      createdAt: "2022-02-02T02:48:47.000Z",
      updatedAt: "2022-02-02T02:48:47.000Z",
    },
    Comments: [
      {
        id: 1,
        text: "In veniam nesciunt quisquam dolorem iure soluta iure magni qui.",
        UserId: 1,
        RestaurantId: 1,
        createdAt: "2022-02-02T02:48:47.000Z",
        updatedAt: "2022-02-02T02:48:47.000Z",
        User: {
          id: 1,
          name: "root",
          email: "root@example.com",
          password:
            "$2a$10$wkuQT8wtThezNRS1CtKQ0Olor3ZtNSAR0eM2PqNqWX9FTktBVRt8q",
          isAdmin: true,
          image: null,
          createdAt: "2022-02-02T02:48:46.000Z",
          updatedAt: "2022-02-02T02:48:46.000Z",
        },
      },
      {
        id: 51,
        text: "Et occaecati blanditiis eveniet repellendus.",
        UserId: 2,
        RestaurantId: 1,
        createdAt: "2022-02-02T02:48:47.000Z",
        updatedAt: "2022-02-02T02:48:47.000Z",
        User: {
          id: 2,
          name: "user1",
          email: "user1@example.com",
          password:
            "$2a$10$LipP8RQ9rz0NF6j8Ffcgn.3vIn8S5zdrS9hcitP5AYRMpME4jRHtO",
          isAdmin: false,
          image: null,
          createdAt: "2022-02-02T02:48:46.000Z",
          updatedAt: "2022-02-02T02:48:46.000Z",
        },
      },
      {
        id: 101,
        text: "Quia blanditiis aliquid animi nisi sed.",
        UserId: 2,
        RestaurantId: 1,
        createdAt: "2022-02-02T02:48:47.000Z",
        updatedAt: "2022-02-02T02:48:47.000Z",
        User: {
          id: 2,
          name: "user1",
          email: "user1@example.com",
          password:
            "$2a$10$LipP8RQ9rz0NF6j8Ffcgn.3vIn8S5zdrS9hcitP5AYRMpME4jRHtO",
          isAdmin: false,
          image: null,
          createdAt: "2022-02-02T02:48:46.000Z",
          updatedAt: "2022-02-02T02:48:46.000Z",
        },
      },
    ],
  },
};

export default {
  data() {
    return {
      restaurant: {
        name: "",
        categoryName: "",
        commentsLength: 0,
        viewCounts: 0,
      },
    };
  },
  created() {
    this.fetchData();
  },
  methods: {
    fetchData() {
      this.restaurant = {
        name: dummyData.restaurant.name,
        categoryName: dummyData.restaurant.categoryName,
        commentsLength: dummyData.restaurant.Comments.length,
        viewCounts: dummyData.restaurant.viewCounts,
      };
    },
  },
};
</script>
