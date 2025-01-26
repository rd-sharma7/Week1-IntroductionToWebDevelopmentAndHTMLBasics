Day 5: January 24, 2025 
Videos to Watch: 
1. CSS Grid Basics 
2. Building Complex Layouts with CSS Grid 
3. Responsive Design and Media Queries 
Tasks: 
• Build a responsive webpage layout:  
o Use CSS Grid to create a grid layout 
o Apply media queries to make the layout adapt to different screen 
sizes







# Learn about Grid 

display:grid;
grid-template-columnns:100px 100px // 2 columns
grid-row: 1/2 // for start to end 
grid-area
grid-template-area: "nav nav " // naming the two columns as nav
place-content
place-item
gap
row-gap
column-gap
align-items
justify-items

repeat(3,100px) // 100px 100 px 100px 
repeat(3,minmax(100px,1fr))


# Card animation 

<!-- HTML -->

<div class="card">
            
 </div>


 <!-- CSS -->

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