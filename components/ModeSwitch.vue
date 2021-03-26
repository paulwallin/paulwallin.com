<template>
    <label class="toggle-switch">
        <input type="checkbox" @click="toggleSwitch">
        <span class="slider round" />
    </label>
</template>

<script>
export default {
  methods: {
    toggleSwitch () {
      const container = document.querySelector('body')
      if (container.classList.contains('test')) {
        container.classList.remove('test')
        // console.log('test1')
      } else {
        container.classList.add('test')
        // console.log('test2')
      }
    }
  }
}
</script>
<style>

.toggle-switch {
  position: relative;
  display: inline-block;
  width: 70px;
  height: 34px;
}

.toggle-switch input {
  opacity: 0;
  width: 0;
  height: 0;
}

.slider {
  position: absolute;
  cursor: pointer;
  top: 0;
  left: 10px;
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
  background-color: #8EABD9;
}

input:focus + .slider {
  box-shadow: 0 0 1px #8EABD9;
}

input:checked + .slider:before {
  -webkit-transform: translateX(26px);
  -ms-transform: translateX(26px);
  transform: translateX(26px);
}

/* Rounded sliders */
.slider.round {
  border-radius: 34px;
}

.slider.round:before {
  border-radius: 50%;
}
</style>