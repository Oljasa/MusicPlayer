<template>
    <div class="player">
        <div class="info">
            
            <div class="controls">
                <button class="prev" @click="prev()"></button>
                <button class="play" @click="play()" v-if="!isPlaying"></button>
                <button class="pause" @click="pause()" v-else></button>
                <button class="next" @click="next()"></button>
            </div>
            <div class="title"> {{current.title}}</div>
            <div class="artist"> {{current.artist}}</div>
        </div>
    </div>
</template>

<script>
export default {
    
    name: 'musicplayer',
    data: function() {
        return {
            current: {
                
            },
            index: 0,
            isPlaying: false,
            songs: [
                {
                    title: 'Davai',
                    artist: 'Loco',
                    src: require('../music/Davai-Loco.mp3')
                },
                {
                    title: 'Gold Dust',
                    artist: 'DJ Fresh',
                    src: require('../music/DJ Fresh - Gold Dust.mp3')
                },
                {
                    title: 'Let It Be Me',
                    artist: 'David Guetta',
                    src: require('../music/David Guetta - Let It Be Me(Remix).mp3')
                }
            ],
            player: new Audio()
        }
    },
    created() {
        this.current = this.songs[this.index];
        this.player.src = this.current.src;
        console.log(this.index)
        
        
    },
    methods: {
        play() {
            this.player.play();
            this.isPlaying=true;
            console.log(this.songs[0])
        },
        pause(){
            this.player.pause();
            this.isPlaying=false;
        },
        next(){
            this.current = this.songs[this.index+1];
            this.index += 1;
            this.player.src = this.current.src;
            if(this.isPlaying==true){
                this.play();
            }
            console.log(this.index)
        },
        prev() {
            if(this.index > 0) {
            this.current = this.songs[this.index-1];
            this.index -= 1;
            this.player.src = this.current.src;
            if(this.isPlaying==true){
                this.play();
            }
            console.log(this.index)
            }
        }
    }
}

</script>

<style scoped>
    .player{
        text-align: center;
        position: absolute;
        width: 300px;
        height: 200px;
        top: 50%;
        left: 50%;
        margin: -100px 0 0 -150px;
    }
    .controls {
        display: flex;
        justify-content: center;
        height: 80px;
        padding: 0 15px;
    }
    .title{
        
        font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
        font-size: 45px;
        justify-content: center;
    }
    .artist {
        
        font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
        font-size: 45px;
        justify-content: center;
    }
    button {
        width: 55px;
        height: auto;
        border-radius: 10px;
        background-position: center center;
        background-repeat: no-repeat;
        background-size: 20px;
        margin: 5px 0;
        background-color: #fff;
        cursor: pointer;
        outline: none;
    }
    .prev {
        background-image: url('../assets/previous.svg');
        
    }
    

    .play {
        background-image: url('../assets/play.svg');
        
    }

    .pause {
        background-image: url('../assets/pause.svg');
        
    }

    .next {
        background-image: url('../assets/next.svg');
        
    }
</style>