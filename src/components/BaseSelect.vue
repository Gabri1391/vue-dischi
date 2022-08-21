<template>
  <select class="m-3 flex-end" v-model="selectedOption" @change="changeOption">
    <option value="">{{ placeholder ||'Choose an option'}}</option>
    <option v-for="option in options" :key="option.value || option" :value="option.value || option">{{option.label || option}}</option>
  </select>
</template>

<script>
export default {
    name: 'BaseSelect',
    data(){
        return{
            selectedOption: '',
        }
    },
    props:{
        placeholder: String,
        options: Array
    },
    methods:{
        changeOption(){
            this.$emit('option-change', this.selectedOption)
        }
    }

}
</script>

<style>

</style>