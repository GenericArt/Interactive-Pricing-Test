<template>
    <div id="container" :style="cssVars">
        <Paragraph msg="Manley" size="50"/>
        <ButtonTypeOne msg="Start my trial" width="150" height="36" bgcolor="34477d"/>
    </div>
</template>

<script>
import Paragraph from './ParaG.vue'
import ButtonTypeOne from './ButtonTypeOne.vue'

export default {
    name: 'FloatingPopup',
    components: {
        Paragraph,
        ButtonTypeOne,
    },
    props: {
        width: {
            type: String,
            default: "250",
        },
        height: {
            type: String,
            default: "150",
        },
    },
    data(){
        return{
            contwidth: this.width,
            contheight: this.height,
        }
    },
    computed: {
        cssVars(){
            return {
                '--contheight': this.contheight + "px",
                '--contwidth': this.contwidth + "px",
                '--invertcontheight': (this.contheight / 2 ) + "px",
                '--invertcontwidth': (this.contwidth /2) + "px",
            }
        }
    }
    
}
</script>

<style scoped>


#container{
    width: var(--contwidth);
    height: var(--contheight);
    position: fixed;
    top: 50%;
    left: 50%;
    margin-top: calc( -1 * var(--invertcontheight));
    margin-left: calc( -1 * var(--invertcontwidth));

    background-color: rgb(248, 248, 248);
    -webkit-box-shadow: 1px 1px 5px 5px rgba(0,0,0,0.10); 
    box-shadow: 1px 1px 18px 8px rgba(0,0,0,0.04);
    border-radius: 10px;
    
}

</style>