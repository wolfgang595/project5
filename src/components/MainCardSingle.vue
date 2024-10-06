<script setup>

import { faker } from '@faker-js/faker'



const firstname = faker.person.firstName()

const lastname = faker.person.lastName()
const fullname = faker.person.fullName({ irstName: firstname, lastName: lastname })
const job_title = faker.person.jobTitle()
const bio = faker.lorem.lines(2)
const username = faker.internet.userName({firstName: firstname, lastName: lastname}).toLowerCase()


</script>


<!--  -->

<template>
    <RouterLink :to="{name: 'CardDetails', params: {id: username} }">
    <div class="border border-blue-600 rounded-lg shadow bg-blue-600 h-full">
        <img class="object-fill h-480 w-960" v-bind:src="faker.image.urlLoremFlickr({category: 'planes', height: 480, width: 960})" />
        <div class="p-4">
            <p class="mb-2 text-2xl font-bold text-red-500">{{ firstname }} {{ lastname }}</p>
            <p class="mb-3 font-normal text-black">{{ jobtitle }}</p>
            <p class="mb-3 font-normal text-black">{{ bio }}</p>
        </div>
    </div>


    </RouterLink>
</template>






















