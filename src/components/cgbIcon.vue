<template>
  <div>
    <svg display="none">
      <symbol id="icon" viewbox="0 0 100 100">
        <path
          fill="#4717F6"
          stroke="#4717F6"
          stroke-width="1"
          d="M 75,85
         a 10 6 0 1 0 -50 0
         q  -20,-30 -5,-50
         l 10,-2
         v 2
         h 2
         v 15
         h 3
         v -15
         l 2,-5
         v -6
         l 3,-10
         l 1,-10
         l 1,10
         l 3,10
         v 6
         l 2,5
         v 15
         h 4
         v -30
         h 6
         v 2
         h 4
         v 2
         h 4
         v -2
         h 4
         v -2
         h 6
         q  20,30 0,65
         z
         
         "
        />

        <path
          mask="url(#bus-cutout)"
          fill="#A239CA"
          stroke="#A239CA"
          stroke-width="1"
          d="M 72,86
         a 10,6 0 1 0 -44,0
         q 0,2 2,5
         q 2,2 5,1
         a 0.9,1 0 0 1 10,0
         l 9,0
         a 0.9,1 0 0 1 10,0
         q 4,2 8,-6
         z"
        />

        <circle cx="40" cy="91.5" r="4" fill="#E7DFDD" />
        <circle cx="59" cy="91.5" r="4" fill="#E7DFDD" />
      </symbol>
    </svg>
    <svg class="logo">
      <mask id="bus-cutout" x="0" y="0" width="100" height="100">
        <rect x="0" y="0" width="100" height="100" fill="white" />
        <rect x="17" y="77" width="20" height="7" fill="black" />
        <rect x="42" y="77" width="5" height="5" fill="black" />
        <rect x="50" y="77" width="5" height="5" fill="black" />
        <rect x="58" y="77" width="5" height="5" fill="black" />
      </mask>
      <use xlink:href="#icon" />
    </svg>
  </div>
</template>
