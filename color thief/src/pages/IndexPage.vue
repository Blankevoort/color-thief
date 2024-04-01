<template>
  <q-page class="flex flex-center">
    <img src="../../public/test.jpg" id="photo" />
  </q-page>
</template>

<script>
import ColorThief from "colorthief";
import { onMounted } from "vue";

export default {
  setup() {
    onMounted(() => {
      const colorThief = new ColorThief();
      const img = document.getElementById("photo");

      if (img.complete) {
        console.log(colorThief.getColor(img));
      } else {
        img.addEventListener("load", function () {
          console.log(colorThief.getColor(img));
        });
      }
    });

    return {};
  },
};
</script>
