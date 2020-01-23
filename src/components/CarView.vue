<template>
  <div id="car-view">
    <table>
      <thead>
        <tr>
          <th>Part Color</th>
          <th>Actions</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="option in options" :key="option.id">
          <td>
            <img :src="option.img">
          </td>

          <td>
            <button @click="$emit('add:option', option.id)">Use/Check</button>
            
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  name: "car-view",
  props: {
    options: Array
  }
};
</script>

<style scoped>
button {
  margin: 0 0.5rem 0 0;
}
</style>