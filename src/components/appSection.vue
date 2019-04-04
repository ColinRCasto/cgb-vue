<template>
  <div class="section" :id="idTag">
    <div class="section-header">
      <div class="bar"></div>
      <div>{{ idTag | prettyMono }}</div>
      <div class="bar"></div>
    </div>
    <div class="section-content">
      <p class="text-block"><slot></slot></p>
    </div>
  </div>
</template>

<script>
export default {
  name: "appSection",
  props: {
    idTag: String
  }
};
</script>

<style lang="scss">
$void: #0e0b16;
$fuschia: #a239ca;
$jewel: #4717f6;
$stark: #e7dfdd;
$title-font: "Permanent Marker", cursive;
$primary-font: "Roboto", sans-serif;
$mono-font: "Major Mono Display", monospace;

.section {
  color: $stark;
  height: 100vh;
  width: 100vw;
}

.bar,
.section-header {
  filter: brightness(2) blur(1.6px);
  pointer-events: none;
}

.bar {
  width: 1em;
  height: 0.1em;
  background-color: $stark;
  flex-grow: 1;
  margin: 1em;
  box-shadow: 0 0 5px $jewel, 0 0 10px $fuschia, 0 0 15px $jewel,
    0 0 20px $fuschia;
}

.section-header {
  font-size: 40px;
  font-family: $mono-font;
  text-align: center;
  color: $stark;
  font-weight: bold;
  display: flex;
  flex-flow: row nowrap;
  justify-content: space-around;
  align-items: center;
  text-shadow: 0 0 5px $stark, 0 0 10px $jewel, 0 0 15px $fuschia,
    0 0 20px $stark, 0 0 35px $jewel, 0 0 40px $fuschia;
}

.section-content {
  display: flex;
  flex-flow: column nowrap;
  justify-content: center;
  height: 90vh;
}

.text-block {
  color: $stark;
  text-align: center;
  font-family: $primary-font;
  font-size: 1.5em;
  padding-left: 10em;
  padding-right: 10em;
  line-height: 1.5em;
}
</style>
