// ./src/components/AdminRestaurantsTable.vue
<template>
  <table class="table">
    <thead class="thead-dark">
      <tr>
        <th scope="col">#</th>
        <th scope="col">Category</th>
        <th scope="col">Name</th>
        <th scope="col" width="300">操作</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="restaurant in restaurants" :key="restaurant.id">
        <th scope="row">
          {{ restaurant.id }}
        </th>
        <td>{{ restaurant.Category ? restaurant.Category.name : "未分類" }}</td>
        <td>{{ restaurant.name }}</td>
        <td class="d-flex justify-content-between">
          <router-link
            :to="{ name: 'admin-restaurant', params: { id: restaurant.id } }"
            class="btn btn-link"
            >Show</router-link
          >

          <router-link
            :to="{
              name: 'admin-restaurant-edit',
              params: {
                id: restaurant.id,
              },
            }"
            class="btn btn-link"
          >
            Edit
          </router-link>

          <button
            type="button"
            class="btn btn-link"
            @click.stop.prevent="deleteRestaurant(restaurant.id)"
          >
            Delete
          </button>
        </td>
      </tr>
    </tbody>
  </table>
</template>

<script>
const dummyData = {
  restaurants: [
    {
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
      id: 3,
      name: "Katlynn Dietrich",
      tel: "(507) 296-5911 x144",
      address: "43148 Kali Creek",
      opening_hours: "08:00",
      description:
        "Sit quo laborum consequatur.\nEarum assumenda cupiditate quaerat consequuntur.\nNihil facilis rem quis aut aliquam reprehenderit ut.\nEst repellat tenetur explicabo.",
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
    },
    {
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
      Category: {
        id: 3,
        name: "義大利料理",
        createdAt: "2021-11-10T13:02:01.000Z",
        updatedAt: "2021-11-10T13:02:01.000Z",
      },
    },
    {
      id: 7,
      name: "Derrick Roob",
      tel: "905-470-3998",
      address: "07618 Ned Squares",
      opening_hours: "08:00",
      description:
        "Rerum maiores dolorem est laboriosam. Quibusdam blanditiis aut voluptas corrupti occaecati ipsam assumenda.",
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
    },
    {
      id: 8,
      name: "Audreanne Maggio",
      tel: "1-888-211-8136 x9788",
      address: "5280 Axel Rapids",
      opening_hours: "08:00",
      description:
        "Qui soluta ad et ab quae qui qui labore autem. Aut sed omnis. Culpa animi nesciunt est ut facilis autem eligendi. Esse beatae quia consequatur dolor. Sed necessitatibus id et et.",
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
      id: 12,
      name: "Torrey Osinski",
      tel: "515.958.0450 x49878",
      address: "135 Walker Pike",
      opening_hours: "08:00",
      description: "qui",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=8.089059088400097",
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
      Category: {
        id: 1,
        name: "中式料理",
        createdAt: "2021-11-10T13:02:01.000Z",
        updatedAt: "2021-11-10T13:02:01.000Z",
      },
    },
    {
      id: 14,
      name: "Mauricio Barton",
      tel: "(105) 902-3624 x202",
      address: "6846 Clement Camp",
      opening_hours: "08:00",
      description:
        "Doloribus qui placeat deserunt nobis et iure ratione placeat. Dolorem sed ipsam mollitia culpa omnis. Ipsam assumenda nam quis. Aut quidem sed ab voluptatum magni facere. Sint velit assumenda error natus et quidem voluptatem.\n \rQuam est voluptatibus adipisci. Modi odio aliquam aut placeat quis ratione. Labore autem ut. Sit perspiciatis unde. Velit neque consequatur.\n \rNatus asperiores odio libero deserunt. Quo et fugiat accusamus molestiae sit nemo voluptatem inventore quia. Reprehenderit ut rerum pariatur voluptatem deleniti. Omnis dolor harum soluta vel molestiae sint aut vero.",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=82.90244539266776",
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
      id: 15,
      name: "Viola Schmeler",
      tel: "(847) 665-8666 x50500",
      address: "56557 Kody Island",
      opening_hours: "08:00",
      description:
        "Sit sunt ducimus autem qui minus magni aut fugit ea. Ratione non ut facilis delectus in commodi. Deleniti amet vitae quia maxime culpa et. Deserunt et ea et neque culpa.",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=38.29279283260052",
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
      id: 17,
      name: "Sterling Wiza",
      tel: "157.064.1698",
      address: "0494 Grimes Island",
      opening_hours: "08:00",
      description: "sed",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=33.68827408668851",
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
      id: 18,
      name: "Mr. Sam Farrell",
      tel: "976.374.9328 x1209",
      address: "6601 Kayden Port",
      opening_hours: "08:00",
      description: "Nobis sed saepe. Quam omnis rerum.",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=91.17427642417026",
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
      id: 19,
      name: "Jameson Hilpert",
      tel: "669-941-2319 x40598",
      address: "20556 Kovacek Hollow",
      opening_hours: "08:00",
      description:
        "Porro dolores occaecati quibusdam numquam non quae quas minus consequatur.",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=90.1296018784935",
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
      Category: {
        id: 5,
        name: "素食料理",
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
    {
      id: 22,
      name: "Sonia Stracke",
      tel: "(304) 125-8622",
      address: "3554 Baumbach Rapids",
      opening_hours: "08:00",
      description:
        "Culpa dicta ipsa voluptates sit. Consequatur omnis nihil occaecati. Omnis eum libero qui.",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=38.752619355345175",
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
      Category: {
        id: 4,
        name: "墨西哥料理",
        createdAt: "2021-11-10T13:02:01.000Z",
        updatedAt: "2021-11-10T13:02:01.000Z",
      },
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
      Category: {
        id: 1,
        name: "中式料理",
        createdAt: "2021-11-10T13:02:01.000Z",
        updatedAt: "2021-11-10T13:02:01.000Z",
      },
    },
    {
      id: 25,
      name: "Alexandria Mills",
      tel: "1-644-841-9837 x4319",
      address: "14443 Reichel Unions",
      opening_hours: "08:00",
      description:
        "Velit delectus optio quam corporis dolorem. Sunt blanditiis atque. Veritatis laudantium possimus. Sunt nesciunt corrupti explicabo veritatis. Repellendus et voluptatem officiis soluta deleniti ex iste. Vitae impedit est itaque accusantium repellendus voluptatem est.",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=81.99054350862407",
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
      id: 26,
      name: "Casandra Harber",
      tel: "231-487-3421 x76187",
      address: "695 Adrian Ramp",
      opening_hours: "08:00",
      description: "expedita dolor excepturi",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=93.85067756231373",
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
      id: 27,
      name: "Augusta Konopelski",
      tel: "(857) 640-6422 x2450",
      address: "2016 Swaniawski Shore",
      opening_hours: "08:00",
      description:
        "Aut culpa minus nulla ut quisquam temporibus. Quam tempora repellendus aliquid. Aliquid necessitatibus molestiae eaque vitae saepe. Magni corrupti dolor quia vitae rem ipsam animi at quia. Labore corporis neque earum.",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=14.893441751627211",
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
      id: 28,
      name: "Elenora Zulauf",
      tel: "(140) 481-7894",
      address: "4320 Keshawn Tunnel",
      opening_hours: "08:00",
      description:
        "Reprehenderit dolores eveniet eos ut vel earum.\nUt et iusto rem velit quo unde.\nUnde recusandae quia tempora quia velit soluta fugit.\nDeserunt quo eligendi officia voluptatum.",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=45.567704445096766",
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
      id: 29,
      name: "Deshawn Halvorson",
      tel: "(477) 316-2724",
      address: "735 Mante Throughway",
      opening_hours: "08:00",
      description:
        "Magnam vitae enim sint. Omnis et atque rerum consectetur qui unde. Odio voluptate nisi suscipit quasi. Iure voluptas eaque sit voluptatibus commodi.\n \rLabore nesciunt repellat velit architecto soluta eos. Sunt rerum alias at dolorem recusandae provident recusandae praesentium. Sed fuga sed ducimus eum omnis quasi veniam repellat. Perspiciatis sunt labore. Aliquid sit consequatur in sit molestiae voluptas.\n \rEt quasi rerum voluptatem in non reprehenderit. Et voluptates qui ut. Vitae a deserunt perferendis aut nostrum deleniti. Ut sint sed doloremque tempore ipsa expedita tempore sapiente sapiente. Quia soluta incidunt.",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=14.437131178192564",
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
      Category: {
        id: 1,
        name: "中式料理",
        createdAt: "2021-11-10T13:02:01.000Z",
        updatedAt: "2021-11-10T13:02:01.000Z",
      },
    },
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
      id: 33,
      name: "Dr. John Cassin",
      tel: "419.262.7437 x836",
      address: "8572 Stark Cape",
      opening_hours: "08:00",
      description:
        "Praesentium voluptatem laboriosam magni maxime ab nam error ea. Totam aliquam non excepturi. Cupiditate excepturi perferendis ducimus rem sunt modi vero. Maxime nesciunt est.",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=27.064854081922938",
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
      id: 34,
      name: "Jeffery Rempel",
      tel: "1-775-374-2857 x55091",
      address: "360 Tabitha Avenue",
      opening_hours: "08:00",
      description:
        "Voluptatem alias vel. Ratione qui qui unde omnis nemo animi numquam eum odit.",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=16.553519197888676",
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
      id: 35,
      name: "Lemuel Shields",
      tel: "701-787-0258",
      address: "5416 Stiedemann Ports",
      opening_hours: "08:00",
      description:
        "Eos aspernatur unde temporibus totam autem. Ratione consequatur omnis sapiente. Quia necessitatibus aut temporibus corporis omnis quam cupiditate. Pariatur sed id fugit aut sapiente beatae. Totam illo porro culpa sed aut id nesciunt iure. Molestiae laudantium est consequuntur.\n \rLaborum et in. Dolores vel velit inventore repudiandae rerum perspiciatis est quis eveniet. Et non fuga facere et. Ipsa ducimus quisquam fuga aut non tempora doloremque. Sed beatae nobis occaecati.\n \rQui nam dolorum ullam. Eum est voluptas iusto sed qui maxime dolor quos. Dignissimos id tempore a iusto voluptatibus maiores.",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=79.2375489851018",
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
      id: 37,
      name: "Tommie Turner",
      tel: "1-489-926-9326",
      address: "7986 Khalid Orchard",
      opening_hours: "08:00",
      description:
        "Eum voluptatem possimus. Nostrum aliquam consequatur vel quo reprehenderit quod quis quas. Quas est incidunt. Quas ipsa eos et corporis et. Omnis inventore ex nihil quidem laudantium ullam odit.",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=68.64916561776211",
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
      id: 39,
      name: "Cesar Fadel",
      tel: "023.968.4031 x24497",
      address: "033 Kip Lakes",
      opening_hours: "08:00",
      description: "Voluptatum nesciunt magnam.",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=64.03240692709558",
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
      id: 40,
      name: "Emerald Terry",
      tel: "737-459-5301",
      address: "9694 Kub Roads",
      opening_hours: "08:00",
      description: "Vitae quo neque. Et earum vero voluptatem.",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=32.64744878126811",
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
      id: 43,
      name: "Leta Frami",
      tel: "835.163.1493 x3606",
      address: "1064 Pierre Islands",
      opening_hours: "08:00",
      description:
        "Et itaque consequatur provident et ullam molestiae quas doloremque voluptatem. Reprehenderit debitis deserunt facere nam quod ut. Ut recusandae ea necessitatibus molestias suscipit numquam tenetur. Autem fugiat quod distinctio maxime et est quo. Voluptatem ex quae iste quo quisquam.",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=4.858608062109138",
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
    },
    {
      id: 44,
      name: "Adela Greenholt",
      tel: "712-216-2293 x567",
      address: "82964 Anika Mews",
      opening_hours: "08:00",
      description: "Explicabo ex aliquam rerum natus.",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=46.924994763128595",
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
      id: 45,
      name: "Henri Farrell",
      tel: "800-143-6840 x47535",
      address: "274 Mustafa Cliff",
      opening_hours: "08:00",
      description:
        "Veritatis repellat harum eos qui facilis vitae non sit. Temporibus nesciunt est sed veritatis veritatis in recusandae explicabo illum. Minus assumenda molestiae fugiat. Ex dolores commodi illo sit. Qui adipisci assumenda sunt laborum.",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=47.206362386487186",
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
      Category: {
        id: 1,
        name: "中式料理",
        createdAt: "2021-11-10T13:02:01.000Z",
        updatedAt: "2021-11-10T13:02:01.000Z",
      },
    },
    {
      id: 47,
      name: "Mr. Manuel Langworth",
      tel: "445.156.6542 x08384",
      address: "3014 Medhurst Knoll",
      opening_hours: "08:00",
      description:
        "Ipsa sequi et provident. Ad voluptatem quos temporibus nihil qui. Quas consequatur facere blanditiis rerum laborum dolor eaque non.",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=72.26996384221722",
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
      id: 48,
      name: "Delmer Hintz",
      tel: "405.323.1970 x4606",
      address: "25110 Abernathy Mountains",
      opening_hours: "08:00",
      description: "Quasi quaerat vel est molestiae a numquam.",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=34.61166929171664",
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
      id: 49,
      name: "Betsy Wehner",
      tel: "481-655-5657",
      address: "85913 Rosemary Rapids",
      opening_hours: "08:00",
      description:
        "Sed tempore numquam id cum nihil.\nRecusandae eaque illo distinctio.\nVero ex nostrum est qui itaque rem dolor perferendis quia.",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=66.10288617434992",
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
      id: 50,
      name: "Shayna Hansen",
      tel: "235.314.6357 x1401",
      address: "954 Hahn Green",
      opening_hours: "08:00",
      description: "reprehenderit voluptas numquam",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=57.68118626013747",
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
    },
  ],
};
export default {
  data() {
    return {
      restaurants: [],
    };
  },
  created() {
    this.fetchRestaurants();
  },
  methods: {
    fetchRestaurants() {
      this.restaurants = dummyData.restaurants;
    },
    deleteRestaurant(restaurantId) {
      this.restaurants = this.restaurants.filter(
        (restaurant) => restaurant.id !== restaurantId
      );
    },
  },
};
</script>