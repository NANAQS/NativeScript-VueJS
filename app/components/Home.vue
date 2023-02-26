<template>
  <Page>
    <ActionBar title="NativeFlix" />
    <ListView height="100%" separatorColor="transparent" v-for="item in posts">
      <v-template>
        <GridLayout
          height="280"
          borderRadius="10"
          class="bg-secondary"
          rows="*, auto, auto"
          columns="*"
          margin="5 10"
          padding="0"
        >
          <image row="0" margin="0" stretch="aspectFill" :src="item.image" />
          <label
            row="1"
            margin="10 10 0 10"
            fontWeight="700"
            class="text-primary"
            fontSize="18"
            :text="item.firstName"
          />
          <label
            row="2"
            margin="0 10 10 10"
            class="text-secondary"
            fontSize="14"
            textWrap="true"
            :text="item.email"
          />
        </GridLayout>
      </v-template>
    </ListView>
  </Page>
</template>

<script lang="ts">
import Vue from 'nativescript-vue';
import { Http } from '@nativescript/core';

export default Vue.extend({
  computed: {
    message() {
      return 'Blank Nanak app';
    },
  },
  created() {
    this.requestApi();
  },
  data() {
    return {
      posts: null,
    };
  },
  methods: {
    logMessage() {
      console.log('You have tapped the message!');
    },
    async requestApi() {
      await Http.getJSON('https://dummyjson.com/users').then(
        (result: any) => {
          console.log(result);
          this.posts = result.users;
        },
        (e) => {}
      );
    },
  },
});
</script>
