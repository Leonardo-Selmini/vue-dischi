<template>
  <main>
    <!-- @filterArtist="filterArtist.author, :prop="filteredByArtist" -->
    <Select @filterGenre="filterSongs"/>
    <div class="card-container" v-if="songs != null">
      <Card
        class="card"
        v-for="(song, index) in filteredSongs"
        :key="index"
        :song="song"
      />
    </div>
    <div class="load" v-else>
      <div class="lds-ripple">
        <div></div>
        <div></div>
      </div>
    </div>
  </main>
</template>

<script>
import Select from "./../commons/Select.vue";
import Card from "./../commons/Card.vue";
import axios from "../../../node_modules/axios";

export default {
  name: "Main",
  components: {
    Select,
    Card
  },
  data() {
    return {
      songs: null,
      filteredSongs: null,
      filteredByArtist: null,
    };
  },
  methods: {
    filterSongs(payload) {
      if(payload == 'all') {
        this.filteredSongs = this.songs;
      } else {
        this.filteredSongs = this.songs.filter((song) => {
          return song.genre.toLowerCase().includes(payload.toLowerCase());
        })
      }
    },
    // filterArtist(payload) {
    //   if(payload == 'all') {
    //     this.filteredByArtist = this.filteredSongs
    //     console.log(this.filteredByArtist);
    //   } else {
    //     this.filteredByArtist = this.filteredSongs.filter((song) => {
    //       return song.author.toLowerCase().includes(payload.toLowerCase());
    //     })
    //   }
    // }
  },
  created() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((response) => {
        // handle success
        this.songs = response.data.response;
        this.filteredSongs = response.data.response;
        console.log(response);
      })
      .catch(function (error) {
        // handle error
        console.log(error);
      });
  },
};
</script>

<style lang="scss" scoped>
@import "../../assets/variables.scss";

main {
  height: 90vh;
  background-color: $darkSecondary;
  overflow-y: scroll;

  .card-container {
    width: 70%;
    display: grid;
    grid-template-columns: 25% 25% 25% 25%;
    margin: 0 auto;
    padding-bottom: 2rem;

    .card {
      display: flex;
      flex-direction: column;
      align-items: center;
      text-align: center;
      transition: filter 0.5s;
      filter: brightness(0.9);

      &:hover {
        cursor: pointer;
        filter: brightness(1.1);
      }
    }
  }

  .load {
    height: 90vh;
    display: flex;
    justify-content: center;
    align-items: center;

    .lds-ripple {
      display: inline-block;
      position: relative;
      width: 20rem;
      height: 20rem;
    }
    .lds-ripple div {
      position: absolute;
      border: 4px solid #fff;
      opacity: 1;
      border-radius: 50%;
      animation: lds-ripple 1s cubic-bezier(0, 0.2, 0.8, 1) infinite;
    }
    .lds-ripple div:nth-child(2) {
      animation-delay: -0.5s;
    }
    @keyframes lds-ripple {
      0% {
        top: 10rem;
        left: 10rem;
        width: 0;
        height: 0;
        opacity: 1;
      }
      100% {
        top: 0px;
        left: 0px;
        width: 20rem;
        height: 20rem;
        opacity: 0;
      }
    }
  }
}
</style>