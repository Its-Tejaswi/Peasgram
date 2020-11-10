<template>
  <q-page class="constrain q-pa-md">
    <div class="row q-col-gutter-lg">
      <div class="col-12 col-sm-8">
        <q-card
          class="card-post q-mb-md"
          v-for="post in posts"
          :key="post.id"
          flat
          bordered
        >
          <q-item>
            <q-item-section avatar>
              <q-avatar>
                <img src="https://cdn.quasar.dev/img/boy-avatar.png" />
              </q-avatar>
            </q-item-section>

            <q-item-section>
              <q-item-label class="text-weight-bold"
                >Tejaswi Sidhanthi</q-item-label
              >
              <q-item-label caption>
                {{ post.location }}
              </q-item-label>
            </q-item-section>
          </q-item>

          <q-separator />

          <q-card bordered flat>
            <q-img :src="post.imageUrl" />
            <q-card-actions align="left">
              <q-btn flat round color="red" icon="eva-heart-outline" />
              <q-btn flat round color="teal" icon="comment" />
              <q-btn flat round color="primary" icon="share" />
            </q-card-actions>
            <q-card-section align="left">
              <div class="text-h6 text-bold">{{ post.caption }}</div>
              <div class="text-caption text-dark">
                {{ post.date | niceDate }}
              </div>
            </q-card-section>
          </q-card>
        </q-card>
      </div>
      <div class="col-4 large-screen-only">
        <q-item class="fixed">
          <q-item-section avatar>
            <q-avatar size="48px">
              <img src="https://cdn.quasar.dev/img/boy-avatar.png" />
            </q-avatar>
          </q-item-section>

          <q-item-section>
            <q-item-label class="text-weight-bold"
              >Tejaswi Sidhanthi</q-item-label
            >
            <q-item-label caption>
              Tejaswi Sidhanthi
            </q-item-label>
          </q-item-section>
        </q-item>
      </div>
    </div>
  </q-page>
</template>

<script>
import { date } from "quasar";
export default {
  name: "PageHome",
  data() {
    return {
      posts: [
        {
          id: 1,
          caption: "Mountain Love",
          date: 1604582032902,
          location: "Bangalore, India",
          imageUrl: "https://cdn.quasar.dev/img/mountains.jpg",
        },
        {
          id: 2,
          caption: "Mountain Love",
          date: 1604582032902,
          location: "Bangalore, India",
          imageUrl: "https://cdn.quasar.dev/img/mountains.jpg",
        },
        {
          id: 3,
          caption: "Mountain Love",
          date: 1604582032902,
          location: "Bangalore, India",
          imageUrl: "https://cdn.quasar.dev/img/mountains.jpg",
        },
        {
          id: 4,
          caption: "Mountain Love",
          date: 1604582032902,
          location: "Bangalore, India",
          imageUrl: "https://cdn.quasar.dev/img/mountains.jpg",
        },
      ],
    };
  },
  filters: {
    niceDate(value) {
      return date.formatDate(value, "YYYY-MM-DD  hh:mmA");
    },
  },
};
</script>
