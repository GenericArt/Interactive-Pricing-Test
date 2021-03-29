/<template>
    <input :style="cssVars" type="range" min="1" max="100" value="50" class="slider" id="myRange">
</template>

<script>
export default {
    name: "RangeSlider",
    props: {
        min:{
            style: String,
            default: "1"
        },
        max: {
            style: String,
            default: "100"
        },
        value: {
            style: String,
            default: "50"
        },
        bgcolor: {
            style: String,
            default: "81e0d8"
        }
    },
    data() {
        return {
            sliderbgcolor: this.bgcolor,
        }
    },
    computed: {
        cssVars() {
            return {
                '--sliderbgcolor': "#" + this.sliderbgcolor,
            }
        }
    },
    
    
}

// document.getElementById("myinput").oninput = function() {
//   var value = (this.value-this.min)/(this.max-this.min)*100
//   this.style.background = 'linear-gradient(to right, #82CFD0 0%, #82CFD0 ' + value + '%, #fff ' + value + '%, white 100%)'
// };

</script>



<style scoped>

input[type="range"] {
    width: 80%;
    height: 8px;
    -webkit-appearance: none;
    border-radius: 2em;
    background-color: var(--sliderbgcolor);
    outline:none;
    
}

input[type='range']::-webkit-slider-runnable-track {
    -webkit-appearance: none;
    color: #9913bb;
}

input[type="range"] {

}

input[type="range"]::-webkit-slider-thumb {
    -webkit-appearance: none;
    background-color: var(--sliderbgcolor);
    width: 40px;
    height: 40px;
    border-radius: 50%;
    border: 2px solid white;
    cursor: pointer;
    transition: .3s ease-in-out;
    /* filter: saturate(0.8); */
    /* filter: brightness(1); */

}

input[type="range"]::-webkit-slider-thumb::before {
    background-color: pink;
}

/* input[type="range"]::-webkit-slider-thumb:hover {
    background-color: white;
    border: 2px solid #e74c3c;
}
input[type="range"]::-webkit-slider-thumb:active {
    transform: scale(1.6);
} */



/* input[type="range"]::-moz-range-progress {
  background-color: #43e5f7; 
}
input[type="range"]::-moz-range-track {  
  background-color: #9a905d;
} */

/* IE*/
/* input[type="range"]::-ms-fill-lower {
  background-color: #43e5f7; 
}
input[type="range"]::-ms-fill-upper {  
  background-color: #9a905d;
} */



/* input[type="range"]::-webkit-slider-thumb {
-webkit-appearance: none;
  border-radius: 50%;
  background: 
   url('https://cdn2.iconfinder.com/data/icons/arrows-1-2/380/Arrow_Right2-512.png') center/contain no-repeat content-box,
   lightgray;
  z-index: 1;
  width: 50px;
  position: relative;
  height: 50px;
  padding:5px;
} */


</style>