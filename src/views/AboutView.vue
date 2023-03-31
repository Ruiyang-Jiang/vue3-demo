<template>
  <div class="common-layout"></div>
  <el-container>
      <el-main style="background-color: #000000;">
        <!-- <div class="stage"></div> -->
        <br><br>
        <div class="light-first_row">
          <el-row :gutter='20' justify="center">
            <el-col :span='2'>
              <div class="gutter">
                <el-button type="primary" circle color="#ffffff" @click="showCircle1">WHITE </el-button> 
                <div v-if="isShowCircle1" class="circle1"></div>
              </div>
            </el-col>
            <el-col :span='2'>
              <div class="gutter">
                <el-button type="primary" circle color="#ffffff" @click="showCircle2">WHITE </el-button>
                <div v-if="isShowCircle2" class="circle2"></div>
              </div>
            </el-col>
            <el-col :span='2'>
              <div class="gutter">
                <el-button type="primary" circle color="#ffffff" @click="showCircle3">WHITE </el-button>
                <div v-if="isShowCircle3" class="circle3"></div>
              </div>
            </el-col>
            <el-col :span='2'>
             <div class="gutter">
                <el-button type="primary" circle color="#ffffff" @click="showCircle4">WHITE </el-button>
                <div v-if="isShowCircle4" class="circle4"></div>
              </div>
            </el-col>
            <el-col :span='2'>
              <div class="gutter">
                <el-button type="primary" circle color="#ffffff" @click="showCircle5">WHITE </el-button>
                <div v-if="isShowCircle5" class="circle5"></div>
              </div>
            </el-col>      
          </el-row>
        </div>
        <br><br><br><br><br><br>
        <el-divider /><br><br><br><br><br>  
        <div class="light-second_row">
          <el-row :gutter='20'  justify="center">
            <el-col :span='2'>
              <div class="gutter" id="color-picker-container">
                <el-button type="primary" circle color="#00FF00" @click="showRGBSCircle1">RGBW_S1</el-button>
                <div v-if="isShowRGBSCircle1" class="RGBSCircle1" :style="{ backgroundColor: color1 }"></div>
              </div>
            </el-col>
            <el-col :span='2' >
              <div class="gutter">
                <el-button type="primary" circle color="#ffffff" @click="showCircle6">WHITE </el-button>
                <div v-if="isShowCircle6" class="circle6"></div>
              </div>
            </el-col>
            <el-col :span='2'>
              <div class="gutter">
                <el-button type="primary" circle color="#FF69B4" @click="showRGBSCircleM1">RGBW_M1</el-button>
                <div v-if="isShowRGBSCircleM1" class="RGBSCircleM1" :style="{ backgroundColor: color5 }" v-drag></div>
              </div>
            </el-col> 
            <el-col :span='2'>
             <div class="gutter">
                <el-button type="primary" circle color="#00FF00" @click="showRGBSCircle2">RGBW_S2</el-button>
                <div v-if="isShowRGBSCircle2" class="RGBSCircle2" :style="{ backgroundColor: color2 }"></div>
              </div>
            </el-col>
            <el-col :span='2'>
              <div class="gutter">
                <el-button type="primary" circle color="#00FF00" @click="showRGBSCircle3">RGBW_S3</el-button>
                <div v-if="isShowRGBSCircle3" class="RGBSCircle3" :style="{ backgroundColor: color3 }"></div>
              </div>
            </el-col>
            <el-col :span='2'>
              <div class="gutter">
                <el-button type="primary" circle color="#FF69B4" @click="showRGBSCircleM2">RGBW_M2</el-button>
                <div v-if="isShowRGBSCircleM2" class="RGBSCircleM2" :style="{ backgroundColor: color6 }" v-drag></div>
              </div>
            </el-col>
            <el-col :span='2'>
              <div class="gutter">
                <el-button type="primary" circle color="#ffffff" @click="showCircle7">WHITE </el-button>
                <div v-if="isShowCircle7" class="circle7"></div>
              </div>
            </el-col>
            <el-col :span='2'>
             <div class="gutter">
              <el-button type="primary" circle color="#00FF00" @click="showRGBSCircle4">RGBW_S4</el-button>
              <div v-if="isShowRGBSCircle4" class="RGBSCircle4" :style="{ backgroundColor: color4 }"></div>
              </div>
            </el-col>
          </el-row>
        </div>
      </el-main>
      <el-footer>
        <div class="color-picker-container">
        <div class="color-picker-wrapper">
          <p>RGBW_S1 color</p>
          <el-color-picker show-alpha id="eu_color_picker" v-model="color1"/>
        </div>
        <div class="color-picker-wrapper-moving1">
          <p>RGBW_M1 color</p>
          <el-color-picker show-alpha id="eu_color_picker4" v-model="color5"/>
        </div>
        <div class="color-picker-wrapper2">
          <p>RGBW_S2 color</p>
          <el-color-picker show-alpha id="eu_color_picker2" v-model="color2"/>
        </div>
        <div class="color-picker-wrapper3">
          <p>RGBW_S3 color</p>
          <el-color-picker show-alpha id="eu_color_picker3" v-model="color3"/>
        </div>
        <div class="color-picker-wrapper-moving2">
          <p>RGBW_M2 color</p>
          <el-color-picker show-alpha id="eu_color_picker4" v-model="color6"/>
        </div>
        <div class="color-picker-wrapper4">
          <p>RGBW_S4 color</p>
          <el-color-picker show-alpha id="eu_color_picker4" v-model="color4"/>
        </div>
        </div>
        <br><br>
        <div>
          <el-form :model="form" label-width="200px">
            <el-form-item label="preset scene name">
              <el-input v-model="form.name" style="width: 500px;"/><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Current Scene:</p>
            </el-form-item>
            <el-form-item>
              <el-button type="primary" @click="onSubmit">Create</el-button>
              <el-button v-for="(button, index) in buttons" :key="button" @click="onDelete(index)">{{ `Delete ${button}` }}</el-button>
            </el-form-item>
          </el-form>
          <div>
            <el-button v-for="(button, index) in buttons" :key="button" :class="buttonClass(index)" @click="callTestUpdateCurrentScene(index)">{{ button }}</el-button>
          </div>
        </div>
        <br><br>
        <el-button type="primary" @click="playCurrentScene">Play current scene</el-button>
      </el-footer>
    </el-container>

</template>

<script lang="ts">
import { defineComponent,ref } from 'vue'
import axios, { AxiosResponse } from 'axios';
import tinycolor from 'tinycolor2';
export default defineComponent({
  data() {
    return {
      isShowCircle1: false,
      isShowCircle2: false,
      isShowCircle3: false,
      isShowCircle4: false,
      isShowCircle5: false,
      isShowCircle6: false,
      isShowCircle7: false,
      isShowCircle8: false,
      isShowCircle9: false,
      isShowRGBSCircle1: false,
      isShowRGBSCircle2: false,
      isShowRGBSCircle3: false,
      isShowRGBSCircle4: false,
      isShowRGBSCircleM1: false,
      isShowRGBSCircleM2: false,
      showColorPicker: false,
      color1: '#000000', // default color
      color2: '#000000', // default color
      color3: '#000000', // default color
      color4: '#000000', // default color
      color5: '#000000', // default color
      color6: '#000000', // default color
      circleTop: 0,
      circleLeft: 0,

      form: {
        name: "",
      },
      buttons: [] as string[],
      activeButton: null as number | null
    };
  },
  methods: {
    showCircle1() {
      this.isShowCircle1 = !this.isShowCircle1;
    },
    showCircle2() {
      this.isShowCircle2 = !this.isShowCircle2;
    },
    showCircle3() {
      this.isShowCircle3 = !this.isShowCircle3;
    },
    showCircle4() {
      this.isShowCircle4 = !this.isShowCircle4;
    },
    showCircle5() {
      this.isShowCircle5 = !this.isShowCircle5;
    },
    showCircle6() {
      this.isShowCircle6 = !this.isShowCircle6;
    },
    showCircle7() {
      this.isShowCircle7 = !this.isShowCircle7;
    },
    showCircle8() {
      this.isShowCircle8 = !this.isShowCircle8;
    },
    showCircle9() {
      this.isShowCircle9 = !this.isShowCircle9;
    },
    showRGBSCircle1() {
      this.isShowRGBSCircle1 = !this.isShowRGBSCircle1;
      if (this.isShowRGBSCircle1) {
        const color = tinycolor(this.color1);
        const r = color._r;
        const g = color._g;
        const b = color._b;
        const i = Math.round(color._a * 255);

        const data = new Uint8Array([r, g, b, i]);

        const CreateFixtureRequest = {
          fixture: {
          id:0,
          channels:data,
          },
        };
        const serverUrl = '192.168.1.13:3000'; // Replace with your actual server URL
        axios.post(`http://${serverUrl}/create-fixture`, CreateFixtureRequest);
        //console.log(0,data);
      }
    },
    showRGBSCircle2() {
      this.isShowRGBSCircle2 = !this.isShowRGBSCircle2;

      if (this.isShowRGBSCircle2) {
        const color = tinycolor(this.color2);
        const r = color._r;
        const g = color._g;
        const b = color._b;
        const i = Math.round(color._a * 255);

        const data = new Uint8Array([r, g, b, i]);
        const CreateFixtureRequest = {
          fixture: {
          id:3,
          channels:data,
          },
        };
        const serverUrl = '192.168.1.13:3000'; // Replace with your actual server URL
        axios.post(`http://${serverUrl}/create-fixture`, CreateFixtureRequest);
        //console.log(2,data);
      }
    },
    showRGBSCircle3() {
      this.isShowRGBSCircle3 = !this.isShowRGBSCircle3;

      if (this.isShowRGBSCircle3) {
        const color = tinycolor(this.color3);
        const r = color._r;
        const g = color._g;
        const b = color._b;
        const i = Math.round(color._a * 255);

        const data = new Uint8Array([r, g, b, i]);
        const CreateFixtureRequest = {
          fixture: {
          id:4,
          channels:data,
          },
        };
        const serverUrl = '192.168.1.13:3000'; // Replace with your actual server URL
        axios.post(`http://${serverUrl}/create-fixture`, CreateFixtureRequest);
        //console.log(3,data);
      }
    },
    showRGBSCircle4() {
      this.isShowRGBSCircle4 = !this.isShowRGBSCircle4

      if (this.isShowRGBSCircle4) {
        const color = tinycolor(this.color4);
        const r = color._r;
        const g = color._g;
        const b = color._b;
        const i = Math.round(color._a * 255);

        const data = new Uint8Array([r, g, b, i]);
        const CreateFixtureRequest = {
          fixture: {
          id:7,
          channels:data,
          },
        };
        const serverUrl = '192.168.1.13:3000'; // Replace with your actual server URL
        axios.post(`http://${serverUrl}/create-fixture`, CreateFixtureRequest);
        //console.log(5,data);
      }
    },
    showRGBSCircleM2() {
      this.isShowRGBSCircleM2 = !this.isShowRGBSCircleM2

      const uint8Array = new Uint8Array(11);
      uint8Array[0] = 150;
      uint8Array[1] = 150;
      uint8Array[2] = 100;
      uint8Array[3] = 100;
      uint8Array[4] = 255;
      uint8Array[5] = 0;
      uint8Array[10] = 0;

      if (this.isShowRGBSCircleM2) {
        const color = tinycolor(this.color6);
        uint8Array[6] = color._r;
        uint8Array[7] = color._g;
        uint8Array[8] = color._b;
        uint8Array[9] = Math.round(color._a * 255);

        const CreateFixtureRequest = {
          fixture: {
          id:5,
          channels:uint8Array,
          },
        };
        const serverUrl = '192.168.1.13:3000'; // Replace with your actual server URL
        axios.post(`http://${serverUrl}/create-fixture`, CreateFixtureRequest);

        //console.log(4,uint8Array);
      }
    },
    showRGBSCircleM1() {
      this.isShowRGBSCircleM1 = !this.isShowRGBSCircleM1;

      const uint8Array = new Uint8Array(11);
      uint8Array[0] = 150;
      uint8Array[1] = 150;
      uint8Array[2] = 100;
      uint8Array[3] = 100;
      uint8Array[4] = 255;
      uint8Array[5] = 0;
      uint8Array[10] = 0;

      if (this.isShowRGBSCircleM1) {
        const color = tinycolor(this.color5);
        uint8Array[6] = color._r;
        uint8Array[7] = color._g;
        uint8Array[8] = color._b;
        uint8Array[9] = Math.round(color._a * 255);

        const CreateFixtureRequest = {
          fixture: {
          id:2,
          channels:uint8Array,
          },
        };
        const serverUrl = '192.168.1.13:3000'; // Replace with your actual server URL
        axios.post(`http://${serverUrl}/create-fixture`, CreateFixtureRequest);

        //console.log(1,uint8Array);
      }
    },
    // onSubmit() {
    //   this.buttons.push(this.form.name);
    //   this.form.name = ""; // clear the input field after creating a button
    // },
    onDelete(index: number) {
      this.buttons.splice(index, 1)
      this.activeButton = null
    },
    onButtonClick(index: number) {
      if (this.activeButton !== null) {
        this.activeButton = index
      }
    },

    async onSubmit() {
      // Assuming `serverUrl` and `createSceneRequest` are defined and passed from the component
      const serverUrl = '192.168.1.13:3000';
      const createSceneRequest = {
        // Define the properties of the createSceneRequest object
        scene: {
          name: this.form.name,
          external: false,
          stage: {
            fixtures: null,
          },
       },
        // Add other properties as needed
      };
      
      axios.post(`http://${serverUrl}/create-scene`, createSceneRequest);
      
      // Do something with the response, e.g., update the component's data
      this.buttons.push(this.form.name);
      this.form.name = '';
      },
      
    async callTestUpdateCurrentScene(index:number) {
      const sceneName = this.buttons[index];
      const UpdateCurrentSceneRequest ={name:sceneName,};
      const serverUrl = '192.168.1.13:3000'; // Replace with your actual server URL
      axios.post(`http://${serverUrl}/update-current-scene`, UpdateCurrentSceneRequest);
    },

    async playCurrentScene() {
      const serverUrl = '192.168.1.13:3000';
      axios.post('http://${serverUrl}/play-scene');
    },
  },
    computed: {
      buttonClass() {
        return (index:number) => {
          return {
            'active': index === this.activeButton
          }
        }
    }
},
    

  },
);

</script>

<style scoped>
.layout-container-demo .el-main {
  padding: 0;
}

.circle1 {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-200%, -70%); /*position of circle*/
  width: 200px;
  height: 200px;
  border-radius: 50%;
  background-color: white;
  pointer-events: none;
  opacity: 30%;
}
.circle2 {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-130%, -70%); /*position of circle*/
  width: 200px;
  height: 200px;
  border-radius: 50%;
  background-color: white;
  pointer-events: none;
  opacity: 30%;
}
.circle3 {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -70%); /*position of circle*/
  width: 200px;
  height: 200px;
  border-radius: 50%;
  background-color: white;
  pointer-events: none;
  opacity: 30%;
}
.circle4 {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(20%, -70%); /*position of circle*/
  width: 200px;
  height: 200px;
  border-radius: 50%;
  background-color: white;
  pointer-events: none;
  opacity: 30%;
}
.circle5 {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(100%, -70%); /*position of circle*/
  width: 200px;
  height: 200px;
  border-radius: 50%;
  background-color: white;
  pointer-events: none;
  opacity: 30%;
}
 .circle6 {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-100%, -150%); 
  width: 200px;
  height: 200px;
  border-radius: 50%;
  background-color: white;
  pointer-events: none;
  opacity: 30%;
}
.circle7 {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(0%, -150%); 
  width: 200px;
  height: 200px;
  border-radius: 50%;
  background-color: white;
  pointer-events: none;
  opacity: 30%;
}
.circle8 {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-30%, -150%); 
  width: 200px;
  height: 200px;
  border-radius: 50%;
  background-color: white;
  pointer-events: none;
  opacity: 30%;
}
.circle9 {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(30%, -150%); 
  width: 200px;
  height: 200px;
  border-radius: 50%;
  background-color: white;
  pointer-events: none;
  opacity: 30%;
}

.RGBSCircle1{
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-140%, -150%); 
  width: 250px;
  height: 250px;
  border-radius: 50%;
  pointer-events: none;
  opacity: 50%;
}
.RGBSCircle2{
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-80%, -150%); 
  width: 250px;
  height: 250px;
  border-radius: 50%;
  pointer-events: none;
  opacity: 50%;
}
.RGBSCircle3{
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-20%, -150%); 
  width: 250px;
  height: 250px;
  border-radius: 50%;
  pointer-events: none;
  opacity: 50%;
}
.RGBSCircle4{
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(40%, -150%); 
  width: 250px;
  height: 250px;
  border-radius: 50%;
  pointer-events: none;
  opacity: 50%;
}

.RGBSCircleM1{
  position: absolute;
  width: 200px;
  height: 200px;
  transform: translate(40%, -150%); 
  border-radius: 50%;
  opacity: 70%;
}
.RGBSCircleM2{
  position: absolute;
  transform: translate(40%, -150%); 
  width: 200px;
  height: 200px;
  border-radius: 50%;
  opacity: 70%;
}

.color-picker-container {
  display: flex;
  flex-direction: row;
}
.color-picker-wrapper {
  margin-left: 5%;
  margin-right: 5%;
}
.color-picker-wrapper-moving1 {
   margin-right: 5%;/*30px; */
}
.color-picker-wrapper-moving2 {
  margin-right:5%; /*20px;*/
}
.color-picker-wrapper2 {
  margin-right:5%; /*20px;*/
}
.color-picker-wrapper3 {
  margin-right:5%; /*170px;*/
}
.active {
  background-color: blue;
  color: white;
}


</style>