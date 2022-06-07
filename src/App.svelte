<script>
	import Card from './Card.svelte';
	import Avatar from './Avatar.svelte';
	export let name;
	let n = name;
	let challenges=[
		{index:1, name: 'stories',date:'Nov 25, 2020',description:'building-a-stories-component',url:'https://www.youtube.com/watch?v=PzvdREGR0Xw'},
		{index:2, name: 'centering',date:'Dec 16, 2020', description:'centering-in-css' ,url:'https://www.youtube.com/watch?v=ncYzTvEMCyE'},
		{index:3, name: 'sidenav',date:'Jan 21, 2021',description:'building-a-sidenav-component' ,url:'https://www.youtube.com/watch?v=uiZqDLqjGRY'},
		{index:4, name: 'tabs',date:'Feb 17, 2021',description:'building-a-tabs-component',url:'https://www.youtube.com/watch?v=mMBcHcvxuuA'},
		{index:5, name: 'settings',date:'Mar 17, 2021',description:'building-a-settings-component' ,url:'https://www.youtube.com/watch?v=dm7gnp6eh3Q'},
		{index:6, name: 'split-Text',date:'Apr 20, 2021',description:'building-split-text-animations' ,url:'https://www.youtube.com/watch?v=3hvN7bkjZBk'},
		{index:7, name: 'media-scroller',date:'May 12, 2021',description:'building-a-media-scroller-component' ,url:'https://www.youtube.com/watch?v=jmLdZY_Lo1k'},
		{index:8, name: 'color-schemes',date:'Jun 9, 2021',description:'building-a-color-scheme',url:'https://www.youtube.com/watch?v=oHcTn83M1ls' },
		{index:9, name: 'breadcrumbs',date:'July 14, 2021',description:'building-a-breadcrumbs-component',url:'https://www.youtube.com/watch?v=kHL3gxAlvK8' },
		{index:10, name: 'switch',date:'Aug 11, 2021',description:'building-a-switch-component',url:'https://www.youtube.com/watch?v=_KqccADghcA' },
		{index:11, name: 'split-buttons',date:'Sep 1, 2021', description:'building-a-split-button-component',url:'https://www.youtube.com/watch?v=Qcpru-fIgwk' },
		{index:12, name: 'multi-select',date:'Oct 13, 2021',description:'building-a-multi-select-component',url:'https://www.youtube.com/watch?v=x0aCdLDZ8BM' },
		{index:13, name: 'game-menu',date:'Oct, 2021',description:'building-a-game-menu-component',url:'https://www.youtube.com/watch?v=HCsV8u-KYUw' },
		{index:14, name: 'toast',date:'Dec 8, 2021',description:'building-a-toast-component' ,url:'https://www.youtube.com/watch?v=R75ZVW4LW5o'},
		{index:15, name: 'theme-switch',date:'Jan 19, 2022',description:'building-a-theme-switch-component',url:'https://www.youtube.com/watch?v=kZiS1QStIWc' },
		{index:16, name: 'svg-favicon',date:'Feb 9,2022', description:'building-an-adaptive-favicon',url:'https://www.youtube.com/watch?v=4pJahmCR8kQ' },
		{index:17, name: 'loading-bar',date:'Mar 16, 2022',description:'building-a-loading-bar-component' ,url:'https://www.youtube.com/watch?v=TD1QxlGgIPk'},
		{index:18, name: 'dialog',date:'Apr 13, 2022', description:'building-a-dialog-component' ,url:'https://www.youtube.com/watch?v=GDzzIlRhEzM'},
		{index:19, name: 'buttons',date:'May 18, 2022', description:'building-a-button-component' ,url:'https://www.youtube.com/watch?v=aJNq-b1zlog&t'}
	];
let array1=[
		{ id: '@AbbyPTsai', word: 'inspired!', url:'https://twitter.com/AbbyPTsai/status/1417046553529782272'},
		{ id: '@gnehcwu', word: 'inspired!', url:'https://twitter.com/gnehcwu/status/1387080622271864832'},
		{ id: '@VarunKS20161856', word: 'Thanks for a fun challenge!', url:'https://twitter.com/VarunKS20161856/status/1504761714323038214'},
		{ id: '@BrettJephson', word: 'really enjoying!', url:'https://twitter.com/BrettJephson/status/1460575837229654018'},
		{ id: '@roman_czerkies', word: 'thanks as always!', url:'https://twitter.com/roman_czerkies/status/1409971197786292224'},
		{ id: '@Clement17', word: 'how hard front end can be!', url:'https://twitter.com/Clement17/status/1447953993611759617'},
		{ id: '@giglobus', word: 'Thought Japanese 3D.', url:'https://twitter.com/giglobus/status/1458517228106784774'},
		{ id: '@css', word: 'keep bookmarking!', url:'https://twitter.com/css/status/1455648044347703302'},
		{ id: '@chriscoyier', word: 'That’s what real front-end development is!', url:'https://css-tricks.com/gui-challenges/'},
		{ id: '@tomayac', word: 'Another great episode.I love.', url:'https://twitter.com/tomayac/status/1415592428611018755'},
		{ id: '@hackertabdev', word: 'stars!', url:'https://twitter.com/hackertabdev/status/1515783430885179395'},
		{ id: '@EdwardAEzekiel', word: 'nice!css concepts in a concise way.', url:'https://twitter.com/EdwardAEzekiel/status/1495212247165149189'},
		{ id: '@roblevintennis', word: 'amazeballs! learning a lot from ya.', url:'https://twitter.com/roblevintennis/status/1516597976973647872'},
		{ id: '@LarsRoettig', word: 'amazing stuff!', url:'https://twitter.com/LarsRoettig/status/1468571960586256384'},
		{ id: '@geoffrich_', word: 'learning materials I really enjoy!', url:'https://twitter.com/geoffrich_/status/1372217555570462720'},
		{ id: '@MVSde', word: 'fantastic!', url:'https://twitter.com/MVSde/status/1392531455645999109'},
		{ id: '@alexandermchan', word: 'fantastic for anyone!', url:'https://twitter.com/alexandermchan/status/1443945888104148998'},
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
	},3000)
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
	<div id='hello'>
	<h3>Hello</h3>
	<div id='textSplit'>
	<Avatar height={60} width={50}/>
	<div>
	{#each n as name, i}
	{#if i===3}
		<span>&nbsp;&nbsp;</span>
	{:else}
		<span>
			{n[i]}
		</span>
	{/if}
	{/each}
	</div>
	</div>
	<p>learn more at <a href="https://github.com/argyleink/gui-challenges">Here.</a></p>
	</div>
</div>

<div id='place'>
	<div id="word">
	<button on:click={add}>What folks say</button>
	<div id='saygroup' >
	{#each newarray as a, i}
	<div class='say'>
		<img src='https://unavatar.io/twitter/{a[0].substring(1)}' alt="@AbbyPTsai" size="20" height="20" width="20">
		<div class='say1'>{a[1]}</div>
		<div class='say2'><a href={a[2]}>{a[0]}</a></div>
	</div>
	{/each}
	</div>
	</div>

	<div id='learn'>
	<h1>a place, </h1>
	<h2>we learn.</h2>
	<h2>we play.</h2>
	<h2>we grow.</h2>
	<h3>"ALL" together.</h3>
	</div>
</div>

<div style='margin-top:10em;'>
<div id='here'>
Seriously, what's going on.
</div>
<p class='year'>
<span>2</span><span>0</span><span>2</span><span>2</span>
</p>

<div class='cardset'>
	{#each challenges as challenge, i}
	{#if challenge.date.includes('2022')}
	<Card>
		<div><h1>{challenge.name}</h1></div>
		<div class='avatar'>
		<Avatar width={30} height={40} />
		</div>
	<button><a href="#dialog{i}">open</a></button>
	<div class="dialog" id="dialog{i}">
	<div class='dialogContent'>
		<div><h1>{challenge.name}</h1></div>
		<div>{challenge.date}</div>
		<div class='description'>{challenge.description}</div>
	<div id='refgroup'>
		<div class='ref'><a href='https://web.dev/{challenge.description}/'>article</a></div>
		<div class='ref'><a href='https://gui-challenges.web.app/{challenge.name}/dist/'>demo</a></div>
		<div class='ref'><a href={challenge.url}>YouTube</a></div>
	</div>
	<div class='avatar'>
	<Avatar width={30} height={40} />
	</div>
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
<div class='avatar'>
<Avatar width={30} height={40} />
</div>
<button><a href="#dialog{i}">open</a></button>
<div class="dialog" id="dialog{i}">
<div class='dialogContent'>
<div><h1>{challenge.name}</h1></div>
<div>{challenge.date}</div>
<div class='description'>{challenge.description}</div>
<div id='refgroup'>
<div class='ref'><a href='https://web.dev/{challenge.description}/'>article</a></div>
<div class='ref'><a href='https://gui-challenges.web.app/{challenge.name}/dist/'>demo</a></div>
<div class='ref'><a href={challenge.url}>YouTube</a></div>
</div>
<div class='avatar'>
<Avatar width={30} height={40} />
</div>
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
<div class='avatar'>
<Avatar width={30} height={40} />
</div>
<button><a href="#dialog{i}">open</a></button>
<div class="dialog" id="dialog{i}">
<div class='dialogContent'>
<div><h1>{challenge.name}</h1></div>
<div>{challenge.date}</div>
<div class='description'>{challenge.description}</div>
<div id='refgroup'>
<div class='ref'><a href='https://web.dev/{challenge.description}/'>article</a></div>
<div class='ref'><a href='https://gui-challenges.web.app/{challenge.name}/dist/'>demo</a></div>
<div class='ref'><a href={challenge.url}>YouTube</a></div>
</div>
<div class='avatar'>
<Avatar width={30} height={40} />
</div>
<button><a href="#cardset">back</a></button>
</div>
</div>
</Card>
{/if}
{/each}
</div>

</div>
<div class="footer">
<div>Inspired ❤ by <a href="https://twitter.com/argyleink">@AdamArgyle</a></div>
<div>copyright 2022 <a href="https://twitter.com/AbbyPTsai">@AbbyTsai</a></div>
</div>
<style>
#refgroup{
	display: grid;
    grid-template-columns: repeat(3, 1fr);
    justify-items: center;
    margin-top: 1em;
	margin-bottom:2em;
    border-image: repeating-linear-gradient(90deg, black 0px 10px, red 10px 20px ) 1 5%;
    border-style: solid;
    border-top-width: 10px;
    border-bottom-width: 10px;
    width: 70vw;
	font-weight:bold;
}

.ref{
	background:lightgreen;
	margin-bottom: 3px;
	border-radius: 59% 72% 5% 14% / 28% 40% 0% 13%;
    font-size: 24px;
}

.avatar{
	position:relative;
	top:-0.4em;
	left:0.1em;
	z-index:100;
}

.avatar:hover{
	transform:rotate(-10deg);
	transform-origin:left left;
}

.say img{
	border-radius:50%;
	border:2px solid black;
}

#here{
	text-align: center;
    background: black;
	color:white;
    border-bottom: 10px solid white;
	font-family:'Amatic SC', cursive;
	font-size:52px;
	font-weight:bolder;
}

#place{
	margin-top:34em;
	display:flex;
	flex-direction:column;
	align-items:center;
	justify-content:flex-start;
	line-height:0.8em;
	text-align:center;
}

.footer{
  font-size: 10px;
  text-align:center;
  margin-top:4em;
}

#knock{
	background:black;
	color:white;
	border:5px solid black;
	border-radius:gray;
	width:3em;
	z-index:300;
	position:absolute;
    top: 6.5em;
	animation:knock 2s 2, close 1s 4s forwards;
	font-family:'Amatic SC', cursive;
	border-radius:83% 59% 26% 87% / 63% 73% 2% 90%;
	font-weight:bolder;
	text-align:center;
	font-size:24px;
}

.dialogContent{
	heigth:300px;
	width:70vw;
	display:flex;
	flex-direction: column;
    align-items: center;
	text-align:center;
	margin-right:auto;
	margin-left:auto;
	background:pink;
	border-image: repeating-linear-gradient(90deg, black 0px 10px, red 10px 20px ) 1 25%;
    border-style: solid;
    border-top-width: 2em;
    border-bottom-width: 2em;
}

.year{
	display: flex;
    flex-direction: column;
    position: absolute;
    width: 3em;
    height: 150px;
    align-items: center;
    justify-content: center;
    padding-top: 0em;
    padding-bottom: 0em;
    border-image: repeating-linear-gradient(90deg, black 0px 10px, red 10px 20px ) 1 15%;
    font-weight: bolder;
    background: black;
    border-style: solid;
    border-top-width: 2em;
    border-bottom-width: 2em;
    border-radius: 25px 30px;
    margin-top: -0.1em;
    color: white;
}

.say{
	background: pink;
    animation: fadeOut 0.5s;
    border-radius:57% 90% 64% 66% / 91% 42% 84% 13%;
	padding:0.5em;
}

.say1{
	font-size:20px;
	font-weight: bolder;
}

.say2{
	font-size:12px;
}

#saygroup{
	display:grid;
	gap:1em;
	justify-items:center;
}

@keyframes fadeOut{
0% {
    transform: translate(1em,-1em) rotate(-0.5turn) scale(0.5);
  }
  20%,100% {
    transform: translateY(1em) rotate(10deg) scale(1);
  }
}

#word{
	position:absolute;
	z-index:100;
	display:flex;
	flex-direction:column;
	align-items:center;
}

#word button{
	background:lightgreen;
	border-radius:52% 70% 48% 1% / 90% 41% 27%;
	height:4em;
	width:10em;
	font-size:28px;	
}

#word button:before {
	content: 'click';
    position: absolute;
	height:1.5em;
	width:3em;
	background:pink;
	border-radius:83% 59% 26% 87% / 63% 73% 2% 90%;
	top:0em;
	left:0.3em;
	transform: rotate(-10deg);
}

button:hover, .ref:hover {
 box-shadow:4px 5px gray;
 transform:translateY(1px);
}

#learn{
	padding-top:5em;
	border-bottom:4em solid red;
	border-radius:57% 90% 64% 66% / 91% 42% 84% 13%;
	width:10em;
}

.dialog{
	height:100vh;
	width:90vw;
	background:lightgray;
    display:none;
    right: 1em;
	z-index:300;
	position:fixed;
	top:0;
}

.dialog:target, .dialog:focus{
	display:block;
}

button, .description {
	font-weight:bold;
}

.cardset button {
	background:red;
	border-radius:52% 70% 48% 1% / 90% 41% 27%;
	position: relative;
    top: -2em;
}

.cardset a{
	font-size:28px;
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
	font-family: 'Amatic SC', cursive;
	font-weight:bolder;
}

#textSplit span{
	font-size:54px;
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

#textSplit span:nth-child(5){
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

#hello p a, .dialogContent a, .footer a{
	text-decoration:lightgreen wavy underline;
}

.dialogContent button a, a{
	text-decoration:none;
}

#hello p {
	text-align:center;
}

@media screen and (min-width:1200px){
#door{
	margin-top:4em;
}
}

@media screen and (min-width:480px){
#door{
	margin-top:0.8em;
}
.cardset{
	display: grid;
	grid-auto-flow: column;
	overflow-x: auto;
	margin-left:3em;
	justify-content: start;
}
.dialogContent{
	margin-top:5%;
}
}

@media screen and (max-width:480px){
#door{
	margin-top:4em;
}
#textSplit span, #here{
	font-size:32px;
}
.dialogContent{
	margin-top:40%;
}
.cardset{
  display: grid;
  grid: 1fr / auto-flow 100%;
  overflow-x: auto;
  scroll-snap-type: x mandatory;
  overscroll-behavior: contain;
  touch-action: pan-x;
  margin-left:3em;
}
}
</style>