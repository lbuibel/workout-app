<template>
    <div id="shopping-form">
        <h5>Add Workout</h5>
        <form @submit.prevent="handleSubmit">

            <div class="flex-row">
                <div class="flex-small half">
                    <label>Workout Type</label>
                    <input v-model="item.type" type="text" />
                </div>

                <div class="flex-small half">
                    <label>Date</label>
                    <input v-model="item.date" type="date" />
                </div>

            </div>

            <div class="flex-row">
                <div class="flex-small one-third">
                    <label>Weight</label>
                    <input v-model="item.weight" type="number" />
                </div>

                <div class="flex-small one-third">
                    <label>Reps</label>
                    <input v-model="item.reps" type="number" />
                </div>

                <div class="flex-small one-third">
                    <label>Sets</label>
                    <input v-model="item.sets" type="number" />
                </div>
            </div>
            <button>Add Workout</button>
        </form>
    </div>

</template>

<script>
export default {
    name: 'workout-form',
    data(){
        return {
            item: {
                type: '',
                weight: '',
                reps: '',
                sets: '',
                date: '',
            }
        }
    },
    methods: {
        handleSubmit() {
            console.log('submitted')
            this.$emit('add:item', this.item)
            this.item = {
                type: '',
                weight: '',
                reps: '',
                sets: '',
                date: '',
            }
        }
    }
}
</script>

<style scoped>
h5 {
    padding: 0;
    margin: 0;
    margin-top: 1rem;
}
label {
    font-size: .85rem;
}
input {
    font-size: .75rem;
    padding: .5rem;
}

button {
    margin-top: 2rem;
    font-size: .85rem;
    text-transform: uppercase;
}

form {
    margin-bottom: 1rem;
}


</style>