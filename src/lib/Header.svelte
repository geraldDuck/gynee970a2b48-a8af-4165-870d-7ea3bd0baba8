<script>
    // @ts-nocheck
    
    
    </script>
    
    <div class="navDiv">
        <nav class="navbar">
            <ul class="navbar-nav">
                <li class="nav-item image">
                    <slot name="image"></slot>
                </li>
    
                <!-- svelte-ignore a11y-click-events-have-key-events -->
                <!-- svelte-ignore a11y-no-noninteractive-element-interactions -->
    
    
                <li class="nav-item search">
                    <slot name="searchBar"></slot>
                </li>
    
               
                    <slot name="uploadBtn"></slot>
                    <slot name="faves"></slot>
                    <slot name="accountBtn"></slot>
                
            </ul>
        </nav>
    </div>
    
    
    <style>
    
    
        
    ul{
        list-style: none;
    
    }
    .navbar{
        height: 70px;
        width: 100%;
        background-color: #E2AEDD;
        color: #1a1a1a;
        font-weight: bold;
        position: fixed;
        bottom: 645px;
        right: 1px;
    }
    
    .navbar-nav{
        display: flex;
        align-items: center;
        justify-content: space-evenly;
        height: 100%;
    }
    
    
    
    
    
    img{
        width: 80px;
        height: auto;
        margin-top: 8px;
    }
    
    
    li.search{
        padding-bottom: 8px;
        padding-inline: 0px;
        cursor:auto;
    }
    
    li.search:hover{
        background-color: #E2AEDD;   
    }
    
    </style>