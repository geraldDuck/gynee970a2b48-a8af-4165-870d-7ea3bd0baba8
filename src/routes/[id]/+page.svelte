<script>
  const params = $page.params.id
  import {page} from "$app/stores"
  import { onMount } from 'svelte';
  import { createClient } from '@supabase/supabase-js'
  import Header from '$lib/Header.svelte';
  const key = "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZSIsInJlZiI6ImJpdnBwemNoZG5xcXFsanJldmNwIiwicm9sZSI6ImFub24iLCJpYXQiOjE3MDI1Nzk0NjEsImV4cCI6MjAxODE1NTQ2MX0.TfAS3cgkk7A4mz55W98dC8Oh8n7XjtOflV_2mzMFYTg"
  const url = "https://bivppzchdnqqqljrevcp.supabase.co/"
  const supabase = createClient(url, key, {
    auth: { persistSession: false, autoRefreshToken: false },
  })

  /**
     * @type {any}
     */
  
  let SongName
  let SongArtist
  let SongLink

  let RS1n = "Click to reveal"
  let RS1ID = params

  let RS2n = "Click to reveal"
  let RS2ID = params

  const getSong = async() =>{  
    const { data, error } = await supabase
      .from('songs')
      .select()
      .eq('id', params)
      console.log(data)
      console.log(error)
      SongName = data[0].name
      SongArtist = data[0].artist
      SongLink = data[0].link
  }
  console.log("Before...      "+SongName)
  const getR_Songs = async(artist) =>{
    console.log("wewrwewsaw...   "+ SongArtist)  
    const { data, error } = await supabase
      .from('songs')
      .select()
      .eq('artist', SongArtist)
      console.log("okay wow... "+ data)
      console.log(error)
      RS1n = data[0].name || "none"
      RS1ID = data[0].id
      RS2n = data[1].name || "none"
      RS2ID = data[1].id

  }
getSong()
</script>
<a href="https://gynee.netlify.app"><button class="back">
  <i class="fa fa-arrow-left"></i>
  Back
</button></a>

<div class="song">
<h1>{SongName}</h1>
<h2>{SongArtist}</h2>
<audio controls src={SongLink}></audio>
<a href='{SongLink}?download=' download='gynee {SongName}'><br><button class="download"><i class='fa fa-download'> </i> Download</button></a>
</div>

<!-- svelte-ignore a11y-click-events-have-key-events -->
<!-- svelte-ignore a11y-no-static-element-interactions -->
<!-- <div on:click={getR_Songs({SongArtist })} class="MFdia">
  <h3>More from {SongArtist}:</h3>
  <a href="http://localhost:5173/{RS1ID}"><div class="recommend"><i class="fa fa-play"></i> {RS1n}</div></a>
  <a href="/{RS2ID}"><div class="recommend"><i class="fa fa-play"></i> {RS2n}</div></a>
</div> -->



<style>
  @import url('https://fonts.googleapis.com/css2?family=Outfit:wght@100..900&display=swap');
  @import url("https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css");

  @font-face {
    font-family: we;
    src: url(fonts/weezer.otf);
  }

  @keyframes gradient_anim {
    0% {background-color: rgba(167,201,87,1);}
    50%{background-color: rgba(106,153,78,1);}
    100%{background:  rgba(56,102,65,1);}
}

  :root{
    background-color: #47126B;
    text-align: center;
    color: aliceblue;
    font-family: "Outfit", sans-serif;
  }



  button.back{
    background-color: #EBCBF4;
    font-family: "Outfit", sans-serif;
    font-size: 2rem;
    border: none;
    padding-block: 10px;
    padding-inline: 10px;
    outline: none;
    border-radius: 1rem;
    cursor: pointer;
    position: absolute;
    top: 15px;
    left: 15px;
  }

  .song{
    background-color: #EBCBF4;
    width: 50%;
    transform: translate(50%, 0);
    padding: 10px;
    border-radius: 1rem;
    color: #000;
    padding-bottom: 40px;
    margin-bottom: 6rem;
  }
  


  button.download{
    background-color: #315659;
    font-family: "Outfit", sans-serif;
    font-size: 2rem;
    border: none;
    padding-block: 10px;
    padding-inline: 10px;
    outline: none;
    border-radius: 1rem;
    cursor: pointer;
    position: rel;
    top: 15px;
    left: 15px;
    color: white;
    padding-inline: 20px;
    margin-top: 2rem;
  }

  .MFdia{
    text-align: left;
  }

  .MFdia h3{
    margin-left: 1rem;
  }

  a{
    text-decoration: none;
    color: inherit;
  }
  .recommend{
    background-color: #EBCBF4;
    width: 75%;
    color: #000;
    padding-inline: 20px;
    padding-block: 20px;
    margin-block: 1rem;
  }


</style>
