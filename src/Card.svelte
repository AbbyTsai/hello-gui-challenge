<script>
</script>

<div class='card'>
<slot>
</slot>
</div>

<style>
@media screen and (min-width:769px){
.card{
	height: 150px;
    width: calc(95vw/3);
    border-image: repeating-linear-gradient(90deg, black 0px 10px, red 10px 20px ) 1 25%;
    border-style: solid;
    border-top-width: 2em;
    border-bottom-width: 2em;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: space-around;
}    
}

@media screen and (max-width:768px) and (min-width:481px){
.card{
	height: 150px;
    width: calc(95vw/2);
    border-image: repeating-linear-gradient(90deg, black 0px 10px, red 10px 20px ) 1 25%;
    border-style: solid;
    border-top-width: 2em;
    border-bottom-width: 2em;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: space-around;
}
}

@media screen and (max-width:480px){
.card{
    height: 150px;
    grid: [story] 1fr / [story] 1fr;
    scroll-snap-align: start;
    scroll-snap-stop: always;
    border-style: solid;
    border-image: repeating-linear-gradient(90deg, black 0px 10px, red 10px 20px ) 1 1%;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-items: center;
    justify-content: center;
    border-top-width:2em;
    border-bottom-width:2em;
    border-left-width:5px;
    border-right-width:5px;
    }
}
</style>