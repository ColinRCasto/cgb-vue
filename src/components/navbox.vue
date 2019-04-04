<template>
  <div class="navbox">
    <div class="nav-container">
      <div class="nav-button" @click="scrollToAnchor('about')">{{ "about" | prettyMono }}</div>
      <div class="nav-button" @click="scrollToAnchor('submit');">{{ "submit" | prettyMono }}</div>
      <div class="nav-button" @click="scrollToAnchor('schedule');">{{ "schedule" | prettyMono }}</div>
      <div class="nav-button" @click="scrollToAnchor('attending');">{{ "attending" | prettyMono }}</div>
      <div class="nav-button" @click="scrollToAnchor('donating');">{{ "donating" | prettyMono }}</div>
    </div>
  </div>
</template>

<script>
export default {
  name: "navbox",
  methods: {
    scrollToAnchor(anchor) {
      document
        .getElementById(anchor)
        .scrollIntoView({ behavior: "smooth", block: "start" });
    }
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

.navbox {
  position: fixed;
  top: 7px;
  display: flex;
  justify-content: center;
  transition: all 0.2s;
}

.nav-container {
  position: sticky;
  bottom: -8em;
  width: 100%;
  display: flex;
  flex-flow: row wrap;
  justify-content: space-around;
  align-items: flex-end;
}

.smaller {
  width: 11em;
  height: 11em;
  justify-content: flex-end;
}

.nav-button {
  background: $stark;
  color: $void;
  display: inline;
  cursor: pointer;
  padding: 0.2em;
  border: 0.1em solid $void;
  text-align: center;
  transition: all 0.2s;
  border-radius: 0.25em;
  flex-grow: 2;
  user-select: none;
  font-family: $mono-font;

  &:hover {
    background: $void;
    color: $stark;
    border-color: $stark;
  }
}
</style>
