<template>
    <div class="citacao">
        <slot name="fonte"></slot>
        <slot name="texto"></slot>
        <slot name="autor"></slot>
    </div>
</template>

<script>
export default {
    created(){
       console.log('created') 
    },
    destroyed(){
        console.log('destroied')
    },
    activated(){
        console.log('activated')
    },
    deactivated(){
        console.log('deactivated')
    }
    // props:['texto']
}
</script>

<style scoped>
    .citacao {
        border: 1px solid #DDD;
        background-color: rgba(0, 0, 0, .1);
        padding: 25px;
        max-width: 450px;
    }
    h1{
        color: blueviolet;
    }
</style>
