<template lang="pug">
transition(name="modal-fade")
  section.modal-wrapper
    div.modal-frame-q
      div.modal-text
        slot
      button.btn-1.modal-button(@click="closeEmitter") Закрыть окно
</template>

<script>
export default {
  name: "FQuis",
  props:['show'],
  methods: {
    closeEmitter(){
      this.$emit('close')
    }
  },
};
</script>

<style lang="scss">
.modal-fade-enter,
.modal-fade-leave-to {
  opacity: 0;
}
.modal-fade-enter-active,
.modal-fade-leave-active {
  transition: opacity .5s ease;
}

.modal-wrapper {
  z-index: 999;

  top: 0px;

  position: absolute;
  display: flex;
  flex-flow: column;
  width: 100vw;
  align-items: center;
  height: 100vh;
  background: #000000c7;
  justify-content: center;
}

.modal-frame-q {
  display: flex;
  flex-flow: column;
  background: #FFBD12;
  border: 2px solid #18191F;
  justify-content: center;
  box-shadow: 0px 6px 0px #18191f;
  align-items: center;
  border-radius: 16px;

  width: 320px;
  height: 370px;

  align-items: center;
}

.modal-text {
  font-family: "m-e-medium";
  font-weight: 500;
  font-size: 19px;
  line-height: 18px;
  margin: 44px 16px;
}

.modal-button {
  margin: 0 0 24px;
  width: fit-content;
}
</style>
