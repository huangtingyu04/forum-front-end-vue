// ./src/views/RestaurantsTop.vue
<template>
  <div class="container py-5">
    <!-- 使用 NavTabs 元件 -->
    <NavTabs />
    <h1 class="mt-5">人氣餐廳</h1>
    <RestaurantTopCard
      v-for="restaurant in restaurants"
      :key="restaurant.id"
      :initial-restaurant="restaurant"
    />
  </div>
</template>

<script>
import NavTabs from "./../components/NavTabs";
import RestaurantTopCard from "./../components/RestaurantTopCard";

const dummyData = {
  restaurants: [
    {
      id: 1,
      name: "Norwood Wehner Jr.",
      tel: "463.606.9752",
      address: "95284 Vernice Crossroad",
      opening_hours: "08:00",
      description: "Rerum dolor aliquam sapiente alias vel ipsa est se",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=15.319122876392854",
      viewCounts: 1,
      createdAt: "2021-11-10T13:02:01.000Z",
      updatedAt: "2021-11-14T02:27:04.000Z",
      CategoryId: 3,
      FavoritedUsers: [],
      isFavorited: false,
      FavoriteCount: 0,
    },
    {
      id: 22,
      name: "Sonia Stracke",
      tel: "(304) 125-8622",
      address: "3554 Baumbach Rapids",
      opening_hours: "08:00",
      description: "Culpa dicta ipsa voluptates sit. Consequatur omnis",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=38.752619355345175",
      viewCounts: 0,
      createdAt: "2021-11-10T13:02:01.000Z",
      updatedAt: "2021-11-10T13:02:01.000Z",
      CategoryId: 3,
      FavoritedUsers: [],
      isFavorited: false,
      FavoriteCount: 0,
    },
    {
      id: 23,
      name: "Angelo Koch",
      tel: "633-560-0029 x1233",
      address: "347 Turner Spring",
      opening_hours: "08:00",
      description: "Vel et fugiat aperiam dolorum.",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=76.66212643910806",
      viewCounts: 0,
      createdAt: "2021-11-10T13:02:01.000Z",
      updatedAt: "2021-11-10T13:02:01.000Z",
      CategoryId: 4,
      FavoritedUsers: [],
      isFavorited: false,
      FavoriteCount: 0,
    },
    {
      id: 24,
      name: "Shaina Halvorson",
      tel: "1-941-346-2472",
      address: "37825 Gaylord Port",
      opening_hours: "08:00",
      description: "Et in incidunt aut accusamus debitis facilis.",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=59.3486435674073",
      viewCounts: 0,
      createdAt: "2021-11-10T13:02:01.000Z",
      updatedAt: "2021-11-10T13:02:01.000Z",
      CategoryId: 1,
      FavoritedUsers: [],
      isFavorited: false,
      FavoriteCount: 0,
    },
    {
      id: 25,
      name: "Alexandria Mills",
      tel: "1-644-841-9837 x4319",
      address: "14443 Reichel Unions",
      opening_hours: "08:00",
      description: "Velit delectus optio quam corporis dolorem. Sunt b",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=81.99054350862407",
      viewCounts: 0,
      createdAt: "2021-11-10T13:02:01.000Z",
      updatedAt: "2021-11-10T13:02:01.000Z",
      CategoryId: 2,
      FavoritedUsers: [],
      isFavorited: false,
      FavoriteCount: 0,
    },
    {
      id: 21,
      name: "Bryon Braun",
      tel: "(000) 970-0498",
      address: "6169 Desiree Port",
      opening_hours: "08:00",
      description: "dolor et libero",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=83.66800292520114",
      viewCounts: 0,
      createdAt: "2021-11-10T13:02:01.000Z",
      updatedAt: "2021-11-10T13:02:01.000Z",
      CategoryId: 3,
      FavoritedUsers: [],
      isFavorited: false,
      FavoriteCount: 0,
    },
    {
      id: 27,
      name: "Augusta Konopelski",
      tel: "(857) 640-6422 x2450",
      address: "2016 Swaniawski Shore",
      opening_hours: "08:00",
      description: "Aut culpa minus nulla ut quisquam temporibus. Quam",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=14.893441751627211",
      viewCounts: 0,
      createdAt: "2021-11-10T13:02:01.000Z",
      updatedAt: "2021-11-10T13:02:01.000Z",
      CategoryId: 5,
      FavoritedUsers: [],
      isFavorited: false,
      FavoriteCount: 0,
    },
    {
      id: 28,
      name: "Elenora Zulauf",
      tel: "(140) 481-7894",
      address: "4320 Keshawn Tunnel",
      opening_hours: "08:00",
      description: "Reprehenderit dolores eveniet eos ut vel earum.\nUt",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=45.567704445096766",
      viewCounts: 0,
      createdAt: "2021-11-10T13:02:01.000Z",
      updatedAt: "2021-11-10T13:02:01.000Z",
      CategoryId: 1,
      FavoritedUsers: [],
      isFavorited: false,
      FavoriteCount: 0,
    },
    {
      id: 29,
      name: "Deshawn Halvorson",
      tel: "(477) 316-2724",
      address: "735 Mante Throughway",
      opening_hours: "08:00",
      description: "Magnam vitae enim sint. Omnis et atque rerum conse",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=14.437131178192564",
      viewCounts: 0,
      createdAt: "2021-11-10T13:02:01.000Z",
      updatedAt: "2021-11-10T13:02:01.000Z",
      CategoryId: 3,
      FavoritedUsers: [],
      isFavorited: false,
      FavoriteCount: 0,
    },
    {
      id: 30,
      name: "Alexis Barton DVM",
      tel: "435-595-6479",
      address: "11880 Crooks Locks",
      opening_hours: "08:00",
      description: "atque",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=98.15680208790394",
      viewCounts: 0,
      createdAt: "2021-11-10T13:02:01.000Z",
      updatedAt: "2021-11-10T13:02:01.000Z",
      CategoryId: 1,
      FavoritedUsers: [],
      isFavorited: false,
      FavoriteCount: 0,
    },
  ],
};
export default {
  components: {
    NavTabs,
    RestaurantTopCard,
  },
  data() {
    return {
      restaurants: [],
    };
  },
  created() {
    this.fetchRestaurantTop();
  },
  methods: {
    fetchRestaurantTop() {
      this.restaurants = dummyData.restaurants;
    },
  },
};
</script>