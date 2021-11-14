// ./src/views/UsersTop.vue
<template>
  <div class="col-3">
    <a href="#">
      <img
        src="http://via.placeholder.com/300x300?text=No+Image"
        width="140px"
        height="140px"
      />
    </a>
    <h2>{{ user.name }}</h2>
    <span class="badge badge-secondary"
      >追蹤人數：{{ user.FollowerCount }}</span
    >
    <p class="mt-3">
      <template v-if="user.isFollowed">
        <button
          type="button"
          class="btn btn-danger"
          @click.stop.prevent="deleteFollow"
        >
          取消追蹤
        </button>
      </template>
      <template v-else>
        <button
          type="button"
          class="btn btn-primary"
          @click.stop.prevent="addFollow"
        >
          追蹤
        </button>
      </template>
    </p>
  </div>
</template>

<script>
export default {
  props: {
    initialUser: {
      type: Object,
      required: true,
    },
  },
  data() {
    return {
      user: this.initialUser,
    };
  },
  methods: {
    addFollow() {
      this.user = {
        ...this.user,
        isFollowed: true,
      };
    },
    deleteFollow() {
      this.user = {
        ...this.user,
        isFollowed: false,
      };
    },
  },
};
</script>