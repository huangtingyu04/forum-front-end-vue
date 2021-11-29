<template>
  <div class="container py-5">
    <h1>餐廳描述頁</h1>
    <!-- 餐廳資訊頁 RestaurantDetail -->
    <RestaurantDetail :initial-restaurant="restaurant" />
    <hr />
    <!-- 餐廳評論 RestaurantComments -->
    <RestaurantComments
      :restaurant-comments="restaurantComments"
      @after-delete-comment="afterDeleteComment"
    />
    <!-- 新增評論 CreateComment -->
    <CreateComment
      :restaurant-id="restaurant.id"
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
    updatedAt: "2021-11-14T02:27:04.267Z",
    CategoryId: 3,
    Category: {
      id: 3,
      name: "義大利料理",
      createdAt: "2021-11-10T13:02:01.000Z",
      updatedAt: "2021-11-10T13:02:01.000Z",
    },
    FavoritedUsers: [],
    LikedUsers: [],
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
  isFavorited: false,
  isLiked: false,
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
        categoryName: dummyData.restaurant.Category.name
          ? dummyData.restaurant.Category.name
          : "未分類",
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
