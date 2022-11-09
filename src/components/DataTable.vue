<template>
  <v-table theme="dark">
    <thead>
      <tr>
        <th class="text-left">Name</th>
        <th class="text-left">Calories</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="item in desserts" :key="item.name">
        <td>{{ item.name }}</td>
        <td>{{ item.calories }}</td>
      </tr>
      <tr>
        <th class="text-left">Total</th>
        <td>
          {{ this.totalValue ? this.totalValue : 0 }}
        </td>
      </tr>
    </tbody>
  </v-table>
</template>

<script>
import { ref } from "vue";
export default {
  setup() {
    let totalValue = ref(0);
    const addValue = (numAdded) => {
      totalValue.value = totalValue.value + numAdded;
    };
    return { totalValue, addValue };
  },
  data() {
    return {
      desserts: [
        {
          name: "Frozen Yogurt",
          calories: 159.9,
        },
        {
          name: "Ice cream sandwich",
          calories: 237.3,
        },
        {
          name: "Eclair",
          calories: 262.8,
        },
        {
          name: "Cupcake",
          calories: 305.1,
        },
        {
          name: "Gingerbread",
          calories: 356.5,
        },
        {
          name: "Jelly bean",
          calories: 375.8,
        },
        {
          name: "Lollipop",
          calories: 392.3,
        },
        {
          name: "Honeycomb",
          calories: 408.8,
        },
        {
          name: "Donut",
          calories: 452.2,
        },
        {
          name: "KitKat",
          calories: 518.7,
        },
      ],
    };
  },
  mounted() {
    this.desserts.map((item) => {
      this.addValue(Math.floor(item.calories));
      console.log(this.totalValue);
    });
  },
};
</script>
