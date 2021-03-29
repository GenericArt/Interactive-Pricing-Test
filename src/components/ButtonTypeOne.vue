<template>
    <a :style="cssVars" id="button">{{ msg }}</a>
</template>

<script>
export default {
    name: 'ButtonTypeOne',
    props: {
        msg: {
            type: String,
            default: "Hello World"
        },
        width: {
            type: String,
            default: "140",
        },
        height: {
            type: String,
            default: "30",
        },
        bgcolor: {
            style: String,
            default: '327fa8'
        },
        fontcolor: {
            style: String,
            default: '#f7f7f7'
        },
        fontsize: {
            style: String,
            default: "12"
        }
    },
    data(){
        return{
            btnwidth: this.width,
            btnheight: this.height,
            btnbgcolor: this.bgcolor,
            btnfontcolor: this.fontcolor,
            btnfontsize: this.fontsize,
        }
    },
    computed: {
        cssVars(){
            return {
                '--btnheight': this.btnheight + "px",
                '--btnwidth': this.btnwidth + "px",
                '--btnbgcolor': "#" + this.btnbgcolor,
                '--btnfontcolor': "#" + this.btnfontcolor,
                '--btnfontsize': this.btnfontsize + "px",
            }
        }
    }
}
</script>

<style scoped>
/* @import url('https://fonts.googleapis.com/css2?family=Raleway&display=swap'); */
@import url('https://fonts.googleapis.com/css2?family=Rubik&display=swap');

#button{
    width: var(--btnwidth);
    height: var(--btnheight);
    color: var(--btnfontcolor);
    display: inline-block;
    padding: 0.3m 1.2m;
    margin: 0 0.3em 0.3em 0;
    border-radius: 2em;
    text-align: center;
    line-height: var(--btnheight);
    background-color: var(--btnbgcolor);
    font-family: 'Rubik', sans-serif;
    transition: all 0.2s;
    font-size: var(--btnfontsize);
}

#button:hover{
    filter: brightness(1.2);
}


</style>