<template>
  <div id="app">
    <div class="stars large"></div>
    <div class="stars medium"></div>
    <cgb-icon></cgb-icon>
    <navbox></navbox>
    <app-section id-tag="about">
      The Columbus Glitchbus is a speedrun marathon hosted live on Twitch.tv,
      showcasing runners from all around Ohio
    </app-section>

    <app-section id-tag="submit">
      If you are interested in running a game for our event that's great! You
      can use our submission form (
      <a
        style="color:#A239CA"
        href="https://docs.google.com/forms/d/e/1FAIpQLSfL2EdW1QpaSPuV5RwtMdnuOa7tahqMzHon-chlTWw640TTtQ/viewform?usp=sf_link"
      >Located Here</a>)
      <br>The currrent deadline for submissions is April 11th, and we will let you
      know if you're run has been accepted within a couple days of that!
    </app-section>

    <app-section id-tag="schedule">
      The schedule will be linked here from
      <a
        style="color:#A239CA"
        href="https://horaro.org/"
      >Horaro.org</a> once it
      is completed
    </app-section>

    <app-section id-tag="attending">
      Coffee Underground will be the venue for our event, if you are able, feel
      free to stop by, grab a muffin and a coffee, hang out and watch some runs
      live!
      <br>
      <div class="mapouter">
        <div class="gmap_canvas">
          <iframe
            width="400"
            height="400"
            id="gmap_canvas"
            src="https://maps.google.com/maps?q=Coffe%20Underground%2C%20Columbus%20Oh&t=&z=13&ie=UTF8&iwloc=&output=embed"
            frameborder="0"
            scrolling="no"
            marginheight="0"
            marginwidth="0"
          ></iframe>
        </div>Google Maps by
        <a
          href="https://www.embedgooglemap.net"
          rel="nofollow"
          target="_blank"
        >Embedgooglemap.net</a>
      </div>
    </app-section>

    <app-section
      id-tag="donating"
    >All proceeds will go to childsplay, further information coming soon!</app-section>
  </div>
</template>

<script>
import appSection from "./components/appSection";
import navbox from "./components/navbox";
import cgbIcon from "./components/cgbIcon";

export default {
  name: "App",
  components: {
    appSection,
    navbox,
    cgbIcon
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

* {
  margin: 0px;
  padding: 0px;
}

#app {
  background: linear-gradient(to bottom, $void 40%, $jewel 75%, $fuschia);
  overflow-x: hidden;
}

@function box-shadow($stars) {
  $bxshadow: ();
  @for $i from 1 to $stars {
    $bxshadow: append(
      $bxshadow,
      (random(2000) + 0px) (random(9000) + 0px) $stark,
      comma
    );
  }
  @return unquote($bxshadow);
}

$bxshadow-large: box-shadow(2000);
$bxshadow-medium: box-shadow(2000);

.stars.large {
  height: 1px;
  width: 1px;
  box-shadow: $bxshadow-large;
  animation: blink-large 3s infinite;
}

.stars.medium {
  height: 0.7px;
  width: 0.7px;
  box-shadow: $bxshadow-medium;
  animation: blink-medium 3s infinite;
}

@keyframes blink-large {
  0% {
    box-shadow: $bxshadow-large;
  }

  70% {
    $colors: $stark, "transparent";
    $stars: $bxshadow-large;
    @for $i from 1 to length($stars) {
      //for each star
      $star: set-nth(
        nth($stars, $i),
        3,
        unquote(nth($colors, random(length($colors))))
      ); //randomly set its shadow color to trnasparent or white
      $stars: set-nth($stars, $i, $star);
    }
    box-shadow: $stars;
  }
  100% {
    box-shadow: $bxshadow-large;
  }
}

@keyframes blink-medium {
  0% {
    box-shadow: $bxshadow-medium;
  }

  50% {
    $colors: "#fff", "transparent";
    $stars: $bxshadow-medium;
    @for $i from 1 to length($stars) {
      //for each star
      $star: set-nth(
        nth($stars, $i),
        3,
        unquote(nth($colors, random(length($colors))))
      ); //randomly set its shadow color to trnasparent or white
      $stars: set-nth($stars, $i, $star);
    }
    box-shadow: $stars;
  }
  80%,
  100% {
    box-shadow: $bxshadow-medium;
  }
}
</style>
