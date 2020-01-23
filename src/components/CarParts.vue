<template>
  <div id="car-parts">
    <table>
      <thead>
        <tr>
          <th>Part Name</th>
          <th>Part Color</th>
          <th>Actions</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="part in parts" :key="part.id">
          <td>{{ part.name }}</td>
          <td>
            <img :src="part.imageUrl">
          </td>

          <td>
            <button @click="$emit('add:option', option.id)">Add</button>
            <button @click="$emit('delete:part', part.id)">Delete</button>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  name: "car-parts",
  props: {
    parts: Array
  }
};
</script>

<style scoped>
button {
  margin: 0 0.5rem 0 0;
}
</style>