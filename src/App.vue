<template>
  <div id="app" class="small-container">
    <h1>Exercise Tracker</h1>

    <button class="bike-button" v-on:click="toggle = true"><ion-icon name="bicycle-outline"></ion-icon></button>
    <button class="workout-button" v-on:click="toggle = false"><ion-icon name="barbell-outline"></ion-icon></button>

    <div v-if="toggle">
      <ride-form @add:item="addRide" @add:workoutType='rideHistory'/>
    </div>

    <div v-else>
      <weight-lift-form @add:item="addWorkout"/>
    </div>

    <div class="flex-row">
      <ride-list class="flex-small" :items='rideHistory' />
      <workout-list class="flex-small" :items='workoutHistory' />
    </div>

  </div>
</template>

<script>

import RideList from './components/RideList'
import RideForm from './components/RideForm.vue'
import WeightLiftForm from './components/WeightLiftForm.vue'
import WorkoutList from './components/WorkoutList.vue'

export default {
  name: 'App',
  components: {
    RideList,
    RideForm,
    WeightLiftForm,
    WorkoutList,
  },
  data() {
 return {
      toggle: true,
      rideHistory: [
        {
          id: 1,
          distance: '25',
          elevationGain: 1000,
          time: 110,
          date: '2021-01-26'
        },
        {
          id: 2,
          distance: '30',
          elevationGain: 1500,
          time: 120,
          date: '2021-02-26'
        },
        {
          id: 3,
          distance: '40',
          elevationGain: 800,
          time: 145,
          date: '2021-03-26'
        }
      ],
      workoutHistory: [
        {
          id: 1,
          type: 'Bench',
          weight: 200,
          reps: 10,
          sets: 3,
          date: '2021-3-27'
        },
        {
          id: 2,
          type: 'Squat',
          weight: 250,
          reps: 8,
          sets: 3,
          date: '2021-3-29'
        },
        {
          id: 2,
          type: 'Curls',
          weight: 25,
          reps: 12,
          sets: 4,
          date: '2021-3-29'
        },
      ],
    }
  },
  methods: {
    addRide(item){
      console.log(item)
      // generating a new id number for the item being passed in
      const lastId = this.rideHistory.length > 0
      ? this.rideHistory[this.rideHistory.length -1].id : 0;

      const id = lastId + 1

      const newRide = { ...item, id}

      this.rideHistory = [...this.rideHistory, newRide]
    },
    addWorkout(item){
      console.log(item)
      // generating a new id number for the item being passed in
      const lastId = this.workoutHistory.length > 0
      ? this.workoutHistory[this.workoutHistory.length -1].id : 0;

      const id = lastId + 1

      const newWorkout = { ...item, id}

      this.workoutHistory = [...this.workoutHistory, newWorkout]
    },
  }
}
</script>

<style>
#app {
  color: #2c3e50;
  margin-top: 40px;
}

.bike-button {
  width: 50%;
  font-size: 1.5rem;
  border-top-right-radius: 0;
  border-bottom-right-radius: 0;
  border-top-left-radius: 1rem;
  border-bottom-left-radius: 1rem;
  outline: none;
  padding: .5rem;
}
.workout-button {
  width: 50%;
  font-size: 1.5rem;
  border-top-left-radius: 0;
  border-bottom-left-radius: 0;
  border-top-right-radius: 1rem;
  border-bottom-right-radius: 1rem;
  outline: none;
  padding: .5rem;
}

</style>
