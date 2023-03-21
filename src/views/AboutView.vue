<template>
  <div class="common-layout"></div>
  <el-container>
      <el-main style="background-color: #000000;">
        <!-- <div class="stage"></div> -->
        <br><br><br><br><br>
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
            <el-col :span='2' >
              <div class="gutter">
                <el-button type="primary" circle color="#ffffff" @click="showCircle6">WHITE </el-button>
                <div v-if="isShowCircle6" class="circle6"></div>
              </div>
            </el-col>
            <el-col :span='2'>
              <div class="gutter" id="color-picker-container">
                <el-button type="primary" circle color="#00FF00" @click="showRGBSCircle1">RGBW_S1</el-button>  <!--id="toggle-color-picker"-->
                <div v-if="isShowRGBSCircle1" class="RGBSCircle1" :style="{ backgroundColor: color1 }"></div>
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
                <el-button type="primary" circle color="#00FF00" @click="showRGBSCircle2">RGBW_S2</el-button>
                <div v-if="isShowRGBSCircle2" class="RGBSCircle2" :style="{ backgroundColor: color2 }"></div>
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
                <el-button type="primary" circle color="#FF69B4" @click="showRGBSCircleM2">RGBW_M2</el-button>
                <div v-if="isShowRGBSCircleM2" class="RGBSCircleM2" :style="{ backgroundColor: color6 }" v-drag></div>
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
                <el-button type="primary" circle color="#ffffff" @click="showCircle8">WHITE </el-button>
                <div v-if="isShowCircle8" class="circle8"></div>
              </div>
            </el-col>
            <el-col :span='2'>
             <div class="gutter">
              <el-button type="primary" circle color="#00FF00" @click="showRGBSCircle4">RGBW_S4</el-button>
              <div v-if="isShowRGBSCircle4" class="RGBSCircle4" :style="{ backgroundColor: color4 }"></div>
              </div>
            </el-col>
            <el-col :span='2'>
              <div class="gutter">
                <el-button type="primary" circle color="#ffffff" @click="showCircle9">WHITE </el-button>
                <div v-if="isShowCircle9" class="circle9"></div>
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
        <div class="color-picker-wrapper2">
          <p>RGBW_S2 color</p>
          <el-color-picker show-alpha id="eu_color_picker2" v-model="color2"/>
        </div>
        <div class="color-picker-wrapper-moving1">
          <p>RGBW_M1 color</p>
          <el-color-picker show-alpha id="eu_color_picker4" v-model="color5"/>
        </div>
        <div class="color-picker-wrapper-moving2">
          <p>RGBW_M2 color</p>
          <el-color-picker show-alpha id="eu_color_picker4" v-model="color6"/>
        </div>
        <div class="color-picker-wrapper3">
          <p>RGBW_S3 color</p>
          <el-color-picker show-alpha id="eu_color_picker3" v-model="color3"/>
        </div>
        <div class="color-picker-wrapper4">
          <p>RGBW_S4 color</p>
          <el-color-picker show-alpha id="eu_color_picker4" v-model="color4"/>
        </div>
        </div>
      </el-footer>
    </el-container>

</template>

<script lang="ts">
import { defineComponent,ref } from 'vue'

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
      // 圆形区域的初始位置
      circleTop: 0,
      circleLeft: 0,
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
    },
    showRGBSCircle2() {
      this.isShowRGBSCircle2 = !this.isShowRGBSCircle2;
    },
    showRGBSCircle3() {
      this.isShowRGBSCircle3 = !this.isShowRGBSCircle3;
    },
    showRGBSCircle4() {
      this.isShowRGBSCircle4 = !this.isShowRGBSCircle4
    },
    showRGBSCircleM2() {
      this.isShowRGBSCircleM2 = !this.isShowRGBSCircleM2
    },
    showRGBSCircleM1() {
      this.isShowRGBSCircleM1 = !this.isShowRGBSCircleM1;
    },

  },
});

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
  transform: translate(-170%, -150%); 
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
  transform: translate(-100%, -150%); 
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
  margin-left: 285px;
  margin-right: 170px;
}
.color-picker-wrapper-moving1 {
  margin-right: 30px;
}
.color-picker-wrapper-moving2 {
  margin-right: 20px;
}
.color-picker-wrapper2 {
  margin-right: 20px;
}
.color-picker-wrapper3 {
  margin-right: 170px;
}


</style>