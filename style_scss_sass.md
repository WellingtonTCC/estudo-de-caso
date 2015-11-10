# estudo-de-caso
//declarando variaveis

$cor: #000000;
$cor2: #8B0000;
$cor3: #191970;
$cor4: #0000FF;
$fonte1: bold 21px "Times New Roman", Arial; 
$fonte2: "trebuchet MS", Arial, Helvetica, sans-serif;
$tamanho: 30px;
$itens: 'item 1','item2','item3';



// usasndo as variaveis

h2 {
	
	font-size: $tamanho;
	color: $cor;
	text-align: center;
	font: $fonte2;
}


body{
	
	background:url(../imagens/degrade.jpg) repeat-x;
	
}

.container{
	width:100%;
	height:800px;
	border: 0px solid black;
	}
	
.cabecalho{
	width: 97%;
	height: 20%;
	border: 0px solid black;
	float:left;
	margin: 10px;
	background:url(../imagens/azul1.png);
	text-align:center;
	padding: 5px;
	}

.rodape{
	width: 97%;
	height: 10%;
	border: 1px solid black;
	float:left;
	margin: 10px;
	background:url(../imagens/azul1.png);
	}

// expressões matemáticas

.rodape p {
	font-size:2pt + 12px;
	color: #000000;
	text-align: center;
	}

// regras de aninhamentos

.menu{
	width: 18%;
	height: 70%;
	border: 2px solid blue;
	float: left;
	margin: 1%;
	background:url(../imagens/azul1.png) repeat-y;
	
		ul{
			text-decoration:none;
			color:#F00;
			font: "trebuchet MS", Arial, Helvetica, sans-serif;
			font-size: 1.3em;
			list-style:none;
			
				li{
					padding-top: 10px;
					margin: 0px 5px 5px 0px;
					
						a{
							text-decoration:none;
							color: #000000;
							
								&:hover {
									font-size: 1.5em;
									color: #C00;
								}
								
								&:active{
									background:green;
								
								}
						}
			
						
	
				}
		}
}

// antes do aninhamento 

/*
.menu {
	width: 18%;
	height: 70%;
	border: 2px solid blue;
	float: left;
	margin: 1%;
	background:url(../imagens/azul1.png) repeat-y;
	
}
.menu ul{
	text-decoration:none;
	color:#F00;
	font: "trebuchet MS", Arial, Helvetica, sans-serif;
	font-size: 1.3em;
	list-style:none;
	
	
}
.menu ul li {
	
	padding-top: 10px;
	margin: 0px 5px 5px 0px;
	
}
.menu ul li  a {
	text-decoration:none;
	color: #000000;
}
.menu ul li  a:hover {
	font-size: 1.5em;
	color: #C00;
}
*/

// diretiva @extend

%valor{
		font-size: 15px;
		font-family: arial;
		font-weigth: 600;
		color:#280382;
		text-align:justify;
		}

.centro{
	width:55%;
	height:70%;
	border:0px solid red;
	float:left;
	margin:1%;
	}

// utilizando @extend

.dir_sup{
	height:50%;
	width:48.5%;
	border:1px solid #00F;
	float:right;
	margin-left: 1%;
	@extend %valor;
	}

// expressões matemáticas

.esq_sup{
	$height:50%;
	$width:97%;
	height:$height;
	width:$width / 2;
	border:1px solid #00F;
	float:right;
	margin-left: $height - 49;
	@extend %valor;
	}

// recurso import

.dir_inf {
	@import 'importacao.scss';
	text-align:center;
	}

// funções mixins

@mixin  teste ( $cor: green, $padding: 16px )  {
	font-size: 17px;
	background:$cor;
	padding: $padding;
	}
	
h3 {
	@include teste(blue, 20px);
	}

.esq_inf {
	height:50%;
	width:48.5%;
	border:1px solid #903;
	float:right;
	margin-left: 1%;
	margin-top:1%;
	text-align: center;
	}

.direita{
	width: 18%;
	height: 70%;
	border: 1px solid #008000;
	float: left;
	margin: 1%;
	}

	// utilizando diretivas de controle if e else
	
.dir_topo{
	height:33%;
	border: 1px solid #F00;	
	text-align:center;
	background: $cor3;
	
// se a luminosidade do fundo for menor que 50 a cor do texto será branca
		@if lightness($cor3) < 50{ 
			color: #ffffff;
// se não será preta
		} @else { 
			color: #000000;
		}
}

// exemplos de laços @for

.dir_meio{
	height:33%;
	border: 1px solid #00F;
	text-align: center;
	
		@for $cor2 from 1 through 5 {
			.menu-#{$cor2}{
				background: red;
			}
		}
			$width:50px;
			@each $valor in $itens{
			$width: $width * 3;
			
			.#{$valor}: before{
				background: url('imagens/#{$valor}.jpg');
				margin-right: 4px;
				width: $width;

			
			}
			
			}	
			
			$i: 10;
			@while $i > 0 {
				.item-#{$i} {
					margin: $i + em;
					
				}
				$i: $i - 2 ;
			}
	}
	
//  Funções próprias

@function dobra($n) {
	@return $n * 2;
	}	

.dir_baixo{
	height:33%;
	border: 1px solid #309;
	text-align: center;
	font-size: dobra(10px);

	}
