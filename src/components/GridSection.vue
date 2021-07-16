<template>
    <div class="containers mx-auto px-4 md:px-12">
        <div v-for="heading in headings" :key="heading.title">
            <heading-card
            :title="heading.title" 
            :color="heading.color">
            </heading-card>
        </div>
        <div class="flex flex-wrap -mx-1 lg:-mx-4">
            <div v-for="box in boxes" :key="box.title" class="my-1 px-1 w-full md:w-1/2 lg:my-4 lg:px-4 lg:w-1/3">
                <box-card 
                :title="box.title" 
                :color="box.color">
                </box-card>
            </div>
        </div>

        <div class="flex flex-wrap -mx-1 lg:-mx-4">
            <div v-for="user in users" :key="user.name" class="my-1 px-1 w-full md:w-1/2 lg:my-4 lg:px-4 lg:w-1/3">
                <user-card 
                :name="user.name" 
                :email="user.email" 
                :image="user.image" 
                :age="user.age">
                </user-card>
            </div>
        </div>
    </div>
</template>

<script>

import BoxCard from './BoxCard.vue'
import HeadingCard from './HeadingCard.vue'
import UserCard from './UserCard.vue'

export default {
    components:{
        'box-card' : BoxCard,
        'heading-card' : HeadingCard,
        'user-card' : UserCard
    },
    data : function() {
        return {
            boxes: [
            {
            title : "1",
            color : "red",
            },
            {
            title : "2",
            color : "green",
            },
            {
            title : "3",
            color : "blue",
            },
            ],
            headings: [
            {
                title : "1",
                color : "pink",
            }
            ],
            users: [],
        }
    },

    async mounted() {
        const res = await fetch('https://randomuser.me/api/?results=21')
        const data = await res.json();

        data.results.forEach(el => {
            this.users.push(
            {
                name   :  el.name.first,
                age    :  el.dob.age,
                image  :  el.picture.large,
                email  :  el.email,
            })
        })
    },
}

</script>

<style scoped>
</style>