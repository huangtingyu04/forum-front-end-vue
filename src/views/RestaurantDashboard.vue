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
      <li>評論數： {{ restaurant.commentsLength }} }</li>
      <li>瀏覽次數： {{ restaurant.viewCounts }} }</li>
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
    name: "Norwood Wehner Jr.",
    tel: "463.606.9752",
    address: "95284 Vernice Crossroad",
    opening_hours: "08:00",
    description:
      "Rerum dolor aliquam sapiente alias vel ipsa est sed ratione. Tenetur sed facere amet eligendi quia. Soluta rerum eius dolor rerum. Quia deserunt quia rerum iste laboriosam odit ea fugit. Tempora cupiditate reiciendis tenetur.",
    image:
      "https://loremflickr.com/320/240/restaurant,food/?random=15.319122876392854",
    viewCounts: 1,
    createdAt: "2021-11-10T13:02:01.000Z",
    updatedAt: "2021-11-14T02:27:04.000Z",
    CategoryId: 3,
    Category: {
      id: 3,
      name: "義大利料理",
      createdAt: "2021-11-10T13:02:01.000Z",
      updatedAt: "2021-11-10T13:02:01.000Z",
    },
    Comments: [
      {
        id: 1,
        text: "Non enim ratione assumenda quam veniam quod consectetur eos quia.",
        UserId: 2,
        RestaurantId: 1,
        createdAt: "2021-11-10T13:02:01.000Z",
        updatedAt: "2021-11-10T13:02:01.000Z",
        User: {
          id: 2,
          name: "user1",
          email: "user1@example.com",
          password:
            "$2a$10$oenC2krq8RWeAj8yr5e.Ou5sOUA30HLpOvsyD7e8IPVPn.w51fS.y",
          isAdmin: false,
          image: null,
          createdAt: "2021-11-10T13:02:01.000Z",
          updatedAt: "2021-11-10T13:02:01.000Z",
        },
      },
      {
        id: 51,
        text: "Repellat eum quia.",
        UserId: 3,
        RestaurantId: 1,
        createdAt: "2021-11-10T13:02:01.000Z",
        updatedAt: "2021-11-10T13:02:01.000Z",
        User: {
          id: 3,
          name: "user2",
          email: "user2@example.com",
          password:
            "$2a$10$PDGaJsrWdYhTcPjAbuK2Bevl0yCku9mT9EV8Aj.WW9BmHwUrmx.qO",
          isAdmin: false,
          image: null,
          createdAt: "2021-11-10T13:02:01.000Z",
          updatedAt: "2021-11-10T13:02:01.000Z",
        },
      },
      {
        id: 101,
        text: "Nobis sed id.",
        UserId: 3,
        RestaurantId: 1,
        createdAt: "2021-11-10T13:02:01.000Z",
        updatedAt: "2021-11-10T13:02:01.000Z",
        User: {
          id: 3,
          name: "user2",
          email: "user2@example.com",
          password:
            "$2a$10$PDGaJsrWdYhTcPjAbuK2Bevl0yCku9mT9EV8Aj.WW9BmHwUrmx.qO",
          isAdmin: false,
          image: null,
          createdAt: "2021-11-10T13:02:01.000Z",
          updatedAt: "2021-11-10T13:02:01.000Z",
        },
      },
    ],
  },
};
export default {
  data() {
    return {
      restaurant: {
        id: -1,
        name: "",
        categoryName: "",
        commentsLength: 0,
        viewCounts: 0,
      },
    };
  },
  created() {
    const { id: restaurantId } = this.$route.params;
    this.fetchRestaurantDashboard(restaurantId);
  },
  methods: {
    fetchRestaurantDashboard(restaurantId) {
      console.log("fetchRestaurantDashboard id: ", restaurantId);
      const { id, name, Category, Comments, viewCounts } = dummyData.restaurant;
      this.restaurant = {
        ...this.restaurant,
        id,
        name,
        categoryName: Category ? Category.name : "未分類",
        commentsLength: Comments.length,
        viewCounts,
      };
    },
  },
};
</script>