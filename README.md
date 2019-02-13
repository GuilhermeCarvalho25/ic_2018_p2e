<!--
Projecto segunda época de Introdução à Computação 2018/2019 (c) by Pedro Serra

Projecto de segunda época de Introdução à Computação 2018/2019 is licensed under a
Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License.

You should have received a copy of the license along with this
work. If not, see <http://creativecommons.org/licenses/by-nc-sa/4.0/>.
-->

# Projecto de segunda época de Introdução à Computação 2018/2019


## Parte 1 [16 Valores]

Pretende desenvolver-se um programa para gerir passwords e ajudar na criação de novas passwords. O programa deverá aceitar como argumento o nome de um ficheiro que contém as passwords gravadas. Em seguida deverá apresentar um menu onde é possível listar as passwords/usernames e criar novas passwords quer por insersão manual ou sugeridas automaticamente pelo programa.

O programa deverá permitir também eliminar registos ou modificar registos existentes. Antes de terminar, o programa deverá gravar toda a informação no ficheiro para que as alterações não sejam perdidas.

As passwords geradas automaticamente deverão conter 10 caracteres entre os quais pelo menos:
* 2 caracteres em letra maiúscula [A-Z]
* 2 dígitos [0-9]
* 1 símbolo ['%','&','$','?','!','#']
* 1 caracter em letra minúscula [a-z]

### Requisitos:
* utilização de memória dinâmica – Inicialmente não são conhecidas o número de passwords gravadas, pelo que a gestão da memória deverá ser feita dinamicamente utilizando malloc() e/ou callloc() e/ou realloc() e free().
* Não é permitido a utilização de variáveis globais
* É estritamente proibida a utilização da instrução goto
* A ferramenta git deverá ser utilizada para controlo de versões
* O código deverá ser dividido em ficheiros e deverá ser incluído um ficheiro Makefile
* O programa tem de compilar em Linux (Ubuntu 14.04) sem erros nem warnings com as flags: `-std=c99 -Wall -Wextra -Wpedantic`.

## Parte 2 [3 Valores]

Crie uma funcionalidade que permita inserir um cartão matriz para homebanking. Essa opção deverá permitir a consulta do cartão matriz pedindo 3 coordenadas. Por exemplo:
```
** input the coordinates
>h31 
>a11 
>c53
** Your security token is: 4 7 8
```

## Parte 3 [1 Valor]
Acrescente uma forma de configurar as passwords geradas aleatoriamente em:
* Número de caracteres
* Quantidade mínima de caracteres em maúscula
*  Quantidade mínima de caracteres em minúscula
* Quantidade mínima de dígitos
* Quantidade mínima de símbolos

## Parte 4 [1 Valor] Extra
Acrescente opções para procurar uma password e para ordenar a lista de passwords gravas.

## Invocação do programa
O programa deve aceitar como único parâmetro um ficheiro de configuração com o seguinte em formato :
```
type=<type>
username=<username>
password=<password>
url=<url>
```
em que  type poderá apenas tomar os valores: 
* login
* wifi
*  homebanking;
Quando o type for wifi, o campo username deverá ser utilizado para gravar o SSID da rede e o campo url não deverá existir. Por exemplo:

```mypass.txt
type=login
username=pingao
password=qwerty1234
url=https://www.amazon.com
type=wifi
username=darkside
password=hansolo1813
type=homebanking
username=144560
password=47892
url=www.cgd.pt
```

## Exemplo de execução
```
** Welcome to Password Vault **
** Please Select Option
**** 	q – Exit the program
**** 	l – list existing passwords
**** 	a – register new password
**** 	u – update existing password
**** 	d – delete existing password
**** 	v – view existing password
**** 	h – show this information
**** 	
>  l
 +------------------------------------------------
 | entry ID = 0
 | type=login
 | username=pingao
 | password=qwerty1234
 | url=https://www.amazon.com
 + ------------------------------------------------
 | entry ID = 1
 | type=wifi
 | username= darkside
 | password= hansolo
 +------------------------------------------------
 | entry ID = 2
 | type=wifi
 | username= darkside
 | password= hansolo
 +------------------------------------------------
 | entry ID = 3
 | type=homebanking
 | username=144560
 | password=47892
 | url=www.cgd.pt
 +------------------------------------------------
** Please Select Option
**** 	q – Exit the program
**** 	l – list existing passwords
**** 	a – register new password
**** 	u – update existing password
**** 	d – delete existing password
**** 	v – view existing password
**** 	h – show this information
**** 	
> u
** please select the entry ID
> 2
** insert username
> lightside
** insert new password manually [m] or generate automatically [a]
> m
** insert new password
> darthmaul
** Ok, done
** Please Select Option
**** 	q – Exit the program
**** 	l – list existing passwords
**** 	a – register new password
**** 	u – update existing password
**** 	d – delete existing password
**** 	v – view existing password
**** 	h – show this information
**** 	
> v
** please select the entry ID
> 2
+------------------------------------------------
| entry ID = 2
| type=wifi
| username= lightside
| password= darthmaul
+------------------------------------------------
** Please Select Option
**** 	q – Exit the program
**** 	l – list existing passwords
**** 	a – register new password
**** 	u – update existing password
**** 	d – delete existing password
**** 	v – view existing password
**** 	h – show this information
**** 
> q
** Ok, Bye
```

## Material a entregar

* Um Ficheiro zip contendo:
* Ficheiro `.c` com código devidamente comentado e indentado:
    - Deve implementar as funcionalidades pedidas.
* Um ficheiro Makefile com a receita de compilação do programa
* Ficheiro `README.md` em formato [Markdown], contendo as seguintes secções:
    - Título
    - Nomes do autor (primeiro e último) e respectivo número de aluno
    - Descrição da solução
    - Conclusões e matéria aprendida
    - Referências
        * Incluindo trocas de ideias com colegas, código aberto reutilizado e bibliotecas utilizadas
* A pasta escondida .git


## Forma e data de entrega

A forma de obter, editar e submeter o trabalho será através do [Moodle] até às **23:55 de 3 de Março de 2019**. Trabalhos entregues depois desta data sofrem de uma penalização de 0.2 valores por dia.

## Peso na avaliação

O projecto será cotado de 0 a 20 valores e terá um peso de 50% da nota final da unidade curricular.

## Honestidade académica

Nesta disciplina, espera-se que cada aluno siga os mais altos padrões de
honestidade académica. Isto significa que cada ideia que não seja do
aluno deve ser claramente indicada, com devida referência ao respectivo
autor. O não cumprimento desta regra constitui plágio [(3)](#ref3).

O plágio inclui a utilização de ideias, código ou conjuntos de soluções
de outros alunos ou indivíduos, ou quaisquer outras fontes para além
dos textos de apoio à disciplina, sem dar o respectivo crédito a essas
fontes. Os alunos são encorajados a discutir os problemas com outros
alunos e devem mencionar essa discussão quando submetem os Projectos.
Essa menção **não** influenciará a nota. Os alunos não deverão, no
entanto, copiar códigos, documentação e relatórios de outros alunos, ou dar os
seus próprios códigos, documentação e relatórios a outros em qualquer
circunstância. De facto, não devem sequer deixar códigos, documentação e
relatórios em computadores de uso partilhado.

Nesta disciplina, a desonestidade académica é considerada fraude, com
todas as consequências legais que daí advêm. Qualquer fraude terá como
consequência imediata a anulação dos Projectos de todos os alunos envolvidos
(incluindo os que possibilitaram a ocorrência). Qualquer suspeita de
desonestidade académica será relatada aos órgãos superiores da escola
para possível instauração de um processo disciplinar. Este poderá
resultar em reprovação à disciplina, reprovação de ano ou mesmo
suspensão temporária ou definitiva da ULHT [(2)](#ref2).

## Referências

<a name="ref1"></a>

* (1) Pereira, A. (2017). C e Algoritmos, 2ª edição. Sílabo.

<a name="ref2"></a>

* (2)  Texto adaptado da disciplina de [Algoritmos e Estruturas de Dados][aed] do [Instituto Superior Técnico][ist].

<a name="ref3"></a>

* (3)  Nuno Fachada. (2017). Primeiro Trabalho de Introdução à Computação, Licenciatura em Videojogos, Universidade Lusófona de Humanidades e Tecnologias, Lisboa.

## Licenças

Todo o código neste repositório é disponibilizado através da licença [GPLv3].
O enunciado e restante documentação são disponibilizados através da licença [CC BY-NC-SA 4.0].

## Metadados

* Autor: [Pedro Serra]
* Curso:  [Licenciatura em Aplicações Multimédia e Videojogos][lamv]
* Instituição: [Universidade Lusófona de Humanidades e Tecnologias][ULHT]



[GPLv3]:https://www.gnu.org/licenses/gpl-3.0.en.html
[CC BY-NC-SA 4.0]:https://creativecommons.org/licenses/by-nc-sa/4.0/
[lamv]:https://www.ulusofona.pt/licenciatura/aplicacoes-multimedia-e-videojogos
[Pedro Serra]:https://github.com/parroz
[ULHT ]:https://www.ulusofona.pt/
[aed]:https://fenix.tecnico.ulisboa.pt/disciplinas/AED-2/2009-2010/2-semestre/honestidade-academica
[ist]:https://tecnico.ulisboa.pt/pt/
[Markdown]:https://guides.github.com/features/mastering-markdown/
[GCC]:https://gcc.gnu.org/
[Clang]:https://clang.llvm.org/
[Gedit]:https://wiki.gnome.org/Apps/Gedit
[Geany]:https://www.geany.org/
[Code::Blocks]:http://www.codeblocks.org/
[Atom]:https://atom.io/
[XCode]:https://developer.apple.com/xcode/
[Notepad++]:https://notepad-plus-plus.org/
[Remarkable]:https://remarkableapp.github.io/
[Git]:https://git-scm.com/
[repositório]:https://github.com/VideojogosLusofona/ic2017p1
[GitHub]:https://github.com/
[git-tutorial]:https://try.github.io/levels/1/challenges/1
[Moodle]:https://secure.grupolusofona.pt/ulht/moodle/
[GitLab]:https://gitlab.com/
[BitBucket]:https://bitbucket.org/
[NotABug]:https://notabug.org/
[StackEdit]:https://stackedit.io/editor
[(GitHub-Flavored) Markdown Editor]:https://jbt.github.io/markdown-editor/
