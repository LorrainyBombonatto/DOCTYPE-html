# DOCTYPE-html
# calculadora
!DOCTYPE html>
<html>
<head>
	<title>Calculadora Laranja e Preta</title>
	<style>
		/* Estilo do contêiner da calculadora */
		.calculadora {
			width: 250px;
			background-color: #333; /* Fundo preto */
			padding: 20px;
			border-radius: 10px;
			box-shadow: 0 0 10px rgba(0, 0, 0, 0.5);
		}
		
		/* Estilo da tela de exibição */
		.tela {
			width: 100%;
			height: 40px;
			background-color: #FFA07A; /* Fundo laranja */
			color: #333; /* Texto preto */
			font-size: 24px;
			font-weight: bold;
			padding: 10px;
			border: none;
			border-radius: 10px;
		}
		
		/* Estilo dos botões */
		.botao {
			width: 50px;
			height: 40px;
			background-color: #FFA07A; /* Fundo laranja */
			color: #333; /* Texto preto */
			font-size: 18px;
			font-weight: bold;
			padding: 10px;
			border: none;
			border-radius: 10px;
			cursor: pointer;
		}
		
		/* Estilo dos botões ao passar o mouse */
		.botao:hover {
			background-color: #af204b; /* Fundo laranja mais claro */
		}
	</style>
</head>
<body>
	<div class="calculadora">
		<input type="text" id="tela" class="tela" readonly>
		
		<div class="botao-container">
			<button class="botao" value="7">7</button>
			<button class="botao" value="8">8</button>
			<button class="botao" value="9">9</button>
			<button class="botao" value="/">/</button>
			
			<button class="botao" value="4">4</button>
			<button class="botao" value="5">5</button>
			<button class="botao" value="6">6</button>
			<button class="botao" value="*">*</button>
			
			<button class="botao" value="1">1</button>
			<button class="botao" value="2">2</button>
			<button class="botao" value="3">3</button>
			<button class="botao" value="-">-</button>
			
			<button class="botao" value="0">0</button>
			<button class="botao" value=".">.</button>
			<button class="botao" value="=">=</button>
			<button class="botao" value="+">+</button>
			<button class="botao" value="C">C</button>
		</div>
	</div>
	
	<script>
		// Adicione eventos aos botões
		const botoes = document.querySelectorAll('.botao');
		botoes.forEach(botao => {
			botao.addEventListener('click', () => {
				// Obtenha o valor atual da tela
				const valorAtual = document.getElementById('tela').value;
				
				// Trate o clique do botão
				if (botao.value === '=') {
					// Avalie a expressão e exiba o resultado
					try {
						const resultado = eval(valorAtual);
						document.getElementById('tela').value = resultado;
					} catch (erro) {
						document.getElementById('tela').value = "Erro";
					}
				} else if (botao.value === 'C') {
					// Limpe a tela
					document.getElementById('tela').value = '';
				} else {
					// Anexe o valor do botão à tela
					document.getElementById('tela').value += botao.value;
				}
			});
		});
	</script>
</body>
</html>
