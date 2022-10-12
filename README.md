# instruções iniciais para front-end

## Disclaimers

1. 🚀 A ideia não é trazer um canhão para matar uma barata, não vejam essas dicas como uma entrava, mas como uma indicação do caminho que devemos seguir. Afinal, começando certo, com pequenos passos, acertaremos no final. Inclusive, já usamos um modelo de pasta bem parecido

1. 🪨 Nada está escrito em pedras! Por mais que eu esteja trazendo um formato usado por vários projetos, podemos adaptar a nossa realidade

1. 🧠 Ao final deste documento estarei deixando o link das referências, mas foi fortemente me baseando na airbnb (referência até nos modelos do eslint, veremos em outro repo!), fusando github de empresas como Meta, artigos e algo não distante do que já temos

1. ❓Você vai ver que algumas pastas começam com **\_\_**, o motivo é para que elas fiquem separadas das demais pastas, então, adicionando o \_ elas ficaram juntas no topo do diretório e também dar a ideia de pastas “privadas”, ou seja, que não devem ser acessadas diretamente através de import.

1. 💡Certamente vão surgir outras estruturas e dúvidas, vamos construindo e implementando esse projeto aqui juntos.

---

## Como criar um projeto se formos usar ts

`npx create-next-app@latest --ts nome_do_menino`

---

## test

Para os testes eu vi 2 abordagens:

1. Cada teste dentro do seu componente: aparentemente fica mais rápido de achar onde cada teste está (ah, quero teste do botão, vou no componente botão... não preciso selecionar dentre vários outros testes)

1. Testes dentro de _**tests**_: argumento que me convenceu:
   > Todos os testes estão armezanados dentro da pasta **tests**, isso para facilitar no dia á dia, pois, geralmente eles são bem menos modificados do que os demais componentes. Assim, se tivermos os arquivos .test.js soltos pelas pastas, ele estarão visualmente poluindo-a. Se eu quero mexer com um teste, eu vou na pasta de teste, eu não preciso ficar vendo eles a todo momento.

Além disso, o Jest busca por pasta **test** [como dito aqui](https://github.com/facebook/jest/issues/637) e [convencionado/recomendado aqui](https://create-react-app.dev/docs/running-tests/)

## assets

Por padrão, nextjs já cria como "public"

- [ ] public, common ou assets. Definir como chamaremos

Na pasta _\_assets_ são armezandos alguns css’s e javascript’s globais do projeto. Também é salvo as imagens seja o logo do cliente ou algum background (se existir). Caso exisa a necessidade de fontes ou ícones personalizados, eles também ficam na pasta \_assets.

## config

A pasta \_config como o próprio nome já diz, é responsável por realizar configurações no projeto. Aqui vão ficar todos os arquivos de configuração, que são utilizados de uma forma global pela aplicação.

## constants

A pasta constants armazena valores (como o nome sugere, constantes) que são utilizados em vários lugares dos códigos, assim, caso algum valor um dia precise mudar ou ser atualizado, essa mudança e atualização será feita em apenas um lugar.

## containers

A pasta containers irá armazenar os componentes que são containers do projeto, em outras palavras, irá armazenar os componentes que fazem o wrap da aplicação. Responsáveis por fazer um Dependency Injection na nossa aplicação, tirando a dependencia da nossa aplicação de funcionar com alguma biblioteca.

Dentro da pasta containers estarão os componentes burros que irão ser informados nas rotas e realiazarão o mapeando das ações e store (mapDispatchToProps e mapStateToProps) para os componentes da pasta pages, a ideia de não chamar diretamente os componentes da pasta pages é para facilitar futuramente nos testes, facilitando a necessidade de mockar ações, stores, etc…

Os containers basicamente serão wrap’s para os pages e cada page deve ter um container.

## docs

Adivinha só? Exatamente! Se o projeto precisar de alguma documentação além do README.md (uma instruçãozinha que seja importante), colocamos aqui

## hooks

Aqui eu gosto de deixar todos os hooks customizáveis da aplicação, por exemplo, um hook que cuida da sessão do usuário.

## pages

Dentro da pasta pages estará o componente que será renderizado na tela.

## components

Aqui vai ficar todos os componentes que são utilizados pela aplicação. Caso a feature precise de um componente exlusivo, uma pasta components deve ser criada para armazená-lo.

## services

Nessa pasta fica todos os arquivos responsáveis por consumir serviços externos, como por exemplo o arquivo de configuração do axios para consumir APIs.

## utils

A pasta utils possui funções que serão reaproveitadas e utilizadas em várias partes dos códigos, assim, a manutenção fica mais fácil, pois, ao realizar a modificação em um determinado arquivo, a mesma irá estar disponível para todo o projeto. Evitando também a repetição de código.

### Referências

- https://blog.matheuscastiglioni.com.br/como-organizar-projetos-em-react/
- https://blog.vinniciusgomes.dev/arquitetando-uma-aplica%C3%A7%C3%A3o-next-js-4e30f45d69ac
- https://dev.to/trybe/um-guia-sobre-estruturacao-de-pastas-para-projetos-em-nextjs-5b6j
- https://github.com/airbnb/javascript
