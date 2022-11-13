<template>
  <div class="w-screen h-screen">
    <!-- fullscreen video -->
    <video
      class="w-screen h-screen object-cover bg-fixed"
      autoplay
      loop
      muted
      playsinline
    >
      <source src="/vid/back-in-uni-cut.mp4" type="video/mp4" />
    </video>
    <!-- overlay -->
    <div class="absolute top-0 left-0 w-full h-full opacity-50"></div>
    <!-- content -->
    <div
      class="absolute top-0 left-0 w-full h-full flex flex-col justify-center items-center"
    >
      <h1 class="text-[15vw] text-[#f8f8f8] font-black font-display">
        AFROBEATS
      </h1>
      <div class="absolute bottom-0 left-0 h-16 w-16 text-5xl text-white pl-4">
        scroll
      </div>
      <div class="absolute bottom-0 right-0 h-16 w-16 text-5xl text-white">
        01
      </div>
    </div>
  </div>
</template>
