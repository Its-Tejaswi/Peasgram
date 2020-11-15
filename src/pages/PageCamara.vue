<template>
  <q-page class="constrain-more q-pa-md">
    <div class="camera-frame q-pa-md">
      <video v-show="!imageCaptured" ref="video" class="full-width" autoplay />
      <canvas
        v-show="imageCaptured"
        ref="canvas"
        class="full-width"
        height="200"
      />
    </div>
    <div class="text-center q-pa-md">
      <q-btn
        @click="captureImage"
        size="lg"
        round
        color="grey-10"
        icon="eva-camera"
      />
    </div>
    <div class="row justify-center q-ma-md">
      <q-input
        dense
        v-model="post.caption"
        label="Caption"
        class="col col-sm-6"
      />
    </div>
    <div class="row justify-center q-ma-md">
      <q-input v-model="post.location" label="Location" class="col col-sm-6">
        <template v-slot:append>
          <q-btn round dense flat icon="my_location" />
        </template>
      </q-input>
    </div>
    <div class="row justify-center q-mt-lg">
      <q-btn unelevated rounded color="black" label="Post Image" />
    </div>
  </q-page>
</template>

<script>
import { uid } from "quasar";
export default {
  name: "PageCamara",
  data() {
    return {
      post: {
        id: uid(),
        caption: "",
        location: "",
        photo: null,
        date: Date.now(),
      },
      imageCaptured: false,
    };
  },
  methods: {
    initCamera() {
      navigator.mediaDevices
        .getUserMedia({
          video: true,
        })
        .then((stream) => {
          this.$refs.video.srcObject = stream;
        });
    },
    captureImage() {
      let video = this.$refs.video;
      let canvas = this.$refs.canvas;
      canvas.width = video.getBoundingClientRect().width;
      canvas.height = video.getBoundingClientRect().height;
      let context = canvas.getContext("2d");
      context.drawImage(video, 0, 0, canvas.width, canvas.height);
      this.imageCaptured = true;
    },
  },
  mounted() {
    this.initCamera();
  },
};
</script>

<style lang="scss">
.camera-frame {
  border: 2px solid $grey-10;
  border-radius: 10px;
}
</style>
