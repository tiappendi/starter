<template>
  <file-picker-button :config="gConfig" @picked="showDetails">
    Open Google Drive Dialog
  </file-picker-button>
</template>
<script>
import FilePickerButton from 'vue-google-picker'
export default {
  components: {
    FilePickerButton
  },
  mounted() {
    // addScript: () => {
      var script = document.createElement('script');
      script.type = 'text/javascript';
      script.src = 'https://apis.google.com/js/api.js';
      document.head.appendChild(script);
    // }
  },
  created() {
    this.gConfig = {
      // The Browser API key obtained from the Google API Console.
      developerKey: 'AIzaSyBx8Hc8nc4mC4ojxwIaWyaiE50lFAvr4mM',

      // The Client ID obtained from the Google API Console. Replace with your own Client ID.
      clientId: '279198720198-aeta0re6qbhavf9f1974dmti3a7b8cp8.apps.googleusercontent.com',

      // Scope to use to access user's drive.
      scope: 'https://www.googleapis.com/auth/drive.file'
    }
  }, 
  methods: {
    showDetails (data) {
     if(data.picked === 'picked') {
      console.log(data.docs)
     }
    }
  }
}
</script>