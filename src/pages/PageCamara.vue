<template>
  <q-page class="constrain-more q-pa-md">
    <div class="camera-frame q-pa-md">
      <img class="full-width" src="https://cdn.quasar.dev/img/mountains.jpg" />
    </div>
    <div class="text-center q-pa-md">
      <q-btn size="lg" round color="grey-10" icon="eva-camera" />
    </div>
    <div class="row justify-center q-ma-md">
      <q-input dense v-model="post.caption" label="Caption" class="col col-sm-6" />
    </div>
    <div class="row justify-center q-ma-md">
      <q-input v-model="post.location" label="Location" class="col col-sm-6">
        <template v-slot:append>
          <q-btn round dense flat icon="my_location" />
        </template>
        </q-input>
    </div>
        <div class="row justify-center q-mt-lg">
          <q-btn
            unelevated
            rounded
            color="black"
            label="Post Image"
          />
        </div>
  </q-page>
</template>

<script>
export default {
  name: "PageCamara",
    data() {
        return {
            post: {
                caption: '',
                location: '',
            }
        }
    }
};
</script>

<style lang="scss">
.camera-frame {
  border: 2px solid $grey-10;
  border-radius: 10px;
}
</style>
