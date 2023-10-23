<template>
    <div class="bg-green-500 text-white">
        <pre>
            {{ meal }}
        </pre>
    </div>
</template>

<script setup>
import { computed } from 'vue';
import store from '../../store'


const meal = computed (() => store.state.meal)
</script>