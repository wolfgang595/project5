<template>

 <div class="flex justify-center gap-4 p-8">
        <button @click="prev" :disabled="activePage === 1" class="rounded-md bg-emerald-400 p-2 font-medium text-slate-700 shadow-md">PREV</button>

        <button v-for="page in pages" :key="page" class= "rounded-md bg-slate-100 p-2 font-medium text-slate-700 shadow-md" :class="page ===activePage ? 'bg-red-600 text-slate-100' : '' ">{{ page }}</button>

        <button @click ="next" :disable="activePage ===pages" class="rounded-md bg-emerald-400 p-2 font-medium text-slate-700 shadow-md">NEXT</button>
    </div>

</template>










<script setup>



        import { ref } from 'vue'

        const pages = ref(20)
        const activePage = ref(2)

        const prev = () => {
            if (activePage.value > 1) {
                activePage.value--
                console.log(activePage.value)
            }
        }

        const next = () => {
            if (activePage.value < pages.value) {
                activePage.value++
                console.log(activePage.value)
            }
        }



</script>