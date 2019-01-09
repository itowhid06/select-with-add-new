<template>
    <div id="app">
        <h3> Select with Add New </h3>
        <WESingleSelectAddNew
                v-model="fruit"
                :options="fruits"
        ></WESingleSelectAddNew>
        <br/>
        <h3> Single Select </h3>
        <WESingleSelect
                v-model="fruit"
                :options="fruits"
        ></WESingleSelect>
    </div>
</template>

<script>
    import WESingleSelectAddNew from './components/select-components/SingleSelectAddNew.vue';
    import WESingleSelect from './components/select-components/SingleSelect.vue';

    export default {
        name: 'app',
        components: {
            WESingleSelectAddNew,
            WESingleSelect
        },

        mounted() {
            this.$on('clickedAddNew', function(newOption){
                this.fruits.push( newOption );
            }) 
        },

        data: function () {
            return {
                fruit: null,
                fruits: ['peach', 'pear', 'apple', 'orange', 'mango', 'banana', 'pineapple']
            }
        }

    }
</script>

<style>
    #app {
        font-family: 'Avenir', Helvetica, Arial, sans-serif;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        text-align: center;
        color: #2c3e50;
        margin-top: 60px;
    }
</style>
