// ./src/views/Restaurant.vue
<template>
  <div class="container py-5">
    <h1>餐廳描述頁</h1>
    <!-- 餐廳資訊頁 RestaurantDetail -->
    <RestaurantDetail :initialRestaurant="restaurant" />
    <hr />
    <!-- 餐廳評論 RestaurantComments -->
    <RestaurantComments
      :restaurantComments="restaurantComments"
      @after-delete-comment="afterDeleteComment"
    />
    <!-- 新增評論 CreateComment -->
    <CreateComment
      :restaurantId="restaurant.id"
      @after-create-comment="afterCreateComment"
    />
  </div>
</template>

<script>
import RestaurantDetail from "./../components/RestaurantDetail";
import RestaurantComments from "./../components/RestaurantComments";
import CreateComment from "./../components/CreateComment";

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
    updatedAt: "2022-02-08T05:55:36.824Z",
    CategoryId: 1,
    Category: {
      id: 1,
      name: "中式料理",
      createdAt: "2022-02-02T02:48:47.000Z",
      updatedAt: "2022-02-02T02:48:47.000Z",
    },
    FavoritedUsers: [],
    LikedUsers: [],
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
  isFavorited: false,
  isLiked: false,
};
const dummyUser = {
  currentUser: {
    id: 1,
    name: "管理者",
    email: "root@example.com",
    image: "https://i.pravatar.cc/300",
    isAdmin: true,
  },
  isAuthenticated: true,
};

export default {
  components: {
    RestaurantDetail,
    RestaurantComments,
    CreateComment,
  },
  data() {
    return {
      restaurant: {
        id: -1,
        name: "",
        categoryName: "",
        image: "",
        openingHours: "",
        tel: "",
        address: "",
        description: "",
        isFavorited: false,
        isLiked: false,
      },
      currentUser: dummyUser.currentUser,
      restaurantComments: [],
    };
  },
  created() {
    const { id: restaurantId } = this.$route.params;
    this.fetchRestaurant(restaurantId);
  },
  methods: {
    fetchRestaurant(restaurantId) {
      console.log("fetchRestaurant id: ", restaurantId);

      this.restaurant = {
        id: dummyData.restaurant.id,
        name: dummyData.restaurant.name,
        categoryName: dummyData.restaurant.Category.name,
        image: dummyData.restaurant.image,
        openingHours: dummyData.restaurant.opening_hours,
        tel: dummyData.restaurant.tel,
        address: dummyData.restaurant.address,
        description: dummyData.restaurant.description,
        isFavorited: dummyData.isFavorited,
        isLiked: dummyData.isLiked,
      };

      this.restaurantComments = dummyData.restaurant.Comments;
    },
    afterDeleteComment(commentId) {
      // 以 filter 保留未被選擇的 comment.id
      this.restaurantComments = this.restaurantComments.filter(
        (comment) => comment.id !== commentId
      );
    },
    afterCreateComment(payload) {
      const { commentId, restaurantId, text } = payload;
      this.restaurantComments.push({
        id: commentId,
        RestaurantId: restaurantId,
        User: {
          id: this.currentUser.id,
          name: this.currentUser.name,
        },
        text,
        createdAt: new Date(),
      });
    },
  },
};
</script>
