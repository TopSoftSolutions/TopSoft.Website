<template>
  <svg viewBox="0 0 135 90" xmlns="http://www.w3.org/2000/svg">
    <defs>
      <style>
        .ink {
          fill: #140957;
          fill-rule: evenodd;
        }
        .blue {
          fill: #1ec2f2;
        }

        .blue-2 {
          animation: move-blue-2 0.5s forwards 0.5s;
        }

        .blue-3 {
          animation: move-blue-3 0.5s forwards 0.5s;
        }

        .ink-1 {
          animation: move-ink-1 0.5s forwards 0.5s;
        }

        .ink-2 {
          animation: move-ink-2 0.5s forwards 0.5s;
        }

        .ink-3 {
          animation: move-ink-3 0.5s forwards 0.5s;
        }

        @keyframes move-blue-2 {
          0% {
            transform: translate(0px, 0px);
          }
          100% {
            transform: translate(-6.55px, 10px);
          }
        }

        @keyframes move-blue-3 {
          0% {
            transform: translate(0px, 0px);
          }
          100% {
            transform: translate(-13.15px, 20px);
          }
        }

        @keyframes move-ink-1 {
          0% {
            transform: translate(0px, 0px);
          }
          100% {
            transform: translate(70px, 15.5px);
          }
        }

        @keyframes move-ink-2 {
          0% {
            transform: translate(0px, 0px);
          }
          100% {
            transform: translate(63.1px, 25.5px);
          }
        }

        @keyframes move-ink-3 {
          0% {
            transform: translate(0px, 0px);
          }
          100% {
            transform: translate(56.4px, 35.5px);
          }
        }

        text {
          opacity: 0;
          animation: fadein 0.5s forwards 1s;
          <!-- fill: white; -->
        }

        @keyframes fadein {
          from {
            opacity: 0;
          }
          to {
            opacity: 1;
          }
        }
      </style>
    </defs>
    <title>TopSoft</title>
    <g>
      <title>TopSoft</title>

      <text x="25" y="20" font-size="9px">Innovation</text>
      <text x="25" y="40" font-size="9px">Quality</text>
      <text x="25" y="62" font-size="9px">Reliability</text>
      <text x="103" y="20" font-size="9px">Design</text>
      <text x="103" y="40" font-size="9px">Build</text>
      <text x="103" y="62" font-size="9px">Manage</text>

      <path
        class="blue blue-1"
        d="m1.57,32.73l17.16,-17.16l1.18,2a5.27,5.27 0 0 1 -0.8,6.48l-17.17,17.13l-1.17,-2a5.26,5.26 0 0 1 0.8,-6.45z"
        id="svg_1"
      />
      <path
        class="blue blue-2"
        d="m8.17,43.78l17.16,-17.16l1.18,2a5.26,5.26 0 0 1 -0.81,6.48l-17.16,17.13l-1.18,-2a5.25,5.25 0 0 1 0.81,-6.48l0,0.03z"
        id="svg_2"
      />
      <path
        class="blue blue-3"
        d="m14.78765,54.9693l17.16,-17.16l1.18,2a5.26,5.26 0 0 1 -0.81,6.48l-17.16,17.13l-1.18,-2a5.25,5.25 0 0 1 0.81,-6.48l0,0.03z"
        id="svg_3"
      />
      <path
        class="ink ink-1"
        d="m8.06436,17.33752l17.17,-17.16l1.18,2a5.27,5.27 0 0 1 -0.81,6.48l-17.16,17.13l-1.18,-2a5.27,5.27 0 0 1 0.8,-6.48l0,0.03z"
        id="svg_7"
      />
      <path
        class="ink ink-2"
        d="m14.91,28.21l17.17,-17.16l1.18,2a5.27,5.27 0 0 1 -0.81,6.48l-17.16,17.13l-1.18,-2a5.27,5.27 0 0 1 0.8,-6.48l0,0.03z"
        id="svg_5"
      />
      <path
        class="ink ink-3"
        d="m21.62141,39.21671l17.17,-17.16l1.18,2a5.27,5.27 0 0 1 -0.81,6.48l-17.16,17.13l-1.18,-2a5.27,5.27 0 0 1 0.8,-6.48l0,0.03z"
        id="svg_6"
      />
    </g>
  </svg>
</template>

<style>
</style>
