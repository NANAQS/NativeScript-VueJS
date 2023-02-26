<template>
  <Page>
    <ActionBar title="NativeFlix" />
    <GridLayout>
      <Label
        class="text-xl align-middle text-center text-gray-500"
        :text="message"
        @tap="logMessage"
      />
    </GridLayout>
  </Page>
</template>

<script lang="ts">
import Vue from 'nativescript-vue';

export default Vue.extend({
  computed: {
    message() {
      return 'Blank Nanak app';
    },
  },

  methods: {
    logMessage() {
      console.log('You have tapped the message!');
    },
  },
});
</script>
