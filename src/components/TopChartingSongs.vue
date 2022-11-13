<template>
  <div id="top-charts">
    <h1 class="text-2xl md:text-[6rem] font-black px-7 py-14">
      Top charting ↗
    </h1>

    <div class="charts w-screen flex">
      <div class="playlist w-full md:w-[70%] min-h-screen">
        <div
          class="song border-y border-black py-5 flex text-[0.9rem] md:text-[2rem] hover:bg-black hover:text-white transition-all duration-300"
          v-for="song in songs"
          :key="song.id"
          :data-cover="song.track.album.images[0].url"
        >
          <div class="song-name w-[33%] pl-3 font-bold">
            {{ song.track.name }}
          </div>
          <div class="song-artist w-[33%] font-medium">
            {{ song.track.artists[0].name }}
          </div>
          <a
            :href="song.track.external_urls.spotify"
            target="_blank"
            class="song-spotify w-[33%] cursor-pointer"
            >Spotify ↗</a
          >
        </div>
      </div>
      <div class="playlist-cover w-[30%] min-h-screen hidden md:block">
        <img
          :src="songs[0].track.album.images[0].url"
          alt="playlist cover"
          class="w-full h-full object-cover song-cover"
          v-if="songs[0]"
        />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "TopChartingSongs",
  data() {
    return {
      songs: [],
    };
  },
  methods: {
    fetchSongs() {
      fetch(
        `https://rich-cyan-sturgeon-sock.cyclic.app/getPlaylist?playlistId=37i9dQZF1DWZCOSaet9tpB?si=d6f575171f6c4b30`
      )
        .then((response) => response.json())
        .then((data) => {
          // cut to only 5 songs
          this.songs = data.tracks.items.slice(0, 7);
          console.log(data.tracks.items.slice(0, 7));
        });
    },
    changeImageOnHover() {
      if (this.songs[0]) {
        const song = document.querySelectorAll(".song");
        const songCover = document.querySelector(".song-cover");

        // change image to the currently hovered song cover
        song.forEach((song) => {
          song.addEventListener("mouseover", () => {
            console.log(song.dataset.cover);
            songCover.src = song.dataset.cover;
          });
        });
      }
    },
  },
  mounted() {
    this.fetchSongs();
    setInterval(() => {
      this.changeImageOnHover();
    }, 3000);
  },
};
</script>
