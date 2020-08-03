<template>
  <div class="site-header flex flex-row flex-col sm:flex-row sm:items-center py-6 sm:py-12 sm:mb-4">

    <nuxt-link class="text-white h-auto w-20 sm:mr-16 hover:opacity-75 focus:opacity-75 mb-4 sm:mb-0" to="/">
      <svg class="h-auto w-auto" version="1.0" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1590 1130" preserveAspectRatio="xMidYMid meet">
        <g id="layer101" fill="#ffffff" stroke="none">
          <path d="M430 1105 c-236 -66 -399 -263 -416 -502 -15 -195 78 -384 243 -496 90 -62 167 -88 278 -94 133 -8 278 36 369 111 32 27 31 19 34 224 l2 113 45 -31 c69 -48 120 -63 215 -63 72 -1 94 3 143 26 78 36 127 76 170 139 107 158 83 354 -59 487 -80 76 -144 101 -254 101 -96 0 -168 -24 -239 -80 l-50 -39 -50 33 c-78 53 -161 77 -276 82 -70 3 -116 -1 -155 -11z m888 -124 c156 -80 192 -295 70 -421 -125 -128 -343 -96 -422 62 -31 62 -36 165 -11 226 29 68 106 134 180 153 45 12 141 2 183 -20z m-627 3 c53 -16 107 -43 140 -71 15 -13 15 -19 3 -60 -11 -35 -14 -119 -14 -344 l0 -298 -28 -20 c-15 -10 -57 -29 -92 -41 -54 -19 -80 -21 -158 -17 -81 4 -102 9 -166 40 -220 109 -308 377 -197 596 49 95 176 196 277 220 63 15 176 12 235 -5z"/>
        </g>
      </svg>
    </nuxt-link>

    <ul class="text-xl text-green-400 flex flex-col sm:flex-row sm:flex-1 sm:content-center sm:pt-5">
      <li class="font-semibold sm:ml-0 sm:mx-8"><nuxt-link to="experience">Experience</nuxt-link></li>
      <li class="font-semibold sm:mx-8"><nuxt-link to="education">Education</nuxt-link></li>
      <li class="font-semibold sm:mx-8"><nuxt-link to="interests">Interests</nuxt-link></li>
      <li class="font-semibold sm:mx-8"><nuxt-link to="skills">Skills</nuxt-link></li>
      <li class="font-semibold sm:mr-0 sm:mx-8"><nuxt-link to="uses">Uses</nuxt-link></li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'SiteHeader'
}
</script>
