<template>
  <div class="history">
    <v-container>
      <div class="mainLabel"><h1>History</h1></div>

      <template>
        <v-simple-table dark="">
          <template v-slot:default>
            <thead>
              <tr>
                <th class="text-left">Film name</th>
                <th class="text-left">Rating</th>
              </tr>
            </thead>
            <tbody>
              <tr v-for="item in desserts" :key="item.name">
                <td>{{ item.name }}</td>
                <td>{{ item.calories }}</td>
              </tr>
            </tbody>
          </template>
        </v-simple-table>
      </template>
    </v-container>
  </div>
</template>

<script>
export default {
  name: "history-view",
  data() {
    return {
      desserts: [
        {
          name: "mad max",
          calories: 6.9,
        },
        {
          name: "Ice cream sandwich",
          calories: 237,
        },
        {
          name: "Eclair",
          calories: 262,
        },
        {
          name: "Cupcake",
          calories: 305,
        },
        {
          name: "Gingerbread",
          calories: 356,
        },
        {
          name: "Jelly bean",
          calories: 375,
        },
        {
          name: "Lollipop",
          calories: 392,
        },
        {
          name: "Honeycomb",
          calories: 408,
        },
        {
          name: "Donut",
          calories: 452,
        },
        {
          name: "KitKat",
          calories: 518,
        },
      ],
    };
  },
};
</script>

<style>
.history {
  height: 100%;
  background-color: rgb(43, 42, 51);
}
</style>
