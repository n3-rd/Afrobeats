<template>
  <div class="min-h-screen flex" id="artists">
    <div class="famous-artists w-full md:w-[70%]">
      <div class="text-2xl text-center font-black py-7 md:hidden">
        Famous Artists
      </div>
      <!-- two columns-grid -->
      <div class="grid grid-cols-1 md:grid-cols-2">
        <div v-for="artist in artists" :key="artist.id">
          <!-- background image with caption -->
          <div class="relative h-[39rem]">
            <img :src="artist.image" class="w-full h-full object-cover" />
            <div class="absolute bottom-0 left-0 w-full h-[3rem]">
              <div class="flex h-full pl-4">
                <div class="text-white">
                  <h1 class="text-2xl font-bold">{{ artist.name }}</h1>
                  <p class="text-sm">{{ artist.description }}</p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div
      class="title text-[3rem] w-[30%] min-h-screen hidden md:flex justify-center items-center"
    >
      <div>Famous Artists</div>
    </div>
  </div>
</template>

<script>
export default {
  name: "FamousArtistsSection",
  data() {
    return {
      artists: [
        {
          name: "Burna Boy",
          image: "/img/burna.jpg",
        },
        {
          name: "Davido",
          image: "/img/davido.jpg",
        },
        {
          name: "Wizkid",
          image: "/img/wizkid.jpeg",
        },
        {
          name: "Kizz Daniel",
          image: "/img/kizz-daniel.jpg",
        },
        {
          name: "Blaqbonez",
          image: "/img/blaqbonez.jpeg",
        },
        {
          name: "BNXN",
          image: "/img/bnxn.jpeg",
        },
        {
          name: "Ruger",
          image: "/img/ruger.jpg",
        },
        {
          name: "Asake",
          image: "/img/asake.jpeg",
        },
        // {
        //   name: "artist-9",
        //   image: "/img/",
        // },
      ],
    };
  },
};
</script>
