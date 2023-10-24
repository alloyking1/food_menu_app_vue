<template>
    <div class="grid grid-cols-1 mx-16">
       <div class="mt-8">
        <input type="text"
        class="w-full rounded border-gray-200"
        placeholder="Enter Search text..">
        <div class="mt-4 flex justify-center">
            <router-link :to="{name:'LetterLink', params: {letter}}" v-for="letter of letters" :key="letter" class="px-2 text-gray-500">
                {{ letter }}
            </router-link>
       </div>
       </div>

       <div class="grid grid-cols-3 gap-3 mt-16">
            <pre>{{ apiRequest }}</pre>
           <div class="border-gray-400 shadow rounded pl-6">
            <img src="" alt="">
            <div class="text-sm p-2 text-gray-500">
                Lorem ipsum dolor sit amet consectetur adipisicing elit. Debitis temporibus itaque, velit quas iste veniam. Dolor id, voluptates provident totam aliquam impedit veritatis cum numquam iste quisquam, natus, enim ipsa.
            </div>
           </div>
       </div>
    </div>
</template>

<script setup>
import { computed, onMounted, ref } from 'vue';
import store from '../../store'
import axiosClient from '../../axiosClient'


const meal = computed (() => store.state.meal)
const letters = 'ABCDEFGHIJKLMNOPQRSTUVWXYZ'.split('')
let apiRequest = ref([])

onMounted(async () => {
    let res = await axiosClient.get('list.php?c=list')
    apiRequest = res.data
    console.log(res.data)
})



</script>