<template>
    <div id="container" :style="cssVars">
        <div id="top-div" style="display: flex;">
            <div>
                <Paragraph msg="100K PAGEVIEWS" size="16" fontcolor="7a7a7a"/>
            </div>
            <div>
                <Paragraph msg="$16.00" size="50" fontcolor="34477d" fontweight="500"/>
            </div>
        </div>
        <div id="middle-upper-div">
            <RangeSlider />
        </div>
        <div id="middle-lower-div">
            <div id="toggle-div">
                <input type="checkbox" id="switch" /><label for="switch">Toggle</label>
            </div>
        </div>
        
        <div id="bottom-div" >
            <!-- <hr id="myH" :style="cssVars"> -->
            <div id="bottom-div-flex-container">
                <div id="bottom-inside-left">
                    <Paragraph msg="Unlimited websites" size="12"/>
                    <Paragraph msg="%100 data ownership" size="12"/>
                    <Paragraph msg="Email reports" size="12"/>
                </div>
                <div id="bottom-inside-right">
                    <ButtonTypeOne msg="Start my trial" width="160" height="36" bgcolor="34477d" fontsize="12" fontcolor="bac5e3"/>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import Paragraph from './ParaG.vue'
import ButtonTypeOne from './ButtonTypeOne.vue'
import RangeSlider from './RangeSlider.vue'

export default {
    name: 'FloatingPopup',
    components: {
        Paragraph,
        ButtonTypeOne,
        RangeSlider,
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
                '--divheight':(this.contheight / 4 ) + "px",
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

#myH {
    border-top: 1px solid rgb(228, 228, 228);
}

#top-div {
    display: flex;
    height: var(--divheight);
}

#middle-upper-div {
    height: var(--divheight);
}

#middle-lower-div {
    height: var(--divheight);
}

#bottom-div {
    height: var(--divheight);
}

#bottom-div-flex-container {
    display: flex;
    border-top: 1px solid rgb(228, 228, 228);
}

#bottom-inside-left{
    width: 49%;
    height: var(--divheight);
}

#bottom-inside-right{
    width: 49%;
    height: var(--divheight);
    display: flex;
    align-items: center;
    justify-content: center;
}





input[type=checkbox]{
	height: 0;
	width: 0;
	visibility: hidden;
}

label {
	cursor: pointer;
	text-indent: -9999px;
	width: 50px;
	height: 25px;
	background: rgb(209, 209, 209);
	display: flex;
	border-radius: 100px;
	position: fixed;
    align-items: center;
    justify-content: center;
}

label:after {
	content: '';
	position: absolute;
	top: 5px;
	left: 5px;
	width: 16px;
	height: 16px;
	background: #fff;
	border-radius: 90px;
	transition: 0.3s;
}

input:checked + label {
	background: #81e0d8;
}

input:checked + label:after {
	left: calc(100% - 5px);
	transform: translateX(-100%);
}

label:active:after {
	width: 50px;
}

#toggle-div {
    
}

/* body {
	display: flex;
	justify-content: center;
	align-items: center;
	height: 100vh;
} */

</style>