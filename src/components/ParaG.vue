<template>
    <p :style="cssVars">{{ msg }}</p>
</template>

<script>
export default {
    name: 'Paragraph',
    props: {
        msg:String,
        size: {
            type: String,
            default: "20"
        }
    },
    data(){
        return{
            fontsize: this.size
        }
    },
    computed: {
        cssVars() {
            return {
                '--size': this.size + 'px',
            }
        }
    }
}
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Raleway&display=swap');

p{
    font-size: var(--size);
    color: rgb(155, 158, 158);
    font-family: 'Raleway', sans-serif;
}

</style>