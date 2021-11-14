// ./src/views/Restaurants.vue
<template>
  <div class="container py-5">
    <!-- 使用 NavTabs 元件 -->
    <NavTabs />
    <h1 class="mt-5">首頁 - 餐廳列表</h1>
    <!-- 餐廳類別標籤 RestaurantsNavPills -->
    <RestaurantsNavPills :categories="categories" />

    <div class="row">
      <!-- 餐廳卡片 RestaurantCard-->
      <RestaurantCard
        v-for="restaurant in restaurants"
        :key="restaurant.id"
        :initial-restaurant="restaurant"
      />
    </div>

    <!-- 分頁標籤 RestaurantPagination -->
    <RestaurantsPagination
      v-if="totalPage.length > 1"
      :current-page="currentPage"
      :total-page="totalPage"
      :category-id="categoryId"
      :previous-page="previousPage"
      :next-page="nextPage"
    />
  </div>
</template>

<script>
import NavTabs from "./../components/NavTabs";
import RestaurantCard from "./../components/RestaurantCard";
import RestaurantsNavPills from "./../components/RestaurantsNavPills";
import RestaurantsPagination from "./../components/RestaurantsPagination";

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
      viewCounts: 0,
      createdAt: "2021-11-10T13:02:01.000Z",
      updatedAt: "2021-11-10T13:02:01.000Z",
      CategoryId: 3,
      Category: {
        id: 3,
        name: "義大利料理",
        createdAt: "2021-11-10T13:02:01.000Z",
        updatedAt: "2021-11-10T13:02:01.000Z",
      },
      isFavorited: false,
      isLiked: false,
    },
    {
      id: 2,
      name: "Holly O'Conner",
      tel: "(732) 195-3486 x87550",
      address: "1541 Constance Road",
      opening_hours: "08:00",
      description: "amet placeat officia",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=30.216075227332695",
      viewCounts: 0,
      createdAt: "2021-11-10T13:02:01.000Z",
      updatedAt: "2021-11-10T13:02:01.000Z",
      CategoryId: 1,
      Category: {
        id: 1,
        name: "中式料理",
        createdAt: "2021-11-10T13:02:01.000Z",
        updatedAt: "2021-11-10T13:02:01.000Z",
      },
      isFavorited: false,
      isLiked: false,
    },
    {
      id: 3,
      name: "Katlynn Dietrich",
      tel: "(507) 296-5911 x144",
      address: "43148 Kali Creek",
      opening_hours: "08:00",
      description: "Sit quo laborum consequatur.\nEarum assumenda cupid",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=99.95115505725171",
      viewCounts: 0,
      createdAt: "2021-11-10T13:02:01.000Z",
      updatedAt: "2021-11-10T13:02:01.000Z",
      CategoryId: 4,
      Category: {
        id: 4,
        name: "墨西哥料理",
        createdAt: "2021-11-10T13:02:01.000Z",
        updatedAt: "2021-11-10T13:02:01.000Z",
      },
      isFavorited: false,
      isLiked: false,
    },
    {
      id: 4,
      name: "Cassandre Gutkowski II",
      tel: "(570) 801-8721 x10498",
      address: "99609 Charlene Creek",
      opening_hours: "08:00",
      description: "Ea ut quaerat.",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=64.41334739737275",
      viewCounts: 0,
      createdAt: "2021-11-10T13:02:01.000Z",
      updatedAt: "2021-11-10T13:02:01.000Z",
      CategoryId: 3,
      Category: {
        id: 3,
        name: "義大利料理",
        createdAt: "2021-11-10T13:02:01.000Z",
        updatedAt: "2021-11-10T13:02:01.000Z",
      },
      isFavorited: false,
      isLiked: false,
    },
    {
      id: 5,
      name: "Helene Schoen II",
      tel: "750.062.3297 x167",
      address: "6469 Jodie Forge",
      opening_hours: "08:00",
      description: "placeat rem exercitationem",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=30.270034440302183",
      viewCounts: 0,
      createdAt: "2021-11-10T13:02:01.000Z",
      updatedAt: "2021-11-10T13:02:01.000Z",
      CategoryId: 3,
      Category: {
        id: 3,
        name: "義大利料理",
        createdAt: "2021-11-10T13:02:01.000Z",
        updatedAt: "2021-11-10T13:02:01.000Z",
      },
      isFavorited: false,
      isLiked: false,
    },
    {
      id: 6,
      name: "Mr. Kelton Hyatt",
      tel: "241-030-3054 x3634",
      address: "3397 Ondricka Squares",
      opening_hours: "08:00",
      description: "Blanditiis ut corrupti quam laboriosam sit. Earum ",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=81.44774932110398",
      viewCounts: 0,
      createdAt: "2021-11-10T13:02:01.000Z",
      updatedAt: "2021-11-10T13:02:01.000Z",
      CategoryId: 3,
      Category: {
        id: 3,
        name: "義大利料理",
        createdAt: "2021-11-10T13:02:01.000Z",
        updatedAt: "2021-11-10T13:02:01.000Z",
      },
      isFavorited: false,
      isLiked: false,
    },
    {
      id: 7,
      name: "Derrick Roob",
      tel: "905-470-3998",
      address: "07618 Ned Squares",
      opening_hours: "08:00",
      description: "Rerum maiores dolorem est laboriosam. Quibusdam bl",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=48.23233195184089",
      viewCounts: 0,
      createdAt: "2021-11-10T13:02:01.000Z",
      updatedAt: "2021-11-10T13:02:01.000Z",
      CategoryId: 4,
      Category: {
        id: 4,
        name: "墨西哥料理",
        createdAt: "2021-11-10T13:02:01.000Z",
        updatedAt: "2021-11-10T13:02:01.000Z",
      },
      isFavorited: false,
      isLiked: false,
    },
    {
      id: 8,
      name: "Audreanne Maggio",
      tel: "1-888-211-8136 x9788",
      address: "5280 Axel Rapids",
      opening_hours: "08:00",
      description: "Qui soluta ad et ab quae qui qui labore autem. Aut",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=56.811438213360454",
      viewCounts: 0,
      createdAt: "2021-11-10T13:02:01.000Z",
      updatedAt: "2021-11-10T13:02:01.000Z",
      CategoryId: 4,
      Category: {
        id: 4,
        name: "墨西哥料理",
        createdAt: "2021-11-10T13:02:01.000Z",
        updatedAt: "2021-11-10T13:02:01.000Z",
      },
      isFavorited: false,
      isLiked: false,
    },
    {
      id: 9,
      name: "Josie Deckow",
      tel: "1-909-694-3470",
      address: "496 Diego Meadow",
      opening_hours: "08:00",
      description: "Est autem eaque sit dignissimos.",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=64.22676402510254",
      viewCounts: 0,
      createdAt: "2021-11-10T13:02:01.000Z",
      updatedAt: "2021-11-10T13:02:01.000Z",
      CategoryId: 1,
      Category: {
        id: 1,
        name: "中式料理",
        createdAt: "2021-11-10T13:02:01.000Z",
        updatedAt: "2021-11-10T13:02:01.000Z",
      },
      isFavorited: false,
      isLiked: false,
    },
    {
      id: 10,
      name: "Jefferey Koss",
      tel: "657.320.7941",
      address: "2740 Ritchie Hill",
      opening_hours: "08:00",
      description: "In saepe ullam delectus ut in a enim qui.",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=62.469816981766215",
      viewCounts: 0,
      createdAt: "2021-11-10T13:02:01.000Z",
      updatedAt: "2021-11-10T13:02:01.000Z",
      CategoryId: 2,
      Category: {
        id: 2,
        name: "日本料理",
        createdAt: "2021-11-10T13:02:01.000Z",
        updatedAt: "2021-11-10T13:02:01.000Z",
      },
      isFavorited: false,
      isLiked: false,
    },
  ],
  categories: [
    {
      id: 1,
      name: "中式料理",
      createdAt: "2021-11-10T13:02:01.000Z",
      updatedAt: "2021-11-10T13:02:01.000Z",
    },
    {
      id: 2,
      name: "日本料理",
      createdAt: "2021-11-10T13:02:01.000Z",
      updatedAt: "2021-11-10T13:02:01.000Z",
    },
    {
      id: 3,
      name: "義大利料理",
      createdAt: "2021-11-10T13:02:01.000Z",
      updatedAt: "2021-11-10T13:02:01.000Z",
    },
    {
      id: 4,
      name: "墨西哥料理",
      createdAt: "2021-11-10T13:02:01.000Z",
      updatedAt: "2021-11-10T13:02:01.000Z",
    },
    {
      id: 5,
      name: "素食料理",
      createdAt: "2021-11-10T13:02:01.000Z",
      updatedAt: "2021-11-10T13:02:01.000Z",
    },
    {
      id: 6,
      name: "美式料理",
      createdAt: "2021-11-10T13:02:01.000Z",
      updatedAt: "2021-11-10T13:02:01.000Z",
    },
    {
      id: 7,
      name: "複合式料理",
      createdAt: "2021-11-10T13:02:01.000Z",
      updatedAt: "2021-11-10T13:02:01.000Z",
    },
  ],
  categoryId: "",
  page: 1,
  totalPage: [1, 2, 3, 4, 5],
  prev: 1,
  next: 2,
};
export default {
  components: {
    NavTabs,
    RestaurantCard,
    RestaurantsNavPills,
    RestaurantsPagination,
  },
  data() {
    return {
      restaurants: [],
      categories: [],
      categoryId: -1,
      currentPage: 1,
      totalPage: [],
      previousPage: -1,
      nextPage: -1,
    };
  },
  created() {
    this.fetchRestaurants();
  },
  methods: {
    fetchRestaurants() {
      const {
        restaurants,
        categories,
        categoryId,
        page,
        totalPage,
        prev,
        next,
      } = dummyData;

      this.restaurants = restaurants;
      this.categories = categories;
      this.categoryId = categoryId;
      this.page = page;
      this.totalPage = totalPage;
      this.previousPage = prev;
      this.nextPage = next;
    },
  },
};
</script>