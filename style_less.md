# estudo-de-caso
body{
	
	background:url(../imagens/degrade.jpg) repeat-x;
	
}


// Declarando as Variáveis 

@cor:#000000;
@cor2: #8B0000;
@cor3: #191970;
@fonte1:bold 21px "Times New Roman", Arial; 
@fonte2: "trebuchet MS", Arial, Helvetica, sans-serif;
@tamanho: 30px;


// Usando as Variáveis 

h2{
	
	font-size:@tamanho;
	color:@cor;
	text-align: center;
	font:@fonte2;
}
p{
	font: @fonte1;
	color: @cor2;
	text-align: center;
}

// Mixins

.radius(@corner: 5px){
	border-radius: @corner;
	-webkit-border-radius: @corner;
	-moz-border-radius: @corner;
	-o-border-radius:@corner;

}

h3{
	background:#808080;
	padding: 10px;
	color: @cor2;
	.radius(10px);
	text-align:center;

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

.centro{
	width:55%;
	height:70%;
	border:0px solid red;
	float:left;
	margin:1%;
	
}

.esq_sup, .dir_sup {
	height:50%;
	width:48.5%;
	border:1px solid #00F;
	float:right;
	margin-left: 1%;
	
	
}

.esq_inf{
	@height:50%;
	@width:97%;
	height:@height;
	width:@width / 2;
	border:1px solid #00F;
	float:right;
	margin-left: @height - 49;
	margin-top:1%;
	
	}
	
// recurso import

.dir_inf {
	@import 'importacao.less';
	}
	
.direita{
	width: 18%;
	height: 70%;
	border: 1px solid #008000;
	float: left;
	margin: 1%;
	
}
// funções de cores
.dir_topo{
	height:33%;
	border: 1px solid #F00;	
	text-align:center;
	background: @cor3;

		p{
		
		color: lighten(@cor3, 80%)
		}
	}

// diretiva extend

.valor{
		font-size: 15px;
		font-family: arial;
		font-weigth: 600;
		color:#280382;
		text-align:justify;
		}

.dir_meio{
	height:33%;
	border: 1px solid #00F;
	&:extend(.valor);
}
.dir_baixo{
	height:33%;
	border: 1px solid #309;
}



