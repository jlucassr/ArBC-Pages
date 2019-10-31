# Histórico de Versões

|Data|Versão|Descrição|Autor|
-|-|-|-
21/09|1.0.0| Inicio do Documento | Marcelo Victor e João Paulino |
22/09|1.0.1| Correção dos tópicos| Marcelo Victor e João Paulino |


## 1. <a name="1">Introdução</a>

### 1.1 <a name ="1_1">Front_End</a>

#### 1.1.1 <a name ="1_1_1">Vue</a>

<p align="justify"> &emsp;&emsp; O vue é uma estrutura progressiva para a construção de interfaces com o usuário. Ao contrário de outras estruturas monolíticas, o Vue é projetado desde o início para ser adotado de forma incremental. A biblioteca principal é focada apenas na camada de visualização e é fácil de entender e integrar com outras bibliotecas ou projetos existentes. Por outro lado, o Vue também é perfeitamente capaz de alimentar aplicativos sofisticados de página única quando usado em combinação com ferramentas modernas e bibliotecas de suporte. </p>

#### 1.1.2 <a name ="1_1_2">Aframe</a>

<p align="justify"> &emsp;&emsp; O aframe-ar.js, é uma biblioteca com o objetivo de permitir que o desenvolvedor aplique em seu projeto realidade aumentada de forma fácil e rápida através de tags, que viabilizam o uso da câmera do aparelho para o reconhecimento de marcadores ou até código de barras. </p>

#### 1.1.3 <a name ="1_1_3">Aframe-gif-shader</a>

<p align="justify"> &emsp;&emsp; O aframe-gif-shader tem como função permitir que seja visualizado Gifs quando apontado a câmera do dispositivo para um marcador </p>

#### 1.1.4 <a name ="1_1_4">Axios</a>

<p align="justify"> &emsp;&emsp; O axios tem como função consumir e exibir dados de uma API. Há várias maneiras de se fazer isso, mas a maneira mais popular é usando axios, um cliente HTTP baseado em Promises, que é um objeto usado para processamento assíncrono. </p>

### 1.2 <a name ="1_2">Back_End</a>

#### 1.2.1 <a name ="1_2_1">Django</a>
<p align="justify"> &emsp;&emsp; Será usado como o principal agente encapsulador das seguintes sub bibliotecas. </p>

#### 1.2.2 <a name ="1_2_2">Pillow</a>
<p align="justify"> &emsp;&emsp; Python Imaging Library é uma biblioteca da linguagem de programação Python que adiciona suporte à abertura e gravação de muitos formatos de imagem diferentes. Basicamente o propósito desta biblioteca é auxiliar no armazenamento de ilustrações no banco de dados. </p>

#### 1.2.3 <a name ="1_2_3">Django-cors-headers</a>
<p align="justify"> &emsp;&emsp; Esta biblioteca permite que o servidor django seja acessado em outros domínios. </p>

#### 1.2.4 <a name ="1_2_4">Django-redis</a>
<p align="justify"> &emsp;&emsp; Biblioteca focada na otimização com relação as requisições de dados da aplicação, ou seja a mesma funciona como um cache entre o servidor e algum cliente qualquer. </p>

#### 1.2.5 <a name ="1_2_5">Djangorestframework</a>
<p align="justify"> &emsp;&emsp; É uma ferramenta para construir Web APIs , dado que o front fará requisições http para o servidor django. </p>

#### 1.2.6 <a name ="1_2_6">Coreapi</a>
<p align="justify"> &emsp;&emsp; Core API é uma biblioteca focada em facilitar a criação de DOMs (Document Object Model) para os objetos criados na aplicação , dado que estes serão enviados para o front-end.
</p>

#### 1.2.7 <a name ="1_2_7">Werkzeug</a>
<p align="justify"> &emsp;&emsp; Werkzeug é uma biblioteca que contém utilitários para WSGI(Web Server Gateway Interface).
	WSGI é um padrão Python descrito na PEP 3333. </p>

#### 1.2.8 <a name ="1_2_8">Psycopg2-binary</a>
<p align="justify"> &emsp;&emsp; É uma biblioteca, em sua maior parte escrita em C , para encapsular a comunicação do PostgreSQL com a aplicação em questão. </p>

#### 1.2.9 <a name ="1_2_9">Awesome-slugify</a>
<p align="justify"> &emsp;&emsp; Biblioteca focada na parte de auxiliar na criação de uma URL que pode ser legível tanto para humanos quanto para mecanismos de busca, ou seja, torna as URLs mais "amigáveis". </p>

## 2. <a name="2">Integração</a>
A iteração ideal entre o front-end e o back-end , dar-se-á da seguinte forma:
	<ol>
		<li>
			O front-end irá detectar uma letra/palavra com o auxilio do AFrame e Ar.js , montará um texto referente aos símbolos detectados.
		</li>
		<li>
		 O front-end com auxilio do Axis e Djangorestframework , solicitará através de uma requisição http uma ilustração referente ao texto detectado.
		 </li>
		<li>
		 O back-end processará a requisição, enviada pelo front, procurando pelo texto enviado na base de dados (que esta integrada com o django pelo psycopg2-binary).
		 </li>
		<li>
		 Caso a base de dados encontre o texto, o mesmo retornará a imagem ( que estava armazenada na base de dados com auxílio do pillow).
		 </li>
		<li>
		 Será montado um arquivo json (com auxilio do core-api) e retornado para o front-end.
		</li>
		<li>
		 O front-end receberá a animação e renderizará a mesma na tela do usuário com o AFrame.
		</li>
	</ol>
