<template>
  <div id="app">
    <table>
      <template v-for="row in rows">
        <tr
          @click="toggle(row.id)"
          :class="{ opened: opened.includes(row.id) }"
          v-bind:key="row.id"
        >
          <td>{{ row.name }}</td>
          <td>{{ row.handle }}</td>
        </tr>
       
      </template>
    </table>
  </div>
</template>

<script>
export default {
  methods: {
    toggle(id) {
      const index = this.opened.indexOf(id);
      if (index > -1) {
        this.opened.splice(index, 1);
      } else {
        this.opened.push(id);
      }
    },
  },

  data() {
    return {
      opened: [],
      rows: [
        { id: 1, name: "Bill", handle: "bill" },
        { id: 2, name: "Bob", handle: "bob" },
        { id: 3, name: "Jim", handle: "jim" },
        { id: 4, name: "Leroy", handle: "leroy" },
      ],
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
table {
  width: 100%;
  border: 1px solid #ccc;
}

td {
  padding: 2px;
  border: 1px solid #ccc;
}

.opened {
  background-color: yellow;
}
</style>
