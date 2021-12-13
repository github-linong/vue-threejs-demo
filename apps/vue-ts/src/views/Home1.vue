<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
  </div>
</template>

<script lang="ts">

import {
  Component, Ref, Vue, Watch,
} from 'vue-property-decorator';

@Component({
    name: 'app-home',
})
export default class App extends Vue {

}
</script>
