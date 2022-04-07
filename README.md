<!DOCTYPE html>
<html>
<head>
	<title>Prova Javascript GitHub</title>
	<meta charset="utf-8" />
   <link href="cadastro.css" rel="stylesheet"/>

		<script>
			//armazena informações das variaveis para mostrar na tela 
			totalUsuarios = 0;

			function criarUsuario() {
				let usuario = document.getElementById("usuario").value; 
				let fone = document.getElementById("fone").value;
				let data = document.getElementById("data").value;
				let data_brasileira = data.split('-').reverse().join('/'); //transforma a data default em brasileira
				let nota = document.getElementById("nota").value;
				let n1 = parseInt(nota); // transforma um string em número
				let nota2 = document.getElementById("nota2").value;
				let n2 = parseInt(nota2); // transforma um string em número
				let media = (n1 + n2)/2; //recebe e soma dois números depois faz a médida
					
					//verifica se existe campo vazio
					if(usuario && fone && data && nota && nota2 !="") {

				alert ('Dados cadastrados com sucesso');

				//retorna na  tela os dados informados 	
				document.getElementById("lista").innerHTML += "<br>O aluno: " + usuario + "<br>Nascido em: " + data_brasileira + "<br>Tem o telefone número: " + fone + "<br> Sua média é: " + media + "<br>";
				totalUsuarios++;
				}
					else {
						alert ('Por favor ! Preencha TODOS os campos !');
						document.getElementById('usuario').focus();
					}

			}

		</script>

</head>
<body>


	<div>

		<div style="width:50%;float:left">

			<p> Formulário para cadastro de alunos </p>
 
		<div>
			<label>Nome do Aluno :</label>
			<input id="usuario" type="text" placeholder="Digite um nome"/>
		</div>	

		<div>
			<label> Telefone :</label>
	        <input id="fone" type="number" placeholder="123456789" min="0" max="999999999" oninput="validity.valid||(value='');" >
		</div>

		<div>
			<label> Nascimento  :</label>
  			<input  id="data" type="date" ><br>
  		</div>

  		<div>
			<label>Primeira Nota :</label>
			<input id="nota" type="number" placeholder="De 0 a 10" min="0" max="10" oninput="validity.valid||(value='');">
		</div>

		<div>
			<label>Segunda  Nota :</label>
			<input id="nota2" type="number" placeholder="De 0 a 10" min="0" max="10" oninput="validity.valid||(value='');">
		</div>
	
		<div>
			<button onclick="criarUsuario()" type="submit">Cadastrar aluno</button>
		</div>

		
	</div>
		<div style="width:50%;float:right">

			<div>
				<p>Alunos cadastrados:</p>
				<div id="lista"></div>
			</div>

		</div>
</div>
</body>
</html>


