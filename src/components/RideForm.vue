<template>
    <div id="shopping-form">
        <h5>Add Ride</h5>
        <form @submit.prevent="handleSubmit">

            <div class="flex-row">
                <div class="flex-small half">
                    <label>Distance</label>
                    <input v-model="item.distance" type="number" />
                </div>

                <div class="flex-small half">
                    <label>Date</label>
                    <input v-model="item.date" type="date" />
                </div>
            </div>

        <div class="flex-row">
                <div class="flex-small half">
                    <label>Time</label>
                    <input v-model="item.time" type="number" />
                </div>
            </div>

            <button>Add Ride</button>
        </form>
    </div>
</template>

<script>
export default {
    name: 'ride-form',
    data(){
        return {
            item: {
                distance: '',
                time: '',
                date: '',
            }
        }
    },
    methods: {
        handleSubmit() {
            this.$emit('add:item', this.item)
            this.item = {
                distance: '',
                time: '',
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