// ./src/views/RestaurantsTop.vue
<template>
  <div class="container py-5">
    <NavTabs />
    <h1 class="mt-5">人氣餐廳</h1>
    <hr />
    <RestaurantsTopCard v-for="restaurant in restaurants" :key="restaurant.id" :initialRestaurant="restaurant"/>
  </div>
</template>

<script>
import NavTabs from "./../components/NavTabs";
import RestaurantsTopCard from "./../components/RestaurantsTopCard";

const dummyData = {
  restaurants: [
    {
      id: 50,
      name: "Kirk Kautzer",
      tel: "(542) 269-9217 x55665",
      address: "796 Towne Fords",
      opening_hours: "08:00",
      description: "qui occaecati voluptates",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=48.16521044667026",
      viewCounts: 0,
      createdAt: "2022-02-02T02:48:47.000Z",
      updatedAt: "2022-02-02T02:48:47.000Z",
      CategoryId: 3,
      FavoritedUsers: [],
      isFavorited: false,
      FavoriteCount: 0,
    },
    {
      id: 49,
      name: "Ali Rodriguez",
      tel: "568-330-0047 x986",
      address: "138 Joana Via",
      opening_hours: "08:00",
      description: "quis",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=33.295646737564425",
      viewCounts: 0,
      createdAt: "2022-02-02T02:48:47.000Z",
      updatedAt: "2022-02-02T02:48:47.000Z",
      CategoryId: 4,
      FavoritedUsers: [],
      isFavorited: false,
      FavoriteCount: 0,
    },
    {
      id: 48,
      name: "Roxanne Pfannerstill",
      tel: "477.302.1822 x803",
      address: "00142 Willms Heights",
      opening_hours: "08:00",
      description: "Incidunt voluptatem ex maxime provident sequi labo",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=62.456631544911815",
      viewCounts: 0,
      createdAt: "2022-02-02T02:48:47.000Z",
      updatedAt: "2022-02-02T02:48:47.000Z",
      CategoryId: 3,
      FavoritedUsers: [],
      isFavorited: false,
      FavoriteCount: 0,
    },
    {
      id: 47,
      name: "Dr. Lavonne Murray",
      tel: "805-696-1761 x019",
      address: "47825 Rippin Glens",
      opening_hours: "08:00",
      description: "Sit pariatur est provident totam dolores quo quia ",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=67.82183148540885",
      viewCounts: 0,
      createdAt: "2022-02-02T02:48:47.000Z",
      updatedAt: "2022-02-02T02:48:47.000Z",
      CategoryId: 5,
      FavoritedUsers: [],
      isFavorited: false,
      FavoriteCount: 0,
    },
    {
      id: 46,
      name: "Fritz Huel",
      tel: "(233) 149-4997",
      address: "899 Nolan Keys",
      opening_hours: "08:00",
      description: "atque fugit maxime",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=50.54358261327112",
      viewCounts: 0,
      createdAt: "2022-02-02T02:48:47.000Z",
      updatedAt: "2022-02-02T02:48:47.000Z",
      CategoryId: 4,
      FavoritedUsers: [],
      isFavorited: false,
      FavoriteCount: 0,
    },
    {
      id: 45,
      name: "Devonte Daugherty",
      tel: "1-081-329-7683",
      address: "19189 Auer Village",
      opening_hours: "08:00",
      description: "Labore et minima facilis rerum porro modi repellen",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=85.89947862411498",
      viewCounts: 0,
      createdAt: "2022-02-02T02:48:47.000Z",
      updatedAt: "2022-02-02T02:48:47.000Z",
      CategoryId: 2,
      FavoritedUsers: [],
      isFavorited: false,
      FavoriteCount: 0,
    },
    {
      id: 44,
      name: "Connor Reinger",
      tel: "(871) 049-0080 x844",
      address: "0957 Taylor Club",
      opening_hours: "08:00",
      description: "Corporis sed soluta atque rem accusantium odio ut.",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=88.2445333187868",
      viewCounts: 0,
      createdAt: "2022-02-02T02:48:47.000Z",
      updatedAt: "2022-02-02T02:48:47.000Z",
      CategoryId: 4,
      FavoritedUsers: [],
      isFavorited: false,
      FavoriteCount: 0,
    },
    {
      id: 43,
      name: "Hilton West",
      tel: "085.229.1049 x62395",
      address: "62645 Phyllis Well",
      opening_hours: "08:00",
      description: "Adipisci earum totam non ipsam praesentium quis. S",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=22.874090202232566",
      viewCounts: 0,
      createdAt: "2022-02-02T02:48:47.000Z",
      updatedAt: "2022-02-02T02:48:47.000Z",
      CategoryId: 1,
      FavoritedUsers: [],
      isFavorited: false,
      FavoriteCount: 0,
    },
    {
      id: 42,
      name: "Aracely Wiza DDS",
      tel: "1-264-736-6085 x33411",
      address: "7423 Jaquan Stravenue",
      opening_hours: "08:00",
      description: "perspiciatis",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=97.38629924405879",
      viewCounts: 0,
      createdAt: "2022-02-02T02:48:47.000Z",
      updatedAt: "2022-02-02T02:48:47.000Z",
      CategoryId: 1,
      FavoritedUsers: [],
      isFavorited: false,
      FavoriteCount: 0,
    },
    {
      id: 41,
      name: "Buster Zulauf",
      tel: "117.266.4555 x7595",
      address: "0296 Danial Dam",
      opening_hours: "08:00",
      description: "asperiores quibusdam nam",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=92.18176355804972",
      viewCounts: 0,
      createdAt: "2022-02-02T02:48:47.000Z",
      updatedAt: "2022-02-02T02:48:47.000Z",
      CategoryId: 5,
      FavoritedUsers: [],
      isFavorited: false,
      FavoriteCount: 0,
    },
  ],
};

export default {
  components: {
    NavTabs,
    RestaurantsTopCard,
  },
  data() {
    return {
      restaurants: []
    }
  },
  created() {
    this.fetchData()
  },
  methods: {
    fetchData() {
      this.restaurants = dummyData.restaurants
    }
  }
};
</script>
