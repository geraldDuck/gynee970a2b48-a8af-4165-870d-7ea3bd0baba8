<script>
  import { onMount } from 'svelte';
  import { createClient } from '@supabase/supabase-js'
    import Header from '$lib/Header.svelte';
  const key = "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZSIsInJlZiI6ImJpdnBwemNoZG5xcXFsanJldmNwIiwicm9sZSI6ImFub24iLCJpYXQiOjE3MDI1Nzk0NjEsImV4cCI6MjAxODE1NTQ2MX0.TfAS3cgkk7A4mz55W98dC8Oh8n7XjtOflV_2mzMFYTg"
  const url = "https://bivppzchdnqqqljrevcp.supabase.co/"
  const supabase = createClient(url, key, {
    auth: { persistSession: false, autoRefreshToken: false },
  })

const yeah=()=>{location.replace("https://gynee.netlify.app")}
yeah()
</script>
<Header>
  <li slot="image">
    <img src="images/Gynee Purple empty.png" alt="Gynee Logo" class="animate__animated animate__jello logo">
  </li>
</Header>

<style>
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
  }

  .favorites{
    background-color: #E2AEDDaa;
    padding-inline: 20px;
    padding-bottom: 20px;
  
    }
  .disN{
    display: none;
  }

  h2{
    margin: 0px;
  }

  h3{
    margin-bottom: 6px;
  }

  button{
    background-color: #315659;
    border: 2px solid #315659;
    margin-bottom: 5px;
    outline: none;
  }

  button.play{
    padding-inline: 42px;
  }

  button:hover{
    background-color: aliceblue;
    color: #315659;
  }

  button.play:hover{
    animation: gradient_anim 1s infinite;  
    color: aliceblue;
  }

  .song{
    display:block;
    background-color: #EBCBF4;
    width: 30rem;
    margin-top: 10rem;
    padding-top: 20px;
    padding-bottom: 40px;
    border-radius: 2rem;
    color: #1a1a1a;
  }

  .play-container{
    background-color: #E2AEDD;
    padding-top: 0rem;
    padding-bottom: 1rem;
    padding-inline: 3rem;
    filter: drop-shadow(2px 2px 5px #000000aa);
    border-radius: 1rem;
    position: fixed;
    font-family: Arial, Helvetica, sans-serif;
    color: #1a1a1a;
  }

  .play-container{
      right: 0;
      left: 0;
      top: 32rem;
    }

  input{
    outline: none;
    font-family: Inter, system-ui, Avenir, Helvetica, Arial, sans-serif;
    font-size: large;
    padding-inline: 5px;
    padding-top: 2px;
    padding-bottom: 2px;
    border-radius: 10px;
}

input::placeholder{
    color: #f0ffffaa;
}

.favBtnCntnr{
  text-align: right; 
}

.favBtnCntnr button{
  background-color: #EBCBF4;
  border: #EBCBF4;
  color: #1a1a1a;
  font-weight:bold;
}



li{
    cursor: pointer;
    margin-bottom: 30px;
    padding-inline: 10px;
    padding-bottom: 15px;
    padding-top: 29px;
}

li:hover{
  background-color: aliceblue;
}

a{
  text-decoration: none;
  color: #1a1a1a;
  font-weight: bold;
}

#favs_dialog div{
margin-bottom: 150px;
}

.favSong{
    display:block;
    background-color: #EBCBF4;
    width: 30rem;
    margin-top: 10rem;
    padding-top: 20px;
    padding-bottom: 40px;
    border-radius: 2rem;
    color: #1a1a1a;
  }

  img.logo{
    width: 80px;
    height: auto;
    margin-top: 8px;
    position: absolute;
    top: 20px;
    left: 20px;
}



  @media screen and (min-width: 1500px) {
    .play-container{
      right: 69rem;
      left: 1rem;
      top: 7rem;
    }

    .song{
      width: 25rem;
    }
  }
</style>
