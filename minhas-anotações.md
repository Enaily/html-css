



Expressão Regular(RegEx):

^	Início da string (começo do texto)

\\(	Representa um parêntese de abertura literal (

\\)	Representa um parêntese de fechamento literal )

\\d	Qualquer dígito numérico de 0 a 9

{2}	Exatamente 2 ocorrências do elemento anterio



**significa**:

^ → início do texto

\\( → abre parêntese

\\d{2} → dois números

\\) → fecha parêntese



todo botão de rádio que faz parte do mesmo grupo, receber o mesmo "name" e não "id"



<form>



Cria um formulário para enviar dados.



action="cadastro.php"



Define para onde os dados serão enviados.



method="get"



Define a forma de envio.



O método GET envia os dados pela URL.



Exemplo:



cadastro.php?sexo=F\&esfut=on



POST



Esconde os dados da URL.



Usado para:



senhas;

cadastros;

informações sensíveis.

***Todo formulário que usa GET, tem um limite até 3mil bytes. passando disso ele não envia os dados, então ao invés de GET, usa o método POST(ex.foto).***




autocomplete="on"



Permite que o navegador sugira informações já digitadas anteriormente.



Exemplo:



Ao digitar o nome, o navegador pode completar automaticamente.



. Primeiro Fieldset

<fieldset>



Agrupa elementos relacionados.



Cria uma "caixinha".



Visualmente:



┌──────────────┐

│ Sexo         │

│ ○ Masculino  │

│ ● Feminino   │

└──────────────┘





Legenda

<legend>Sexo</legend>



Título da caixinha.



Resultado:



Sexo





<input>



Cria um campo de entrada.



type="radio"



Cria uma bolinha de seleção.



Exemplo:



○ Masculino

○ Feminino



Só permite escolher uma opção.





name="sexo"



Nome enviado ao servidor.



Exemplo:



sexo=M



ou



sexo=F



Todos os radios com o mesmo name pertencem ao mesmo grupo.



Por isso só é possível marcar um.



id="isxmas"



Identificador único do elemento.



Serve para ligar o input ao label.



value="M"



Valor enviado.



Se marcar Masculino:



sexo=M







Label Masculino

<label for="isxmas">Masculino</label>

<label>



Texto associado ao campo.



for="isxmas"



Liga o texto ao input cujo id é:



id="isxmas"



Assim, ao clicar em "Masculino", a bolinha também é marcada.



7\. Quebra de linha

<br>



Pula para a próxima linha.



8\. Radio Feminino

<input type="radio"

&#x20;      name="sexo"

&#x20;      id="isxfem"

&#x20;      value="F"

&#x20;      checked>



Igual ao anterior.



Diferença:



checked



Deixa marcado automaticamente.



Resultado:



○ Masculino

● Feminino

9\. Segundo Fieldset

<fieldset>



Nova caixinha.



Agrupa os esportes.



10\. Legenda

<legend>Esportes favoritos</legend>



Título da segunda caixinha.



11\. Checkbox



Exemplo:



<input type="checkbox"

&#x20;      name="esbas"

&#x20;      id="iesbas"

&#x20;      checked>

type="checkbox"



Cria quadradinhos de marcação.



Exemplo:



☑ Basquete

☑ Futebol

☐ Natação

☐ Tênis



Diferente do radio:



Radio → apenas 1 opção.

Checkbox → várias opções.

name="esbas"



Nome enviado.



Se marcado:



esbas=on

id="iesbas"



Identificador.



checked



Já vem marcado.



12\. Labels dos esportes



Exemplo:



<label for="iesbas">Basquete</label>



Ao clicar no texto "Basquete", o quadradinho é marcado ou desmarcado.



13\. Botão Enviar

<input type="submit" value="Enviar">

type="submit"



Envia o formulário.



value="Enviar"



Texto exibido no botão.



Resultado:



\[ Enviar ]

14\. Botão Limpar

<input type="reset" value="Limpar">

type="reset"



Apaga tudo o que o usuário selecionou e volta ao estado inicial.



value="Limpar"



Texto do botão.



Resultado:



\[ Limpar ]

Fluxo completo do formulário

O usuário escolhe o sexo.

Marca os esportes favoritos.

Clica em Enviar.

O navegador envia os dados para:

cadastro.php



Usando o método GET.



Exemplo de URL gerada:



cadastro.php?sexo=F\&esbas=on\&esfut=on



Isso significa:



sexo=F → Feminino;

esbas=on → Basquete marcado;

esfut=on → Futebol marcado.

Resumo rápido

Expressão	Função

<form>	Cria o formulário

action	Define para onde enviar

method="get"	Envia pela URL

autocomplete	Sugere dados já usados

<fieldset>	Agrupa campos

<legend>	Título do grupo

type="radio"	Escolha única

type="checkbox"	Múltiplas escolhas

name	Nome enviado ao servidor

id	Identificador único

value	Valor enviado

checked	Campo marcado por padrão

<label>	Texto associado ao campo

<br>	Quebra de linha

type="submit"	Envia o formulário

type="reset"	Limpa o formulário







***O que é RegEx?***



RegEx significa Regular Expression (Expressão Regular).



É uma forma de criar padrões de texto para:



✔️ validar informações;

✔️ procurar palavras;

✔️ substituir partes de textos;

✔️ filtrar dados;

✔️ verificar formatos específicos.



Pense nela como uma "regra" para dizer:



"Eu quero encontrar textos que sigam exatamente este padrão."



Exemplo simples



Imagine que você queira encontrar a palavra:



casa



A RegEx seria:



casa



Ela encontra:



A casa é bonita.



Mas não encontra:



O apartamento é bonito.

Onde a RegEx é usada?



Ela aparece em praticamente todas as linguagens:



HTML (atributo pattern)

JavaScript

PHP

Python

Java

C#

Bancos de dados

Editores de texto como VS Code

No HTML



Você pode validar um campo usando RegEx.



Exemplo: permitir somente 5 números.



<input type="text" pattern="\[0-9]{5}">



Se o usuário digitar:



✅



12345



aceita.



❌



1234



não aceita.



❌



12abc



não aceita.



Os símbolos mais importantes

1\. . (ponto)



Significa:



qualquer caractere.



RegEx:



c.sa



Encontra:



✅



casa

cosa

cesa

c9sa



Não encontra:



❌



caasa

2\. ^



Significa:



início do texto.



Exemplo:



^Ana



Encontra:



✅



Ana Clara



Não encontra:



❌



Meu nome é Ana

3\. $



Significa:



final do texto.



Exemplo:



Silva$



Encontra:



✅



Maria Silva



Não encontra:



❌



Silva Maria

4\. \[]



Significa:



qualquer caractere dentro dos colchetes.



Exemplo:



\[abc]



Encontra:



✅



a

b

c

Intervalos

\[a-z]



letras minúsculas.



\[A-Z]



maiúsculas.



\[0-9]



números.



Exemplo:



\[A-Z]\[0-9]



aceita:



✅



A1

B9

Z5

5\. +



Significa:



uma ou mais vezes.



Exemplo:



a+



Encontra:



✅



a

aa

aaa

aaaa

6\. \*



Significa:



zero ou mais vezes.



Exemplo:



a\*



Aceita:



✅



(nada)

a

aa

aaa

7\. ?



Significa:



opcional.



Exemplo:



colou?r



Encontra:



✅



color

colour

8\. {}



Define quantidade.



Exemplo:



\[0-9]{3}



Exatamente:



3 números.



Aceita:



✅



123

987

Quantidade mínima e máxima

\[0-9]{2,4}



Aceita:



✅



12

123

1234



Não aceita:



❌



1

12345

9\. \\d



Atalho para número.



Equivale a:



\[0-9]



Exemplo:



\\d{4}



4 números.



10\. \\w



Significa:



letras, números e underline.



Equivale aproximadamente a:



\[A-Za-z0-9\_]

11\. \\s



Significa:



espaço em branco.



Inclui:



espaço;

tabulação;

quebra de linha.

Exemplos úteis

CEP brasileiro

^\\d{5}-?\\d{3}$



Aceita:



✅



01234-567

01234567

Telefone

^\\d{10,11}$



Aceita:



✅



11987654321

1134567890

Somente letras

^\[A-Za-zÀ-ÿ\\s]+$



Aceita:



✅



Ana Clara

José

Marília

Senha forte



Pelo menos:



8 caracteres;

1 letra maiúscula;

1 minúscula;

1 número.



Exemplo:



^(?=.\*\[a-z])(?=.\*\[A-Z])(?=.\*\\d).{8,}$



Aceita:



✅



Senha123

Brasil2026

RegEx em JavaScript



Verificar CPF com apenas 11 dígitos:



let cpf = "12345678901";



if (/^\\d{11}$/.test(cpf)) {

&#x20;   console.log("CPF válido");

}

RegEx em HTML



Validar um usuário com 3 a 15 letras:



<input

&#x20;   type="text"

&#x20;   pattern="\[A-Za-z]{3,15}"

&#x20;   title="Digite entre 3 e 15 letras">

Como aprender RegEx?



A melhor forma é praticar criando validações reais:



CEP;

telefone;

e-mail;

senha forte;

CPF;

nome completo;

usuário do sistema.

Uma dica importante



No começo, RegEx parece "uma língua alienígena". Até programadores experientes precisam consultar exemplos. O segredo é entender o significado dos símbolos e praticar aos poucos.



Como você está estudando HTML/CSS e pretende avançar para JavaScript e PHP, aprender RegEx agora vai ajudar bastante quando começar a trabalhar com formulários e validação de dados.


*** ***

Media Query= Media Type + Media Feature
media types= tipos de media
Media Feature= características de media

meida types são indicadas sem ()
Media Feature são indicadas entre ()

***📱 Teoria do Mobile First (resumida)***

Mobile First é uma abordagem de desenvolvimento em que o site é criado primeiro para telas pequenas, como celulares. Depois, usando Media Queries, o layout é adaptado para tablets e computadores. Essa técnica melhora a responsividade, o desempenho e a experiência do usuário em dispositivos móveis.

*** 📱 Breakpoints ***

São os tamanhos de tela onde o layout do site “muda”.
Exemplo:

600px (celular)
768px (tablet)
992px (desktop)

👉 Ou seja: é o ponto onde a tela quebra o layout atual e precisa de ajuste.

*** Justify-content***=(é utilizado quando usa o wrap/wrap-reverse) alinha conteúdo dentro do eixo principal
*** align-items***= alinha itens dentro do eixo transversal
*** align-content***=(é utilizado quando usa o wrap/wrap-reverse) alinha itens no eixo transversal mais quando eles estão empacotados.


***align-content***: por padrão, o valor é stretch, ou seja, as linhas de itens são esticadas para ocupar todo o espaço disponível no eixo transversal.

***align-content: space-around;***

→ Distribui as linhas com espaço ao redor de cada uma.
→ Há espaço antes da primeira linha, entre as linhas e depois da última.
→ Funciona apenas quando existem várias linhas (flex-wrap: wrap).

No space-around, o espaço entre os itens é o dobro do espaço existente nas extremidades (start e end).

💡 Macete para decorar:

space-between → sem espaço nas extremidades.
space-around → metade do espaço nas extremidades.
space-evenly → todos os espaços são exatamente iguais (entre itens e nas extremidades).
quando criamos container flaxbox a parte de fora é flex e a parte de dentro não é flex.


todo item em flexbox terá order 0 por padrão

*** align-self *** se aplica aos itens e vai funcionar diretamente no
cross-axis(eixo transversal)

*** flex-basis: auto *** 
a largura dos itens pra cada elemento é dada através do tamanho do seu conte údo. 

***flex-grow ***  → define o quanto o item pode crescer.

*** flex-shrink *** → define o quanto o item pode encolher. 

flex-grow: 1
→ Permite que o item cresça para ocupar o espaço livre disponível no contêiner.

flex-shrink: 1
→ Permite que o item encolha quando faltar espaço no contêiner.

flex= flex-grow + flex-shrink + flex-basis



