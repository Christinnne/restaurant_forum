// ./src/components/AdminRestaurantsTable.vue
<template>
  <table class="table">
    <thead class="thead-dark">
      <tr>
        <th scope="col">#</th>
        <th scope="col">Category</th>
        <th scope="col">Name</th>
        <th scope="col" width="300">操作</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="restaurant in restaurants" :key="restaurant.id">
        <th scope="row">
          {{ restaurant.id }}
        </th>
        <td>{{ restaurant.Category ? restaurant.Category.name : "未分類" }}</td>
        <td>{{ restaurant.name }}</td>
        <td class="d-flex justify-content-between">
          <router-link
            :to="{ name: 'admin-restaurant', params: { id: restaurant.id } }"
            class="btn btn-link"
          >
            Show
          </router-link>

          <router-link
            :to="{
              name: 'admin-restaurant-edit',
              params: { id: restaurant.id },
            }"
            class="btn btn-link"
            >Edit</router-link
          >

          <button
            type="button"
            class="btn btn-link"
            @click.stop.prevent="deleteRestaurant(restaurant.id)"
          >
            Delete
          </button>
        </td>
      </tr>
    </tbody>
  </table>
</template>

<script>
const dummyData = {
  restaurants: [
    {
      id: 1,
      name: "Brandon Trantow",
      tel: "1-748-466-4588 x2170",
      address: "12121 Wendell Lakes",
      opening_hours: "08:00",
      description: "Adipisci saepe alias recusandae harum consequatur ",
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
      isFavorited: false,
      isLiked: false,
    },
    {
      id: 2,
      name: "Mr. Guido Torphy",
      tel: "560.811.4554 x8508",
      address: "4829 Baumbach Stream",
      opening_hours: "08:00",
      description: "Adipisci voluptatem assumenda at. Quia ea neque ne",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=46.19150110902006",
      viewCounts: 0,
      createdAt: "2022-02-02T02:48:47.000Z",
      updatedAt: "2022-02-02T02:48:47.000Z",
      CategoryId: 1,
      Category: {
        id: 1,
        name: "中式料理",
        createdAt: "2022-02-02T02:48:47.000Z",
        updatedAt: "2022-02-02T02:48:47.000Z",
      },
      isFavorited: false,
      isLiked: false,
    },
    {
      id: 3,
      name: "Ottilie Schoen",
      tel: "128-240-4416",
      address: "6545 Samara Park",
      opening_hours: "08:00",
      description: "fuga ea eum",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=85.3179175485218",
      viewCounts: 0,
      createdAt: "2022-02-02T02:48:47.000Z",
      updatedAt: "2022-02-02T02:48:47.000Z",
      CategoryId: 3,
      Category: {
        id: 3,
        name: "義大利料理",
        createdAt: "2022-02-02T02:48:47.000Z",
        updatedAt: "2022-02-02T02:48:47.000Z",
      },
      isFavorited: false,
      isLiked: false,
    },
    {
      id: 4,
      name: "Armando Graham",
      tel: "(664) 894-1574",
      address: "87764 Kautzer Vista",
      opening_hours: "08:00",
      description: "in",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=0.8559426630384337",
      viewCounts: 0,
      createdAt: "2022-02-02T02:48:47.000Z",
      updatedAt: "2022-02-02T02:48:47.000Z",
      CategoryId: 4,
      Category: {
        id: 4,
        name: "墨西哥料理",
        createdAt: "2022-02-02T02:48:47.000Z",
        updatedAt: "2022-02-02T02:48:47.000Z",
      },
      isFavorited: false,
      isLiked: false,
    },
    {
      id: 5,
      name: "Carmella Mraz",
      tel: "395-832-4366 x115",
      address: "56111 Mollie Streets",
      opening_hours: "08:00",
      description: "Impedit adipisci temporibus sapiente nihil odio re",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=18.90404891255337",
      viewCounts: 0,
      createdAt: "2022-02-02T02:48:47.000Z",
      updatedAt: "2022-02-02T02:48:47.000Z",
      CategoryId: 3,
      Category: {
        id: 3,
        name: "義大利料理",
        createdAt: "2022-02-02T02:48:47.000Z",
        updatedAt: "2022-02-02T02:48:47.000Z",
      },
      isFavorited: false,
      isLiked: false,
    },
    {
      id: 6,
      name: "Deron Mann",
      tel: "1-335-310-5989",
      address: "66126 Gusikowski Burgs",
      opening_hours: "08:00",
      description: "Quis nulla quae eos repellendus labore illo molest",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=71.57735717799056",
      viewCounts: 0,
      createdAt: "2022-02-02T02:48:47.000Z",
      updatedAt: "2022-02-02T02:48:47.000Z",
      CategoryId: 5,
      Category: {
        id: 5,
        name: "素食料理",
        createdAt: "2022-02-02T02:48:47.000Z",
        updatedAt: "2022-02-02T02:48:47.000Z",
      },
      isFavorited: false,
      isLiked: false,
    },
    {
      id: 7,
      name: "Miss Joannie Kunze",
      tel: "228.580.1141 x641",
      address: "65354 Rasheed Port",
      opening_hours: "08:00",
      description: "Impedit repellat eligendi praesentium aperiam comm",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=2.2039208395385534",
      viewCounts: 0,
      createdAt: "2022-02-02T02:48:47.000Z",
      updatedAt: "2022-02-02T02:48:47.000Z",
      CategoryId: 2,
      Category: {
        id: 2,
        name: "日本料理",
        createdAt: "2022-02-02T02:48:47.000Z",
        updatedAt: "2022-02-02T02:48:47.000Z",
      },
      isFavorited: false,
      isLiked: false,
    },
    {
      id: 8,
      name: "Molly Moore",
      tel: "113-598-1247",
      address: "616 Brown Gardens",
      opening_hours: "08:00",
      description: "Quisquam esse sunt repellat dolor aut dicta quos e",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=90.25797502886543",
      viewCounts: 0,
      createdAt: "2022-02-02T02:48:47.000Z",
      updatedAt: "2022-02-02T02:48:47.000Z",
      CategoryId: 1,
      Category: {
        id: 1,
        name: "中式料理",
        createdAt: "2022-02-02T02:48:47.000Z",
        updatedAt: "2022-02-02T02:48:47.000Z",
      },
      isFavorited: false,
      isLiked: false,
    },
    {
      id: 9,
      name: "Veronica Casper I",
      tel: "1-272-937-2661",
      address: "0641 Anastasia Trafficway",
      opening_hours: "08:00",
      description: "Qui reiciendis nesciunt libero velit consequatur e",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=24.224231585201505",
      viewCounts: 0,
      createdAt: "2022-02-02T02:48:47.000Z",
      updatedAt: "2022-02-02T02:48:47.000Z",
      CategoryId: 1,
      Category: {
        id: 1,
        name: "中式料理",
        createdAt: "2022-02-02T02:48:47.000Z",
        updatedAt: "2022-02-02T02:48:47.000Z",
      },
      isFavorited: false,
      isLiked: false,
    },
    {
      id: 10,
      name: "Suzanne Gutkowski Jr.",
      tel: "243.872.9916 x44038",
      address: "35160 Batz Brook",
      opening_hours: "08:00",
      description: "Consequatur ipsam asperiores. Inventore rem commod",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=24.233724051832706",
      viewCounts: 0,
      createdAt: "2022-02-02T02:48:47.000Z",
      updatedAt: "2022-02-02T02:48:47.000Z",
      CategoryId: 3,
      Category: {
        id: 3,
        name: "義大利料理",
        createdAt: "2022-02-02T02:48:47.000Z",
        updatedAt: "2022-02-02T02:48:47.000Z",
      },
      isFavorited: false,
      isLiked: false,
    },
  ],
  categories: [
    {
      id: 1,
      name: "中式料理",
      createdAt: "2022-02-02T02:48:47.000Z",
      updatedAt: "2022-02-02T02:48:47.000Z",
    },
    {
      id: 2,
      name: "日本料理",
      createdAt: "2022-02-02T02:48:47.000Z",
      updatedAt: "2022-02-02T02:48:47.000Z",
    },
    {
      id: 3,
      name: "義大利料理",
      createdAt: "2022-02-02T02:48:47.000Z",
      updatedAt: "2022-02-02T02:48:47.000Z",
    },
    {
      id: 4,
      name: "墨西哥料理",
      createdAt: "2022-02-02T02:48:47.000Z",
      updatedAt: "2022-02-02T02:48:47.000Z",
    },
    {
      id: 5,
      name: "素食料理",
      createdAt: "2022-02-02T02:48:47.000Z",
      updatedAt: "2022-02-02T02:48:47.000Z",
    },
    {
      id: 6,
      name: "美式料理",
      createdAt: "2022-02-02T02:48:47.000Z",
      updatedAt: "2022-02-02T02:48:47.000Z",
    },
    {
      id: 7,
      name: "複合式料理",
      createdAt: "2022-02-02T02:48:47.000Z",
      updatedAt: "2022-02-02T02:48:47.000Z",
    },
  ],
  categoryId: "",
  page: 1,
  totalPage: [1, 2, 3, 4, 5],
  prev: 1,
  next: 2,
};

export default {
  data() {
    return {
      restaurants: [],
    };
  },
  created() {
    this.fetchRestaurants();
  },
  methods: {
    fetchRestaurants() {
      this.restaurants = dummyData.restaurants;
    },
    deleteRestaurant(restaurantId) {
      this.restaurants = this.restaurants.filter(
        (restaurant) => restaurant.id !== restaurantId
      );
    },
  },
};
</script>