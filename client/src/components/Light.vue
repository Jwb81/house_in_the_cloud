<template>
    <!-- <div class='flex-centered'> -->
    <v-flex xs6 sm4 md2 algin-self-center>
        <div 
            class="light-button flex-centered" 
            :class="[selected ? 'light-active' : 'light-inactive']"
            @click='() => handleLightClick(light.id)'
        >
            <span>{{ light.name }}</span>
            <label v-if='showSwitch' class='switch'>
                <input type="checkbox">
                <span class="slider round"></span>
            </label>
        </div>
    </v-flex>
    <!-- </div> -->
</template>

<script>

export default {
    name: 'Light',
    props: {
        light: Object,
        selected: Boolean,
        handleLightClick: Function,
        showSwitch: Boolean
    },   
}
</script>

<style scoped>
.flex-centered {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}

.light-wrapper {
    width: 25%;
}

.light-button {
    background-color: rgba(0,0,0,0.2);
    border: 2px solid gray;
    cursor: pointer;
    /* width: 150px; */
    flex: 1;
    height: 75px;
    margin: 5px;
    border-radius: 10px;
    color: white;
    position: relative;
}
.light-button:hover {
    background-color: rgba(100,100,200,0.4);
}

.light-inactive {
    border: 2px solid rgba(0,0,0, 0.7);
}

.light-active {
    border: 2px solid rgba(20,230,20, 0.7);    
    /* background-color: rgba(0,250,0,0.2); */
}

.top-half,
.bottom-half {
    flex: 1;
}

.top-half {
    display: flex;
    flex-direction: row;
    justify-content: flex-start;
}

.icon {
    /* padding-left: 10px; */
    color: white;
}

/* Light Switch */
.switch {
    position: relative;
    display: inline-block;
    width: 60px;
    height: 34px;
    margin-top: 10px;
}
.swtich input {
    opacity: 0;
    width: 0;
    height: 0;
}
.slider {
    position: absolute;
    cursor: pointer;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background-color: #ccc;
    -webkit-transition: .4s;
    transition: .4s;
}
.slider:before {
  position: absolute;
  content: "";
  height: 26px;
  width: 26px;
  left: 4px;
  bottom: 4px;
  background-color: white;
  -webkit-transition: .4s;
  transition: .4s;
}
input:checked + .slider {
  background-color: #2196F3;
}

input:focus + .slider {
  box-shadow: 0 0 1px #2196F3;
}
input:checked + .slider:before {
  -webkit-transform: translateX(26px);
  -ms-transform: translateX(26px);
  transform: translateX(26px);
}

.slider.round {
  border-radius: 34px;
}

.slider.round:before {
  border-radius: 50%;
}

</style>

