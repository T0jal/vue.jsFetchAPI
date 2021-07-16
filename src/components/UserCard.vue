<template>
    <div id="card" class="overflow-hidden rounded-lg shadow-lg" style="width:350px">
        <a href="#">
            <img alt="Placeholder" class="block" :src="image">
        </a>

        <header class="flex items-center justify-between leading-tight p-2 md:p-4" >
            <h1 class="text-lg">
                <a class="no-underline hover:underline text-black" href="#">
                    {{name}}
                </a>
            </h1>
            <p class="text-grey-darker text-sm">
                {{email}}
            </p>
        </header>

        <footer class="flex items-center justify-between leading-none p-1 md:p-4">
            <a class="flex items-center no-underline hover:underline text-black" href="#">
                <p class="ml-2 text-sm">
                    Age: {{age}}
                </p>
            </a>
        </footer>
    </div>
</template>

<script>
    export default {
        name: 'user-card',
        props: {
            name : {
                type: String,
                required: true
            },
            email : {
                type: Date,
                required: true
            },
            image : {
                type: String,
                required: true
            },
            age : {
                type: String,
                require: true
            }
        },
    }
</script>

<style>
img {
    width: 350px;
    height: auto;
}
footer, header {
    background-color: #eee;
}
</style>