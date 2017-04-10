<template>
  <button 
  :class="[
      {
        'btn-rounded': rounded,
        'btn-pill':pill
      }
    ]"
  ><slot></slot>
  </button>
</template>

<script>
export default {
  props:{
    rounded:Boolean,
    pill:Boolean
  }
}
</script>

<style scoped>
*{
  transition: all .3s;
}
button,button:hover,button:active,button:focus{
  border: none;
  outline:none;
}
button{
  padding:1em 3em;
  cursor: pointer;
  text-align: center;
  font-size: 16px;
  white-space:nowrap;
  appearance: none;
  color:#FFF;
}
.btn-rounded{
  border-radius: 4px;
}
.btn-pill{
  border-radius: 200px;
}
.primary{
  background-color: #1B9AF7
}
.primary:hover{
  background-color: #4cb0f9
}
.success{
  background-color: #A5DE37
}
.success:hover{
  background-color: #b9e563
}
.warning{
  background-color: #FEAE1B
}
.warning:hover{
  background-color: #fec04e
}
.danger{
  background-color: #FF4351
}
.danger:hover{
  background-color: #ff7680
}
.royal{
  background-color: #7B72E9
}
.royal:hover{
  background-color: #a49ef0
}
</style>
