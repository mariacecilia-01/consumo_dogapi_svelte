# Integração da Dog API com o Svelte
Aplicação simples desenvolvida com **Svelte** para consumo da **Dog API**, com foco em testar reatividade, navegação entre páginas e tratamento de erros.
A aplicação possui duas telas:  
a **tela de busca**, com uma única caixa de texto para digitar a raça do cachorro e navegar para o resultado, e a **tela de resultado**, que exibe o nome da raça pesquisada, imagens retornadas pela API, mensagem de erro para raças inválidas e um botão para voltar à tela inicial.

## Prévia

### Tela inicial
![tela inicial](/SvelteDogAPI/imagem2.png)

### Tela de resultado da busca
![resultado da busca](/SvelteDogAPI/imagem1.png)

## O que é o Svelte

O Svelte é um framework JavaScript para criação de interfaces web modernas.  
Diferente de outros frameworks, ele **não roda no navegador**: o código é compilado em JavaScript puro durante o build, o que resulta em aplicações mais rápidas e leves.

## Por que utilizar o Svelte

- Alto desempenho, com menos JavaScript sendo enviado ao navegador  
- Curva de aprendizado simples e sintaxe mais limpa    
- Reatividade nativa sem uso de estruturas complexas    
- Ideal para aplicaçsões rápidas, modernas e escaláveis

## Em quais cenários o Svelte não é indicado

- Projetos que dependem fortemente de bibliotecas exclusivas de React ou Angular  
- Times grandes que já seguem padrões rígidos baseados em outros frameworks  
- Aplicações legadas onde a migração teria alto custo  
- Projetos que exigem um ecossistema extremamente amplo e consolidado

## Guia de instalação

1. Requisitos do ambiente:

Garanta a instalação prévia do **Node.js** e do **npm** executando os comandos:

node -v  
npm -v  

Caso não estejam instalados, faça o download da versão mais recente em:

https://nodejs.org/

2. Comando de criação do projeto:

Na pasta onde o projeto será criado, execute o comando:

npx sv create (nome do projeto)

Responda às perguntas do instalador de acordo com as necessidades do projeto.

3. Como executar a aplicação localmente:

Acesse a pasta do projeto com o comando:

cd (nome do projeto)

Instale as dependências do projeto (Svelte, SvelteKit, Vite e dependências de desenvolvimento):

npm install

Inicie o servidor de desenvolvimento com o comando:

npm run dev

## Fontes de pesquisa
- Documentação oficial do Svelte:  
  https://svelte.dev  

- Artigo “Svelte: o que é, como funciona e diferenças com o React JS” – Alura:  
  https://www.alura.com.br/artigos/svelte-versus-react-quais-diferencas?srsltid=AfmBOoqdSsMre2pUrVFn6AKBaf_QZNFeME8S-jag9kKq7D4MGucRPmXT  

- Artigo "Svelte: o que é, vantagens, desvantagens e cases" – Blog Cubos:
  https://blog.cubos.io/svelte-o-que-e-vantagens-desvantagens-cases/# 

### Autoras
Maria Cecilia Pereira Jardim, Rebeca Gomes e Luana Bomfim.