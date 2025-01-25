# Learnings 

Animation 

1. For move a box from init to final position i.e transform using translate

// .box is a devision

  .box {
        width: 34px;
        height: 44px;
        background-color: aqua;
        animation: animationLearning;
        animation-duration: 3s;
        animation-iteration-count: 3;
        animation-timing-function: cubic-bezier(0.075, 0.82, 0.165, 1);
        animation-delay: 3s;
        /* animation-direction: alternate-reverse; */
        animation-play-state: running;
    
    }


    @keyframes  animationLearning {

        from {

        }

        to {
            transform: translate(100vh);
        }
        
    }

<!-- Mulitiple animationss -->

    

    @keyframes  byusingPercentage {

        0% {
            transform: rotate(200deg);
        }
        20% {transform: rotate(240deg);}

        40% { transform: rotate(300deg);}

        100% { transform: rotate(310deg);}

        
    }


2. margin: 0 auto // gives o margin from top and bottom and auto fro left and right


3. for a animation of a div surrounding border 

<!-- HTML code -->

     <div class="card">
            Animation Border <br><br>
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Tempore quis voluptatibus aperiam sed repudiandae officiis, tempora rem minima. Provident, eos!
    </div>

<!-- CSS code -->

    @property --angle {
    
        syntax: "<angle>";
        initial-value: 0deg;
        inherits: false;
    }

    .card {
        margin: 40vh auto;
        padding: 2em;
        width: 300px;
        background: #ffff;
        text-align: center;
        border-radius: 15px;
        position: relative;
     }
 

    .card::after, .card::before{
        --angle: 0deg;
        content: '';
        position: absolute;
        height: 100%;
        width: 100%;
        background-image: conic-gradient(from var(--angle) ,transparent 70% ,blue);
        top: 50%;
        left: 50%;
        translate: -50% -50%;
        z-index: -1;
        padding: 3px;
        border-radius: 13px;
        animation: 3s spin linear infinite;
    }


    .card::before{
        filter: blur(1.5rem);
        opacity: 0.5;
    }


    @keyframes spin {

        from {
            --angle:0deg;
        }

        to {
            --angle:360deg;
        }
    }