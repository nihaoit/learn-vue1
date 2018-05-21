<template>
    <div class="container">
        <div class="row">
            <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                <h1 v-demo:background.delayed="'red'">Directives Exercise</h1>
                <!-- Exercise -->
                <!-- Build a Custom Directive which works like v-on (Listen for Events) -->

            </div>
        </div>
    </div>
</template>

<script>
export default {
  directives: {
    demo: {
      bind(el, binding, vnode) {
        let delay = 0;
        if (binding.modifiers['delayed']) {
          delay = 3000;
          setTimeout(() => {
            if (binding.arg === 'background') {
              el.style.backgroundColor = binding.value;
            } else {
              el.style.color = binding.value;
            }
          }, delay);
        } else {
          if (binding.arg === 'background') {
            el.style.backgroundColor = binding.value;
          } else {
            el.style.color = binding.value;
          }
        }
      }
    }
  }
};
</script>

<style>
</style>
