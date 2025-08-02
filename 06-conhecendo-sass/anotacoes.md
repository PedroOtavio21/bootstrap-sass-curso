# Aula 06 - Conhecendo o Sass

## O que é Sass?

SASS é a sigla para Syntactically Awesome StyleSheets

É uma linguagem de extensão de CSS, algo como um "CSS com superpoderes"

Permite escrever folhas de estilo usando recursos avançados que não existem na linguagem CSS convencional

O código SASS (que não funciona no navegador) é então convertido para código CSS compatível

- Pense nesse processo como algo semelhante ao que ocorre com o código JS moderno ou TS, que deve 
ser convertido com Babel ou outro compilador antes de ser colocado em produção 

## As 2 variações de sintaxe do Sass 

Ambas podem ser utilizadas e suportam todos os recursos avançados da linguagem, a escolha fica a critério do 
programador

### Arquivo .sass

A sintaxe original do Sass. É mais simples e funciona baseada em identação (como o Python)

### Arquivo .scss

A sintaxe mais comum do Sass. É praticamente identica ao CSS, usando "{}" e ";" para organização de código

## Recursos mais usados do Sass

- Variáveis
- Aninhamento 
- Funções, Mixins e outras "At-Rules" (regras que começam com @)
- Importações de módulos/arquivos
- Módulos nativos (com funções para manipulação de cores, strings, operações matemáticas, e muitos outros)

## Material complementar:

- [Site oficial]("https://sass-lang.com/")
- [Uso do Sass em conjunto com o Bootstrap]("https://getbootstrap.com/docs/5.3/customize/sass")

## Podemos usar o Sass de algumas formas diferentes:

- Usando alguma extensão para converter o código manualmente
- Instalando globalmente via npm através do pacote "sass"
- Instalando em um projeto com um empacotador, como Webpack ou o Vite