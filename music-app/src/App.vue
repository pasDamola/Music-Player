<template>
  <div id="app">
    <h1 id="info"></h1>
        <audio id="album" controls>
        </audio>
  </div>
</template>

<script>
export default {
  name: 'app',
      data() {
        return {
            blacks: [
                { name: 'Unfair', location: './albums/East Atlanta Love Letter/01. Unfair.mp3' },
                { name: 'Loaded Gun', location: './albums/East Atlanta Love Letter/02. Loaded Gun.mp3' },
                { name: 'East Atlanta Love Letter (feat. Future)', location: './albums/East Atlanta Love Letter/03. East Atlanta Love Letter (feat. Future).mp3' },
                { name: 'Let Her Go', location: './albums/East Atlanta Love Letter/04. Let Her Go.mp3' },
                { name: 'Sorry', location: './albums/East Atlanta Love Letter/05. Sorry.mp3' },
                { name: 'Pretty Little Fears (feat. J. Cole)', location: './albums/East Atlanta Love Letter/06. Pretty Little Fears (feat. J. Cole).mp3' },
                { name: 'Disconnect', location: 'albums/East Atlanta Love Letter/07. Disconnect.mp3' },
                { name: 'Switch', location: './albums/East Atlanta Love Letter/08. Switch.mp3' },
                // {name:'Thugger’s Interlude', location: 'albums/East Atlanta Love Letter/09. Thugger’s Interlude.mp3'},
                { name: 'Balenciaga Challenge (feat. Offset)', location: './albums/East Atlanta Love Letter/10. Balenciaga Challenge (feat. Offset).mp3' },
                { name: 'Scripture', location: './albums/East Atlanta Love Letter/11. Scripture.mp3' },
                { name: 'Nonchalant', location: './albums/East Atlanta Love Letter/12. Nonchalant.mp3' },
                { name: 'Seasons (feat. Khalid)', location: './albums/East Atlanta Love Letter/13. Seasons (feat. Khalid).mp3' },
                { name: 'Stan', location: './albums/East Atlanta Love Letter/14. Stan.mp3' },
            ]
        }


    },

    mounted() {
        var i = 0;
        var vm = this;
        var audio = document.getElementById("album");
        var info = document.getElementById("info");
       info.innerHTML = `You are now listening to ${vm.blacks[i].name}`;
        audio.src = vm.blacks[i].location;
        audio.addEventListener('ended', function () {
            if (audio.currentTime === audio.duration) {
                i++;
                audio.src = vm.blacks[i].location;
                info.innerHTML = `You are now listening to ${vm.blacks[i].name}`;
                audio.play();
            }
        });
    } 

}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
