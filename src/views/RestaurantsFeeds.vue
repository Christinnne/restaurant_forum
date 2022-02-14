// ./src/views/RestaurantsFeeds.vue
<template>
  <div class="container py-5">
    <NavTabs />

    <h1 class="mt-5">最新動態</h1>
    <hr />
    <div class="row">
      <div class="col-md-6">
        <h3>最新餐廳</h3>
        <NewestRestaurants :restaurants="restaurants" />
        <!-- 最新餐廳 NewestRestaurants -->
      </div>
      <div class="col-md-6">
        <!-- 最新評論 NewestComments-->
        <h3>最新評論</h3>
        <NewestComments :comments="comments"/>
      </div>
    </div>
  </div>
</template>

<script>
import NavTabs from "./../components/NavTabs";
import NewestRestaurants from "./../components/NewestRestaurants";
import NewestComments from "./../components/NewestComments";

const dummyData = {
  restaurants: [
    {
      id: 33,
      name: "Retta Bayer",
      tel: "(142) 215-6748 x7608",
      address: "160 Fern Mission",
      opening_hours: "08:00",
      description:
        "Deleniti laudantium doloremque autem facilis maiores sequi vel soluta.\nUt cum qui et tempora.",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=25.966888760244956",
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
    },
    {
      id: 45,
      name: "Devonte Daugherty",
      tel: "1-081-329-7683",
      address: "19189 Auer Village",
      opening_hours: "08:00",
      description: "Labore et minima facilis rerum porro modi repellendus.",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=85.89947862411498",
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
    },
    {
      id: 35,
      name: "Verla Welch",
      tel: "(774) 010-3010",
      address: "333 Christina Causeway",
      opening_hours: "08:00",
      description:
        "Laborum ex deleniti. Aliquid omnis praesentium voluptas excepturi occaecati et eius explicabo minima.",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=36.73170137263679",
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
    },
    {
      id: 13,
      name: "Zaria Hackett Jr.",
      tel: "1-764-801-7864 x69093",
      address: "85565 O'Hara Freeway",
      opening_hours: "08:00",
      description: "tenetur",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=69.44502653264344",
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
    },
    {
      id: 34,
      name: "Frederique Kuhic",
      tel: "242-477-4740",
      address: "641 Juvenal Streets",
      opening_hours: "08:00",
      description:
        "Est eos ad. Voluptatem atque aut praesentium harum sit totam distinctio suscipit. Et in corporis sit fugit ut fugit ut laudantium numquam. Qui sed quia. Corporis nobis et qui consequatur eveniet neque.",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=91.32474285653838",
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
    },
    {
      id: 26,
      name: "Priscilla Prohaska IV",
      tel: "(189) 860-9582",
      address: "8578 Kling Keys",
      opening_hours: "08:00",
      description:
        "Quod est eius.\nFuga quibusdam non qui repellendus ut necessitatibus dicta ut.\nIusto eum accusamus autem enim in saepe.\nEt laudantium voluptatum fugit nostrum tempora.\nQuam consequuntur non voluptatem amet.",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=75.83685282747561",
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
    },
    {
      id: 1,
      name: "Brandon Trantow",
      tel: "1-748-466-4588 x2170",
      address: "12121 Wendell Lakes",
      opening_hours: "08:00",
      description:
        "Adipisci saepe alias recusandae harum consequatur in hic rerum. Aliquam ut et error quos rerum adipisci est rerum qui. Aut quibusdam accusantium ab voluptatem. Recusandae non distinctio nemo enim ullam quia asperiores. Ut ullam quidem saepe non est a quo aliquid. Veniam numquam totam sint esse qui quo.",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=63.26051580842733",
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
      Category: {
        id: 1,
        name: "中式料理",
        createdAt: "2022-02-02T02:48:47.000Z",
        updatedAt: "2022-02-02T02:48:47.000Z",
      },
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
    },
    {
      id: 36,
      name: "Miss Dahlia Mertz",
      tel: "1-882-877-1605",
      address: "644 Medhurst Junctions",
      opening_hours: "08:00",
      description:
        "Nulla occaecati voluptatem est quae et magni aspernatur maxime.",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=32.161278868708074",
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
    },
  ],
  comments: [
    {
      id: 12,
      text: "Iste recusandae quam tempora aut porro vel qui.",
      UserId: 1,
      RestaurantId: 12,
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
      Restaurant: {
        id: 12,
        name: "Rosamond Gibson",
        tel: "(811) 541-5058 x793",
        address: "8557 Kohler Fords",
        opening_hours: "08:00",
        description:
          "Officiis error nobis velit. Suscipit et aut est iure suscipit eligendi earum est. Commodi laudantium sunt molestias enim. Placeat qui est sint voluptatem velit sed eum. Ullam et temporibus aut facere laudantium eius corporis est.\n \rEt aliquid consequatur doloribus expedita velit aliquam quas eos. Esse voluptas suscipit voluptate dolorem odit maxime. Et odio officiis nobis asperiores consequuntur repudiandae itaque dolorem sit. Officiis qui voluptate vero cupiditate facere nam.\n \rNatus velit ut ipsum consectetur. Distinctio incidunt accusantium iure consequuntur. Aliquam inventore modi molestiae inventore officiis nihil. Ut fugit voluptas tempora nostrum odio commodi voluptas sed. Voluptatibus modi porro maiores consequuntur dolor in dolorum voluptas.",
        image:
          "https://loremflickr.com/320/240/restaurant,food/?random=48.571527415885306",
        viewCounts: 0,
        createdAt: "2022-02-02T02:48:47.000Z",
        updatedAt: "2022-02-02T02:48:47.000Z",
        CategoryId: 4,
      },
    },
    {
      id: 28,
      text: "Et id nemo beatae consequatur explicabo aut odit quo deserunt.",
      UserId: 1,
      RestaurantId: 28,
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
      Restaurant: {
        id: 28,
        name: "Manuel Rau",
        tel: "1-233-121-5549 x588",
        address: "4824 Osinski Dam",
        opening_hours: "08:00",
        description:
          "Aut earum dolores minima rerum voluptatibus reiciendis praesentium. Voluptatum repellat iusto quam quibusdam. Laboriosam ut asperiores nam aspernatur quidem accusamus sint et.\n \rConsequatur consequatur consectetur corporis expedita. Incidunt molestias vel aperiam. Et nihil reiciendis. Qui sed aut eligendi hic sit earum rem omnis. Minima ipsam provident.\n \rEt unde ducimus sit fuga ut ex reprehenderit quod ipsam. Repellat dolor soluta tenetur et beatae fugit neque quam. Quo optio error ducimus quis eligendi sequi voluptate. Architecto laboriosam quis blanditiis enim. Voluptatibus aliquid porro et ullam dolorum maxime. Saepe dolor laudantium ut sit qui enim fugit.",
        image:
          "https://loremflickr.com/320/240/restaurant,food/?random=59.239672841169266",
        viewCounts: 0,
        createdAt: "2022-02-02T02:48:47.000Z",
        updatedAt: "2022-02-02T02:48:47.000Z",
        CategoryId: 4,
      },
    },
    {
      id: 68,
      text: "Quia omnis possimus modi provident itaque.",
      UserId: 1,
      RestaurantId: 18,
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
      Restaurant: {
        id: 18,
        name: "Bradford Miller",
        tel: "1-866-781-1607 x8441",
        address: "48020 Cynthia Groves",
        opening_hours: "08:00",
        description:
          "Perspiciatis quas et optio accusantium.\nTemporibus est dolorem vero ut dolorem provident.\nNecessitatibus et et est dolorum.\nAt eum quisquam cumque.",
        image:
          "https://loremflickr.com/320/240/restaurant,food/?random=16.55556113122185",
        viewCounts: 0,
        createdAt: "2022-02-02T02:48:47.000Z",
        updatedAt: "2022-02-02T02:48:47.000Z",
        CategoryId: 3,
      },
    },
    {
      id: 85,
      text: "Labore molestias ex a iste ex.",
      UserId: 1,
      RestaurantId: 35,
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
      Restaurant: {
        id: 35,
        name: "Verla Welch",
        tel: "(774) 010-3010",
        address: "333 Christina Causeway",
        opening_hours: "08:00",
        description:
          "Laborum ex deleniti. Aliquid omnis praesentium voluptas excepturi occaecati et eius explicabo minima.",
        image:
          "https://loremflickr.com/320/240/restaurant,food/?random=36.73170137263679",
        viewCounts: 0,
        createdAt: "2022-02-02T02:48:47.000Z",
        updatedAt: "2022-02-02T02:48:47.000Z",
        CategoryId: 3,
      },
    },
    {
      id: 118,
      text: "Velit necessitatibus maxime sunt rerum eum dolorum.",
      UserId: 1,
      RestaurantId: 18,
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
      Restaurant: {
        id: 18,
        name: "Bradford Miller",
        tel: "1-866-781-1607 x8441",
        address: "48020 Cynthia Groves",
        opening_hours: "08:00",
        description:
          "Perspiciatis quas et optio accusantium.\nTemporibus est dolorem vero ut dolorem provident.\nNecessitatibus et et est dolorum.\nAt eum quisquam cumque.",
        image:
          "https://loremflickr.com/320/240/restaurant,food/?random=16.55556113122185",
        viewCounts: 0,
        createdAt: "2022-02-02T02:48:47.000Z",
        updatedAt: "2022-02-02T02:48:47.000Z",
        CategoryId: 3,
      },
    },
    {
      id: 136,
      text: "Illum pariatur ad voluptatibus.",
      UserId: 1,
      RestaurantId: 36,
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
      Restaurant: {
        id: 36,
        name: "Miss Dahlia Mertz",
        tel: "1-882-877-1605",
        address: "644 Medhurst Junctions",
        opening_hours: "08:00",
        description:
          "Nulla occaecati voluptatem est quae et magni aspernatur maxime.",
        image:
          "https://loremflickr.com/320/240/restaurant,food/?random=32.161278868708074",
        viewCounts: 0,
        createdAt: "2022-02-02T02:48:47.000Z",
        updatedAt: "2022-02-02T02:48:47.000Z",
        CategoryId: 3,
      },
    },
    {
      id: 11,
      text: "Pariatur ut sed voluptatem sed in cum est maxime ut.",
      UserId: 2,
      RestaurantId: 11,
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
      Restaurant: {
        id: 11,
        name: "Junius Reichel",
        tel: "1-117-157-0441 x50435",
        address: "1258 Rocio Square",
        opening_hours: "08:00",
        description:
          "Voluptas tempora quisquam id in architecto quas consectetur.\nVoluptatem voluptatibus aliquam iusto laborum.",
        image:
          "https://loremflickr.com/320/240/restaurant,food/?random=18.731777546003304",
        viewCounts: 0,
        createdAt: "2022-02-02T02:48:47.000Z",
        updatedAt: "2022-02-02T02:48:47.000Z",
        CategoryId: 2,
      },
    },
    {
      id: 41,
      text: "Non iure dolor earum aliquid architecto.",
      UserId: 2,
      RestaurantId: 41,
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
      Restaurant: {
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
      },
    },
    {
      id: 56,
      text: "Hic vel sit qui quo.",
      UserId: 2,
      RestaurantId: 6,
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
      Restaurant: {
        id: 6,
        name: "Deron Mann",
        tel: "1-335-310-5989",
        address: "66126 Gusikowski Burgs",
        opening_hours: "08:00",
        description:
          "Quis nulla quae eos repellendus labore illo molestias. Hic et inventore animi earum amet non nesciunt harum sed. Aliquam error totam est illo rerum. Et molestiae id rem non cumque est doloribus et minus.",
        image:
          "https://loremflickr.com/320/240/restaurant,food/?random=71.57735717799056",
        viewCounts: 0,
        createdAt: "2022-02-02T02:48:47.000Z",
        updatedAt: "2022-02-02T02:48:47.000Z",
        CategoryId: 5,
      },
    },
    {
      id: 93,
      text: "Rerum perferendis animi minima.",
      UserId: 2,
      RestaurantId: 43,
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
      Restaurant: {
        id: 43,
        name: "Hilton West",
        tel: "085.229.1049 x62395",
        address: "62645 Phyllis Well",
        opening_hours: "08:00",
        description:
          "Adipisci earum totam non ipsam praesentium quis. Sint voluptatem laboriosam ut delectus dicta itaque soluta sint itaque. Quidem consectetur a quo quia sed sapiente cum quos.",
        image:
          "https://loremflickr.com/320/240/restaurant,food/?random=22.874090202232566",
        viewCounts: 0,
        createdAt: "2022-02-02T02:48:47.000Z",
        updatedAt: "2022-02-02T02:48:47.000Z",
        CategoryId: 1,
      },
    },
  ],
};

export default {
  components: {
    NavTabs,
    NewestRestaurants,
    NewestComments,
  },
  data() {
    return {
      restaurants: [],
      comments: [],
    };
  },
  created() {
    this.fetchFeeds();
  },
  methods: {
    fetchFeeds() {
      this.restaurants = dummyData.restaurants;
      this.comments = dummyData.comments;
    },
  },
};
</script>