<script>
export default /*#__PURE__*/ {
  name: "VueMzcModal", // vue component name
  props: {
    title: {
      type: String,
      default: "",
    },
  },
  created() {
    this.$nextTick(function () {
      this.$refs.modal.focus();
    })
  },
};
</script>

<template>
  <div class="vue-mzc-modal">
    <div class="vue-mzc-modal__container">
      <div class="vue-mzc-modal__middle">
        <div class="vue-mzc-modal__box">
          <div class="vue-mzc-modal__overlay" @click="$emit('close')"></div>
          <div class="vue-mzc-modal-box" ref="modal" @keydown.esc="$emit('close')" tabindex="0">
            <div class="vue-mzc-modal-box__header">
              <div class="vue-mzc-modal-box__title">{{ title }}</div>
              <button
                class="vue-mzc-modal-box__close"
                @click="$emit('close')"
              ></button>
            </div>
            <slot />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
