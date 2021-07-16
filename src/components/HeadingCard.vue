<template>
    <div class="container w-full">
        <h1 class="text-center text-2xl text-white font-bold m-4" :style={color:color}>Heading</h1>
    </div>
</template>

<script>
export default {
    name: 'heading-card',
    
    data: function(){
        return {
            color : "pink"
        }
    },
    
    created(){
        window.Event.$on('mouseover', (data)=>{
        this.color = data
        })
    }  
}
</script>