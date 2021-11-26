<template>
  <div class="container py-5">
    <form @submit.stop.prevent="handleSubmit">
      <div class="form-group">
        <label for="name">Name</label>
        <input
          id="name"
          v-model="name"
          type="text"
          name="name"
          class="form-control"
          placeholder="Enter Name"
          required
        />
      </div>

      <div class="form-group">
        <label for="image">Image</label>
        <img
          v-if="image"
          :src="image"
          class="d-block img-thumbnail mb-3"
          width="200"
          height="200"
        />

        <input
          id="image"
          type="file"
          name="image"
          accept="image/*"
          class="form-control-file"
          @change="handleFileChange"
        />
      </div>

      <button type="submit" class="btn btn-primary">Submit</button>
    </form>
  </div>
</template>

<script>
const dummyData = {
  currentUser: {
    id: 1,
    image: "",
    name: "root",
    email: "root@example.com",
  },
};
export default {
  data() {
    return {
      id: 0,
      image: "",
      name: "",
      email: "",
    };
  },
  created() {
    const { id } = this.$route.params;
    this.setUser(id);
  },
  methods: {
    setUser() {
      const { id, image, name, email } = dummyData.currentUser;
      this.id = id;
      this.name = name;
      this.email = email;
      this.image = image;
    },
    handleFileChange(e) {
      const files = e.target.files;
      if (!files.length) return;
      const imageURL = window.URL.createObjectURL(files[0]);
      this.image = imageURL;
    },
    handleSubmit(e) {
      const form = e.target; // <form></form>
      const formData = new FormData(form);
      this.$emit("after-submit", formData);
    },
  },
};
</script>