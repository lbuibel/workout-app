<template>
  <div id="shoppingList-table">
      <h5>Workout History</h5>
      <table class="striped-table">
          <thead>
              <tr>
                  <th>Type</th>
                  <th>Weight</th>
                  <th>Reps</th>
                  <th>Sets</th>
                  <th>Date</th>
              </tr>
          </thead>
          <tbody>
            <tr v-for="item in items" :key="item.id">
                <td>{{item.type}}</td>
                <td>{{item.weight}} lbs</td>
                <td>{{item.reps}}</td>
                <td>{{item.sets}}</td>
                <td>{{item.date}}</td>
            </tr>
          </tbody>
      </table>
      
  </div>
</template>

<script>
export default {
    name: 'WorkoutList',
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