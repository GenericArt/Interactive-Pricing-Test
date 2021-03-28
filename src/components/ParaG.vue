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
        },
        fontcolor: {
            style: String,
            default: '545454'
        }
    },
    data(){
        return{
            fontsize: this.size,
            btnfontcolor: this.fontcolor,
        }
    },
    computed: {
        cssVars() {
            return {
                '--size': this.size + 'px',
                '--btnfontcolor': "#" + this.btnfontcolor,
                
            }
        }
    }
}
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Raleway&display=swap');

p{
    font-size: var(--size);
    color: var(--btnfontcolor);
    font-family: 'Raleway', sans-serif;
}

</style>