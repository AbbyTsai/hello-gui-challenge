<script>

</script>


<div class='card'>
<slot>

</slot>

</div>

<style>
.card{
    height: 200px;
	width: 400px;
    border-image: repeating-linear-gradient(90deg, black 0px 10px, red 10px 20px ) 1 5%;
    border-style: solid;
    border-top-width: 15px;
    border-bottom-width: 15px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: space-around;
}
</style>