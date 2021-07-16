<template>
    <div id="card" @mouseover="toggleColor" :style={background:color} class="overflow-hidden rounded-lg shadow-lg h-40 w-40">
    </div>
</template>

<script>
export default {
    name: 'box-card',
    props: {
        title : {
            type: String,
            required: true
        },
        color : {
            type: String,
            required: true
        },
    },

    methods:{
        toggleColor: function() {
            window.Event.$emit('mouseover', this.color)
            console.log(this.color)
        },
    },
}
</script>