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
        },
        fontweight: {
            style: String,
            default: "400"
        }
    },
    data(){
        return{
            fontsize: this.size,
            parfontcolor: this.fontcolor,
            parfontweight: this.fontweight,
        }
    },
    computed: {
        cssVars() {
            return {
                '--size': this.size + 'px',
                '--btnfontcolor': "#" + this.parfontcolor,
                '--parfontweight': this.parfontweight,
            }
        }
    }
}
</script>

<style scoped>
/* @import url('https://fonts.googleapis.com/css2?family=Raleway&display=swap');
 */
 @import url('https://fonts.googleapis.com/css2?family=Rubik:wght@400;500&display=swap');

p{
    font-size: var(--size);
    color: var(--btnfontcolor);
    font-family: 'Rubik', sans-serif;
    font-weight: var(--parfontweight);
}

</style>