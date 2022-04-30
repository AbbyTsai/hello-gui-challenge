<script>
	import Card from './Component/Card.svelte';
	export let name;
	let n = name;	
	let challenges=[
		{ name: 'styries',date:'2022/11/25',type:'layout',property:'grid, scroll-snap',description:'reponsive story component',url:'https://github.com' },
		{ name: 'centering',date:'2022/12/16',type:'typography',property:'position', description:'centering strategy' ,url:'https://github.com'},
		{ name: 'styries',date:'2022/11/25',type:'layout',property:'grid, scroll-snap',description:'reponsive story component' ,url:'https://github.com'},
		{ name: 'centering',date:'2022/12/16',type:'typography',property:'position', description:'centering strategy' ,url:'https://github.com'},
		{ name: 'styries',date:'2021/11/25',type:'layout',property:'grid, scroll-snap',description:'reponsive story component',url:'https://github.com' },
		{ name: 'centering',date:'2021/12/16',type:'typography',property:'position', description:'centering strategy' ,url:'https://github.com'},
		{ name: 'styries',date:'2021/11/25',type:'layout',property:'grid, scroll-snap',description:'reponsive story component' ,url:'https://github.com'},
		{ name: 'centering',date:'2021/12/16',type:'typography',property:'position', description:'centering strategy' ,url:'https://github.com'},
		{ name: 'styries',date:'2021/11/25',type:'layout',property:'grid, scroll-snap',description:'reponsive story component',url:'https://github.com' },
		{ name: 'centering',date:'2021/12/16',type:'typography',property:'position', description:'centering strategy',url:'https://github.com' },
		{ name: 'styries',date:'2021/11/25',type:'layout',property:'grid, scroll-snap',description:'reponsive story component',url:'https://github.com' },
		{ name: 'centering',date:'2020/12/16',type:'typography',property:'position', description:'centering strategy',url:'https://github.com' },
		{ name: 'styries',date:'2020/11/25',type:'layout',property:'grid, scroll-snap',description:'reponsive story component',url:'https://github.com' },
		{ name: 'centering',date:'2020/12/16',type:'typography',property:'position', description:'centering strategy' ,url:'https://github.com'},
		{ name: 'styries',date:'2020/11/25',type:'layout',property:'grid, scroll-snap',description:'reponsive story component',url:'https://github.com' },
		{ name: 'centering',date:'2020/12/16',type:'typography',property:'position', description:'centering strategy',url:'https://github.com' },
		{ name: 'styries',date:'2020/11/25',type:'layout',property:'grid, scroll-snap',description:'reponsive story component' ,url:'https://github.com'},
		{ name: 'centering',date:'2020/12/16',type:'typography',property:'position', description:'centering strategy' ,url:'https://github.com'},
		{ name: 'styries',date:'2020/11/25',type:'layout',property:'grid, scroll-snap',description:'reponsive story component',url:'https://github.com' },
		{ name: 'centering',date:'2020/12/16',type:'typography',property:'position', description:'centering strategy',url:'https://github.com' },
	];

let array1=[
		{ id: '@AbbyPTsai', word: 'inspired!🧡', url:'https://twitter.com'},
		{ id: '@gnehcwu', word: 'inspired!👍', url:'https://twitter.com'},
		{ id: '@AMVSde', word: 'fantastic!🎈', url:'https://twitter.com'},
		{ id: '@gnehcwu', word: 'inspired!🎨', url:'https://twitter.com'},
		{ id: '@AbbyPTsai', word: 'inspired!🎏', url:'https://twitter.com'},
		{ id: '@gnehcwu', word: 'inspired!👍', url:'https://twitter.com'},
		{ id: '@AMVSde', word: 'fantastic!🎡', url:'https://twitter.com'},
		{ id: '@gnehcwu', word: 'inspired!👍', url:'https://twitter.com'},
		{ id: '@AbbyPTsai', word: 'inspired!😊', url:'https://twitter.com'},
		{ id: '@gnehcwu', word: 'inspired!👍', url:'https://twitter.com'},
		{ id: '@AMVSde', word: 'fantastic!😍', url:'https://twitter.com'},
		{ id: '@gnehcwu', word: 'inspired!👍', url:'https://twitter.com'},
	];

let newarray=[];
function add(){
	const random=Math.floor(Math.random()*array1.length);
	newarray=[...newarray,[array1[random].id,array1[random].word,array1[random].url]];
	del();
}

function del(){
	setTimeout(function(){
		newarray=newarray.slice(1);
	},5000)
}

</script>

<div id='door'>
	<div id="doorLeft" class='door'>
	<div class='hook'>.</div>
	</div>
	<div id="doorRight" class='door'>
	<div class='hook'>.</div>
	</div>
	<div id='knock'>
	knock!
	</div>
	<div id="word">
<button on:click={add}>What folks say</button>
{#each newarray as a, i}
<div class='say'>
{a[1]} <a href={a[2]}>{a[0]}</a>
</div>
{/each}
</div>

<div id='hello'>
<div id='textSplit'>
<h5>Hello</h5>
{#each n as name, i}
{#if i===3}
	<span>&nbsp;&nbsp;</span>
{:else}
	<span>
		{n[i]}
	</span>
{/if}
{/each}
<p>learn more at <a href="https://github.com/argyleink/gui-challenges">Here.</a></p>
</div>
</div>
</div>

<div style='margin-top:35em;'>
<p class='year'>
<span>2</span><span>0</span><span>2</span><span>2</span></p>

<div class='cardset'>
{#each challenges as challenge, i}
{#if challenge.date.includes('2022')}
<Card>
<div><h1>{challenge.name}</h1></div>
<div>{challenge.type}</div>
<div>{challenge.property}</div>
<button><a href="#dialog{i}">Open</a></button>
<div class="dialog2022" id="dialog{i}">
<div class='dialogContent'>
<div><h1>{challenge.name}</h1></div>
<div>{challenge.type}</div>
<div>{challenge.property}</div>
<div><a href={challenge.url}>{challenge.description}</a></div>
<div>{challenge.date}</div>
<button><a href="#cardset">back</a></button>
</div>
</div>
</Card>
{/if}
{/each}
</div>

<p class='year'>
<span>2</span><span>0</span><span>2</span><span>1</span></p>
<div class='cardset'>
{#each challenges as challenge, i}
{#if challenge.date.includes('2021')}
<Card>
<div><h1>{challenge.name}</h1></div>
<div>{challenge.type}</div>
<div>{challenge.property}</div>
<button><a href="#dialog{i}">Open</a></button>
<div class="dialog" id="dialog{i}">
<div class='dialogContent'>
<div><h1>{challenge.name}</h1></div>
<div>{challenge.type}</div>
<div>{challenge.property}</div>
<div><a href={challenge.url}>{challenge.description}</a></div>
<div>{challenge.date}</div>
<button><a href="#cardset">back</a></button>
</div>
</div>
</Card>
{/if}
{/each}
</div>

<p class='year'>
<span>2</span><span>0</span><span>2</span><span>0</span></p>
<div class='cardset'>
{#each challenges as challenge, i}
{#if challenge.date.includes('2020')}
<Card>
<div><h1>{challenge.name}</h1></div>
<div>{challenge.type}</div>
<div>{challenge.property}</div>
<button><a href="#dialog{i}">Open</a></button>
<div class="dialog" id="dialog{i}">
<div class='dialogContent'>
<div><h1>{challenge.name}</h1></div>
<div>{challenge.type}</div>
<div>{challenge.property}</div>
<div><a href={challenge.url}>{challenge.description}</a></div>
<div>{challenge.date}</div>
<button><a href="#cardset">back</a></button>
</div>
</div>
</Card>
{/if}
{/each}
</div>

</div>
<div class="footer">
<div>Inspired by <a href="https://web.dev/shows/gui-challenges/">GUI CHALLENGES.</a></div>
<div class="footer">Made❤ 2022 <a href="https://abbytsai.github.io/">@AbbyTsai</div>
</div>
<style>
.footer{
  font-size: 10px;
  text-align:center;
  margin-top:2em;
}
#knock{
	background:black;
	color:white;
	border:5px solid black;
	border-radius:gray;
	width:3em;
	z-index:300;
	position:absolute;
    top: 8em;
	animation:knock 2s 2, close 1s 4s forwards;
}
.dialogContent{
	display:flex;
	flex-direction: column;
    align-items: center;
	padding-top:4em;
}
.year:before{
	    content: '';
    position: absolute;
    background: repeating-linear-gradient(90deg, black 0px 10px, red 10px 20px );
    border-radius: 50%;
    top: -15%;
    width: 2.3em;
    height: 1em;
}
.year{
	display: flex;
    flex-direction: column;
    position: relative;
    font-size: 36px;
    width: 1.8em;
    height: 5em;
    border: 15px solid black;
    border-radius: 25px 30px;
    align-items: center;
    justify-content: center;
    padding-top: 0.25em;
    padding-bottom: 0.25em;
    top: 0.65em;
    border-image: repeating-linear-gradient(90deg, black 0px 10px, red 10px 20px ) 1 5%;
	font-weight:bolder;
	background:lightgreen;
}
.say{
	background:pink;
	animation:fadeOut 0.5s;
	text-align:center;
	margin-bottom:0.5em;
}
@keyframes fadeOut{
	0% {
    transform: translate(1em,-1em) rotate(-0.5turn) scale(0.5);
  }
  20%,
  100% {
    transform: translateY(1em) rotate(10deg) scale(1);
  }
}
#word{
	position:absolute;
	z-index:100;
	display:flex;
	flex-direction:column;
}
#word button{
	background:lightgreen;
}
.dialog, .dialog2022{
	height:100vh;
	width:90vw;
	background:pink;
    display:none;
    position: absolute;
    right: 1em;
	z-index:300;
}
.dialog{
	top: 45em;
	margin-top:1em;
}
.dialog2022{
	top: 25em;
	margin-top:1em;
}
.dialog:target, .dialog:focus, .dialog2022:target, .dialog2022:focus{
	display:block;
}
.cardset{
	display: grid;
	grid-auto-flow: column;
	overflow-x: auto;
	background:var(--color);
	margin-left:4.8em;
	margin-top:-12em;
}
.cardset button {
	background:red;
}
.hook:nth-child(1){
	height:1.5em;
	width:1.5em;
	border-radius:50%;
	border:5px solid black;
	margin:0.5em;
	animation:knock 2s 2;
}
@keyframes knock{
	25%{transform-origin:top center;transform:translatX(5px) scale(1.1);}
	50%{transform-origin:top center;transform:translateX(-5px);}
	75%{transform-origin:top center;transform:translateX(5px) scale(1.1);}
	100%{transform-origin:top center;transform:translateX(-5px);}
}
@keyframes close{
	100%{opacity:0;}
}
.door:nth-child(1){
	justify-content: flex-end;
}
#door{
	display: flex;
	flex-direction: row;
	justify-content:center;
	height:450px;
	width: 50vw;
	border:10px solid black;
	position: relative;
	z-index:100;
	margin-left:22%;
	position:absolute;
}
.door{
	display:flex;
	height:430px;
	width: 23.5vw;
	border:10px solid black;
    align-items: center;
	background:red;
	z-index:300;
}
#doorLeft{
	animation:  move1 2s 6s forwards;
}
#doorRight{
	animation: move2 2s 6s forwards;
}
@keyframes move1{
	30%{transform-origin:top left;}
	100%{transform-origin:top left;transform:translate(1px) rotate3d(0,1,0,150deg);}
		}
@keyframes move2{
	30%{transform-origin:top right;}
	100%{transform-origin:top right;transform:rotate3d(0,1,0,-150deg);}
		}
#hello{
	display:flex;
	flex-direction: column;
    align-items: center;
	text-transform:uppercase;
	margin-top:5.5em;
	margin-bottom:12em;
	position:absolute;
}
#textSplit{
	text-align:center;
}
#textSplit span{
	font-size:36px;
	display:inline-block;
	border-radius:100% 4% 26% 0% / 100% 100% 65% 10%;
}
#textSplit span:nth-child(1){
	animation:breath 1s 8s;
}
#textSplit span:nth-child(2){
	animation:breath 1s 8.5s;
}
#textSplit span:nth-child(3){
	animation:breath 1s  9s;
}
#textSplit span:nth-child(4){
	animation:breath 1s 9.5s;
}
#textSplit span:nth-child(6){
	animation:breath 1s 10s;
}
#textSplit span:nth-child(7){
	animation:breath 1s  10.5s;
}
#textSplit span:nth-child(8){
	animation:breath 1s  11s;
}
#textSplit span:nth-child(9){
	animation:breath 1s  11.5s;
}
#textSplit span:nth-child(10){
	animation:breath 1s  12s;
}
#textSplit span:nth-child(11){
	animation:breath 1s  12.5s;
}
#textSplit span:nth-child(12){
	animation:breath 1s  13s;
}
#textSplit span:nth-child(13){
	animation:breath 1s  13.5s;
}
#textSplit span:nth-child(14){
	animation:breath 1s 14s;
}
#textSplit span:nth-child(15){
	animation:breath 1s 14.5s;
}
@keyframes breath {
  from {
    animation-timing-function: ease-out;
  }
  to {	  
    transform: scale(1.1) translateY(-0.5em) perspective(1px);
    animation-timing-function: ease-in-out;
  }
}
#hello p a, .dialogContent a{
	text-decoration:lightgreen wavy underline;
}
.dialogContent button a{
	text-decoration:none;
}
.card{
    border-image: repeating-linear-gradient(90deg, black 0px 10px, red 10px 20px ) 1 5%;
    border-style: solid;
    border-top-width: 15px;
    border-bottom-width: 15px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: space-around;
}
@media screen and (min-width:1200px){
#door{
	margin-top:2em;
}
}
@media screen and (max-width:480px){
#door{
	margin-top:4em;
}
#textSplit span{
	font-size:22px;
}
}
</style>

