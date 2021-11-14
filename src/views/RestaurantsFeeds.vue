// ./src/views/RestaurantsFeeds.vue
<template>
  <div class="container py-5">
    <!-- 使用 NavTabs 元件 -->
    <NavTabs />
    <h1 class="mt-5">最新動態</h1>
    <hr />
    <div class="row">
      <div class="col-md-6">
        <h3>最新餐廳</h3>
        <!-- 最新餐廳 NewestRestaurants -->
        <NewestRestaurants :restaurants="restaurants" />
      </div>
      <div class="col-md-6">
        <!-- 最新評論 NewestComments-->
        <h3>最新評論</h3>
        <NewestComments :comments="comments" />
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
      id: 31,
      name: "Earnest Corkery",
      tel: "(734) 938-3476 x65860",
      address: "9675 Heidenreich Ranch",
      opening_hours: "08:00",
      description: "Aliquid distinctio quia odit non architecto.",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=6.7610716802245285",
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
    },
    {
      id: 36,
      name: "Mrs. Elza Bradtke",
      tel: "1-985-332-8635",
      address: "649 Viola Fords",
      opening_hours: "08:00",
      description: "Eveniet ex dolores consequatur.",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=58.366877842888165",
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
    },
    {
      id: 16,
      name: "Cassie Beatty DDS",
      tel: "1-193-573-5620",
      address: "16351 Gusikowski Land",
      opening_hours: "08:00",
      description:
        "Aperiam sed cum quod. Eaque voluptatem rerum odio numquam labore est. Animi dolorem cum ut expedita quo tempore. Maxime aliquam dolorem aut hic dolores nam deleniti aliquid. Ut blanditiis quas.",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=91.94554118588918",
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
    },
    {
      id: 41,
      name: "Kody Ryan",
      tel: "989-805-6446",
      address: "2500 Kertzmann Views",
      opening_hours: "08:00",
      description: "dolor nemo et",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=99.68645148232437",
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
    },
    {
      id: 11,
      name: "Andrew Balistreri",
      tel: "251-264-3639 x34474",
      address: "22528 Klocko Fall",
      opening_hours: "08:00",
      description: "Tempore laboriosam nisi ad aut temporibus et ut in.",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=31.208632240246438",
      viewCounts: 0,
      createdAt: "2021-11-10T13:02:01.000Z",
      updatedAt: "2021-11-10T13:02:01.000Z",
      CategoryId: 5,
      Category: {
        id: 5,
        name: "素食料理",
        createdAt: "2021-11-10T13:02:01.000Z",
        updatedAt: "2021-11-10T13:02:01.000Z",
      },
    },
    {
      id: 42,
      name: "Mr. Morton Morar",
      tel: "(849) 104-3949",
      address: "799 Marge Underpass",
      opening_hours: "08:00",
      description:
        "Placeat deleniti dolorem rem officia et aut. Eum voluptatem reiciendis aut voluptas. Pariatur voluptatum sint sit sit qui cum est laborum.\n \rVoluptatem officia est ipsam. Quo autem nisi ipsum exercitationem laborum perferendis porro ab esse. Esse temporibus molestias quia corporis voluptas.\n \rVeniam dicta amet laboriosam iure dolore doloribus aliquam rerum. Exercitationem eos consequatur repellendus optio nam soluta sint. Nisi cumque voluptatem delectus rerum et dolorum aut. Consequatur aut fugit sapiente voluptatum quod non iure. Suscipit eum assumenda. Nemo cumque unde nulla mollitia voluptatem amet tempore nihil.",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=41.79375154947087",
      viewCounts: 0,
      createdAt: "2021-11-10T13:02:01.000Z",
      updatedAt: "2021-11-10T13:02:01.000Z",
      CategoryId: 5,
      Category: {
        id: 5,
        name: "素食料理",
        createdAt: "2021-11-10T13:02:01.000Z",
        updatedAt: "2021-11-10T13:02:01.000Z",
      },
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
    },
    {
      id: 32,
      name: "Josiah Kulas",
      tel: "1-299-427-3607 x8764",
      address: "295 Lorenzo Lock",
      opening_hours: "08:00",
      description:
        "Enim consequuntur qui laborum.\nSit distinctio qui.\nNobis repellendus magnam voluptatem quia ut architecto explicabo ullam praesentium.\nNostrum voluptatem dolores omnis quia voluptatem et aliquam excepturi.\nEt quod consectetur.",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=66.46285796455867",
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
    },
    {
      id: 38,
      name: "Jamal Denesik III",
      tel: "884.265.0087 x63163",
      address: "078 Loyce Corners",
      opening_hours: "08:00",
      description: "magni",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=86.54273299546004",
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
      Category: {
        id: 3,
        name: "義大利料理",
        createdAt: "2021-11-10T13:02:01.000Z",
        updatedAt: "2021-11-10T13:02:01.000Z",
      },
    },
  ],
  comments: [
    {
      id: 11,
      text: "Sit ut tempore.",
      UserId: 1,
      RestaurantId: 11,
      createdAt: "2021-11-10T13:02:01.000Z",
      updatedAt: "2021-11-10T13:02:01.000Z",
      User: {
        id: 1,
        name: "root",
        email: "root@example.com",
        password:
          "$2a$10$8IVLT/Wm3Rl4mR8/FSt78.chL8PDcbUn.oISGJdQMXUP47SjRCEWK",
        isAdmin: true,
        image: null,
        createdAt: "2021-11-10T13:02:01.000Z",
        updatedAt: "2021-11-10T13:02:01.000Z",
      },
      Restaurant: {
        id: 11,
        name: "Andrew Balistreri",
        tel: "251-264-3639 x34474",
        address: "22528 Klocko Fall",
        opening_hours: "08:00",
        description: "Tempore laboriosam nisi ad aut temporibus et ut in.",
        image:
          "https://loremflickr.com/320/240/restaurant,food/?random=31.208632240246438",
        viewCounts: 0,
        createdAt: "2021-11-10T13:02:01.000Z",
        updatedAt: "2021-11-10T13:02:01.000Z",
        CategoryId: 5,
      },
    },
    {
      id: 30,
      text: "Et occaecati repellendus.",
      UserId: 1,
      RestaurantId: 30,
      createdAt: "2021-11-10T13:02:01.000Z",
      updatedAt: "2021-11-10T13:02:01.000Z",
      User: {
        id: 1,
        name: "root",
        email: "root@example.com",
        password:
          "$2a$10$8IVLT/Wm3Rl4mR8/FSt78.chL8PDcbUn.oISGJdQMXUP47SjRCEWK",
        isAdmin: true,
        image: null,
        createdAt: "2021-11-10T13:02:01.000Z",
        updatedAt: "2021-11-10T13:02:01.000Z",
      },
      Restaurant: {
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
      },
    },
    {
      id: 56,
      text: "Qui exercitationem aspernatur est animi.",
      UserId: 1,
      RestaurantId: 6,
      createdAt: "2021-11-10T13:02:01.000Z",
      updatedAt: "2021-11-10T13:02:01.000Z",
      User: {
        id: 1,
        name: "root",
        email: "root@example.com",
        password:
          "$2a$10$8IVLT/Wm3Rl4mR8/FSt78.chL8PDcbUn.oISGJdQMXUP47SjRCEWK",
        isAdmin: true,
        image: null,
        createdAt: "2021-11-10T13:02:01.000Z",
        updatedAt: "2021-11-10T13:02:01.000Z",
      },
      Restaurant: {
        id: 6,
        name: "Mr. Kelton Hyatt",
        tel: "241-030-3054 x3634",
        address: "3397 Ondricka Squares",
        opening_hours: "08:00",
        description:
          "Blanditiis ut corrupti quam laboriosam sit. Earum modi non molestiae et optio blanditiis. Voluptatem nostrum expedita ipsam sunt sed dignissimos. Ut velit ad ut tempora eum laborum rerum eligendi vitae. Iusto consequuntur ipsum impedit nemo quam nesciunt in. Autem blanditiis sequi illo ut sint natus.",
        image:
          "https://loremflickr.com/320/240/restaurant,food/?random=81.44774932110398",
        viewCounts: 0,
        createdAt: "2021-11-10T13:02:01.000Z",
        updatedAt: "2021-11-10T13:02:01.000Z",
        CategoryId: 3,
      },
    },
    {
      id: 81,
      text: "Magnam rerum voluptas dolorem.",
      UserId: 1,
      RestaurantId: 31,
      createdAt: "2021-11-10T13:02:01.000Z",
      updatedAt: "2021-11-10T13:02:01.000Z",
      User: {
        id: 1,
        name: "root",
        email: "root@example.com",
        password:
          "$2a$10$8IVLT/Wm3Rl4mR8/FSt78.chL8PDcbUn.oISGJdQMXUP47SjRCEWK",
        isAdmin: true,
        image: null,
        createdAt: "2021-11-10T13:02:01.000Z",
        updatedAt: "2021-11-10T13:02:01.000Z",
      },
      Restaurant: {
        id: 31,
        name: "Earnest Corkery",
        tel: "(734) 938-3476 x65860",
        address: "9675 Heidenreich Ranch",
        opening_hours: "08:00",
        description: "Aliquid distinctio quia odit non architecto.",
        image:
          "https://loremflickr.com/320/240/restaurant,food/?random=6.7610716802245285",
        viewCounts: 0,
        createdAt: "2021-11-10T13:02:01.000Z",
        updatedAt: "2021-11-10T13:02:01.000Z",
        CategoryId: 1,
      },
    },
    {
      id: 104,
      text: "Quis ut voluptatem.",
      UserId: 1,
      RestaurantId: 4,
      createdAt: "2021-11-10T13:02:01.000Z",
      updatedAt: "2021-11-10T13:02:01.000Z",
      User: {
        id: 1,
        name: "root",
        email: "root@example.com",
        password:
          "$2a$10$8IVLT/Wm3Rl4mR8/FSt78.chL8PDcbUn.oISGJdQMXUP47SjRCEWK",
        isAdmin: true,
        image: null,
        createdAt: "2021-11-10T13:02:01.000Z",
        updatedAt: "2021-11-10T13:02:01.000Z",
      },
      Restaurant: {
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
      },
    },
    {
      id: 120,
      text: "Id accusamus impedit quidem.",
      UserId: 1,
      RestaurantId: 20,
      createdAt: "2021-11-10T13:02:01.000Z",
      updatedAt: "2021-11-10T13:02:01.000Z",
      User: {
        id: 1,
        name: "root",
        email: "root@example.com",
        password:
          "$2a$10$8IVLT/Wm3Rl4mR8/FSt78.chL8PDcbUn.oISGJdQMXUP47SjRCEWK",
        isAdmin: true,
        image: null,
        createdAt: "2021-11-10T13:02:01.000Z",
        updatedAt: "2021-11-10T13:02:01.000Z",
      },
      Restaurant: {
        id: 20,
        name: "Fredy Davis",
        tel: "1-701-243-0379 x1761",
        address: "53546 Rempel Rest",
        opening_hours: "08:00",
        description:
          "Sed maiores minus. Reiciendis itaque eum ipsam iusto aspernatur quaerat. Qui qui et quam ad aut laboriosam aliquid.",
        image:
          "https://loremflickr.com/320/240/restaurant,food/?random=25.463163315411606",
        viewCounts: 0,
        createdAt: "2021-11-10T13:02:01.000Z",
        updatedAt: "2021-11-10T13:02:01.000Z",
        CategoryId: 5,
      },
    },
    {
      id: 146,
      text: "Id voluptas cumque animi sint quia voluptatem voluptatum.",
      UserId: 1,
      RestaurantId: 46,
      createdAt: "2021-11-10T13:02:01.000Z",
      updatedAt: "2021-11-10T13:02:01.000Z",
      User: {
        id: 1,
        name: "root",
        email: "root@example.com",
        password:
          "$2a$10$8IVLT/Wm3Rl4mR8/FSt78.chL8PDcbUn.oISGJdQMXUP47SjRCEWK",
        isAdmin: true,
        image: null,
        createdAt: "2021-11-10T13:02:01.000Z",
        updatedAt: "2021-11-10T13:02:01.000Z",
      },
      Restaurant: {
        id: 46,
        name: "Benedict Rolfson",
        tel: "155.645.5618",
        address: "63745 Jameson Coves",
        opening_hours: "08:00",
        description:
          "Est rerum fugit quia. Est fugiat sit dolores voluptatem et. Rerum at magnam. Neque nemo corrupti qui. At eius vitae corporis maiores excepturi ullam. Quas ut aut et molestiae enim dolores laudantium.\n \rQuo quibusdam blanditiis fuga sunt. Occaecati quas et in. Suscipit accusantium porro ut sint. Voluptatibus alias aliquid repellendus eos pariatur temporibus id aliquam. Dolor sed laudantium harum. Doloribus vitae repudiandae.\n \rVel et ut natus iste qui dolor. Ad assumenda numquam distinctio harum. Cum ducimus voluptatem doloribus dolor omnis mollitia repellat mollitia.",
        image:
          "https://loremflickr.com/320/240/restaurant,food/?random=43.89738534438874",
        viewCounts: 0,
        createdAt: "2021-11-10T13:02:01.000Z",
        updatedAt: "2021-11-10T13:02:01.000Z",
        CategoryId: 1,
      },
    },
    {
      id: 13,
      text: "Consequatur sed iste ab voluptas.",
      UserId: 2,
      RestaurantId: 13,
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
      Restaurant: {
        id: 13,
        name: "Mrs. Mckayla Kunze",
        tel: "583.159.4201 x19790",
        address: "0085 Kallie Falls",
        opening_hours: "08:00",
        description:
          "Sit tenetur magni consequatur dolorum. Quia et magni libero vitae. Est voluptatem sit eius. Qui qui quam. Quaerat qui exercitationem. Dolores eum ad ducimus voluptatem ullam et non.\n \rFugiat nobis omnis ipsa nisi. Nihil laboriosam aut quasi tempore delectus rem. Aut qui eaque similique ab odio sunt. Vel eum eum aut amet aperiam corrupti ratione. Corporis non voluptas ut tempora aliquid.\n \rDeserunt omnis aperiam qui consequatur ex. Quo porro voluptatem in distinctio quos eos ratione vitae. Itaque ut et ut. Mollitia doloribus ipsum nulla. Aliquid dolores expedita. Tempore dolor sint fugiat magni mollitia voluptatem.",
        image:
          "https://loremflickr.com/320/240/restaurant,food/?random=37.530268243076726",
        viewCounts: 0,
        createdAt: "2021-11-10T13:02:01.000Z",
        updatedAt: "2021-11-10T13:02:01.000Z",
        CategoryId: 1,
      },
    },
    {
      id: 38,
      text: "At aut repudiandae enim unde quo.",
      UserId: 2,
      RestaurantId: 38,
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
      Restaurant: {
        id: 38,
        name: "Jamal Denesik III",
        tel: "884.265.0087 x63163",
        address: "078 Loyce Corners",
        opening_hours: "08:00",
        description: "magni",
        image:
          "https://loremflickr.com/320/240/restaurant,food/?random=86.54273299546004",
        viewCounts: 0,
        createdAt: "2021-11-10T13:02:01.000Z",
        updatedAt: "2021-11-10T13:02:01.000Z",
        CategoryId: 2,
      },
    },
    {
      id: 61,
      text: "Illum non non omnis debitis dignissimos quasi possimus illo provident.",
      UserId: 2,
      RestaurantId: 11,
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
      Restaurant: {
        id: 11,
        name: "Andrew Balistreri",
        tel: "251-264-3639 x34474",
        address: "22528 Klocko Fall",
        opening_hours: "08:00",
        description: "Tempore laboriosam nisi ad aut temporibus et ut in.",
        image:
          "https://loremflickr.com/320/240/restaurant,food/?random=31.208632240246438",
        viewCounts: 0,
        createdAt: "2021-11-10T13:02:01.000Z",
        updatedAt: "2021-11-10T13:02:01.000Z",
        CategoryId: 5,
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
      this.comments = dummyData.comments.filter(
        (comment) => comment.Restaurant && comment.text
      );
    },
  },
};
</script>