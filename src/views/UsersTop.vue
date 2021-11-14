// ./src/views/UsersTop.vue
<template>
  <div class="container py-5">
    <!-- 使用 NavTabs 元件 -->
    <NavTabs />
    <h1 class="mt-5">美食達人</h1>
    <div class="row text-center">
      <UserTop v-for="user in users" :key="user.id" :initial-user="user" />
    </div>
  </div>
</template>

<script>
import NavTabs from "./../components/NavTabs";
import UserTop from "./../components/UserTop";

const dummyData = {
  users: [
    {
      id: 1,
      name: "root",
      email: "root@example.com",
      password: "$2a$10$8IVLT/Wm3Rl4mR8/FSt78.chL8PDcbUn.oISGJdQMXUP47SjRCEWK",
      isAdmin: true,
      image: null,
      createdAt: "2021-11-10T13:02:01.000Z",
      updatedAt: "2021-11-10T13:02:01.000Z",
      Followers: [],
      FollowerCount: 0,
      isFollowed: false,
    },
    {
      id: 2,
      name: "user1",
      email: "user1@example.com",
      password: "$2a$10$oenC2krq8RWeAj8yr5e.Ou5sOUA30HLpOvsyD7e8IPVPn.w51fS.y",
      isAdmin: false,
      image: null,
      createdAt: "2021-11-10T13:02:01.000Z",
      updatedAt: "2021-11-10T13:02:01.000Z",
      Followers: [],
      FollowerCount: 0,
      isFollowed: false,
    },
    {
      id: 3,
      name: "user2",
      email: "user2@example.com",
      password: "$2a$10$PDGaJsrWdYhTcPjAbuK2Bevl0yCku9mT9EV8Aj.WW9BmHwUrmx.qO",
      isAdmin: false,
      image: null,
      createdAt: "2021-11-10T13:02:01.000Z",
      updatedAt: "2021-11-10T13:02:01.000Z",
      Followers: [],
      FollowerCount: 0,
      isFollowed: false,
    },
  ],
};
export default {
  components: {
    NavTabs,
    UserTop,
  },
  data() {
    return {
      users: [],
    };
  },
  created() {
    this.fetchUsersTop();
  },
  methods: {
    fetchUsersTop() {
      this.users = dummyData.users;
    },
  },
};
</script>