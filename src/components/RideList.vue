<template>
  <div id="shoppingList-table">
    <h5>Ride History</h5>
      <table class="striped-table">
          <thead>
              <tr>
                  <th>Distance</th>
                  <th>Elevation Gain</th>
                  <th>Time</th>
                  <th>Date</th>
              </tr>
          </thead>
          <tbody>
            <tr v-for="item in items" :key="item.id">
                <td>{{item.distance}} miles</td>
                <td>{{item.elevationGain}} feet</td>
                <td>{{item.time}} minutes</td>
                <td>{{item.date}}</td>
            </tr>
          </tbody>
      </table>
      
  </div>
</template>

<script>
export default {
    name: 'ShoppingList',
    props: {
        items: Array
    }
}
</script>

<style scoped>
th {
    font-size: .85rem;
}
td {
    font-size: .75rem;
}

</style>