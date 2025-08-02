# Aula 07 - Customizando o Bootstrap com Sass

Quando combinamos Bootstrap com a linguagem Sass podemos torná-lo ainda mais poderoso, permitindo a modularização do framework, customização de variáveis e otimização dos arquivos finais.

1. Vamos começar criando um novo projeto com o Vite:

    Obs.: Usaremos ele pela facilidade, mas a documentação do Bootstrap traz o passo a passo de instalação para vários cenários e empacotadores diferentes, como o Webpack.

```bash
npm create vite@latest
```

2. Vamos instalar também o Bootstrap e o Sass:

```bash
npm i --save bootstrap @popperjs/core
npm i --save-dev sass
```

3. Antes de prosseguir, remova todo o conteúdo de exemplo do Vite e crie o diretório src/scss contendo o arquivo style.scss. Além disso, modifique o arquivo index.html como no código abaixo:

```html
<!doctype html>
<html lang="pt-br">

<head>
  <meta charset="UTF-8" />
  <link rel="icon" type="image/svg+xml" href="/vite.svg" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Bootstrap + Sass</title>
  <script type="module" src="./src/main.js"></script>
</head>

<body>
  <div class="container bg-body-tertiary mt-3 p-3 border rounded shadow-sm">
    <h1>Usando o Bootstrap com Sass</h1>
    <p>Com a ajuda do Sass podemos customizar, modularizar e otimizar o uso do Bootstrap em nossos sites e aplicativos.</p>
    <a
      href="<https://getbootstrap.com/docs/5.3/customize/sass/>"
      class="btn btn-primary"
      target="_blank"
    >
      Leia a Documentação
    </a>
  </div>
</body>

</html>
```

src/scss/style.scss:
```scss
@use 'bootstrap/scss/bootstrap';
```

src/main.js:
```js
import '../scss/style.scss'
```

4. Opcionalmente, você pode ajustar a configuração do Vite de acordo com a documentação do Bootstrap como fizemos em aulas anteriores:

    Obs.: Lembrando que, se você usar essa configuração, precisa colocar seu arquivo index.html dentro da pasta src e ajustar o caminho da tag script para <script type="module" src="./js/main.js"></script>

```js
import { resolve } from 'path'

export default {
  root: resolve(__dirname, 'src'), // indica que o index.html raiz estará na pasta 'src'
  build: { outDir: '../dist' }, // especifica um nome para a pasta de saída/build
  server: { port: 8080 } // executa o servidor na porta 8080 ao invés de 5173 (padrão)
}
```

5. Agora que já estamos com o Bootstrap e o Sass funcionando corretamente, podemos customizar quais as partes do framework que vamos utilizar, otimizando drásticamente o tamanho do nosso pacote final:

    Obs.: Lembrando que o Bootstrap 5.3.3 ainda não atualizou para trabalhar com o @use das versões mais recentes do Sass. Se o seu Bootstrap for o 5.3.4 ou superior, provavelmente poderá usar o @use.

```scss
// 1. Include functions first (so you can manipulate colors, SVGs, calc, etc)
@import "bootstrap/scss/functions";

// 2. Include any default variable overrides here

// 3. Include remainder of required Bootstrap stylesheets (including any separate color mode stylesheets)
@import "bootstrap/scss/variables";
@import "bootstrap/scss/variables-dark";

// 4. Include any default map overrides here

// 5. Include remainder of required parts
@import "bootstrap/scss/maps";
@import "bootstrap/scss/mixins";
@import "bootstrap/scss/utilities";
@import "bootstrap/scss/root";

// 6. Optionally include any other parts as needed
@import "bootstrap/scss/reboot";
@import "bootstrap/scss/type";
@import "bootstrap/scss/images";
@import "bootstrap/scss/containers";
// @import "bootstrap/scss/grid";
// @import "bootstrap/scss/tables";
// @import "bootstrap/scss/forms";
@import "bootstrap/scss/buttons";
@import "bootstrap/scss/transitions";
// @import "bootstrap/scss/dropdown";
@import "bootstrap/scss/button-group";
// @import "bootstrap/scss/nav";
// @import "bootstrap/scss/navbar";
@import "bootstrap/scss/card";
// @import "bootstrap/scss/accordion";
// @import "bootstrap/scss/breadcrumb";
// @import "bootstrap/scss/pagination";
// @import "bootstrap/scss/badge";
// @import "bootstrap/scss/alert";
// @import "bootstrap/scss/progress";
// @import "bootstrap/scss/list-group";
// @import "bootstrap/scss/close";
// @import "bootstrap/scss/toasts";
// @import "bootstrap/scss/modal";
// @import "bootstrap/scss/tooltip";
// @import "bootstrap/scss/popover";
// @import "bootstrap/scss/carousel";
// @import "bootstrap/scss/spinners";
// @import "bootstrap/scss/offcanvas";
// @import "bootstrap/scss/placeholders";

// Helpers
@import "bootstrap/scss/helpers";

// 7. Optionally include utilities API last to generate classes based on the Sass map in `_utilities.scss`
@import "bootstrap/scss/utilities/api";

// 8. Add additional custom code here
```

6. Também podemos modificar variáveis antes de sua declaração pelo framework, sobrescrevendo assim o seu valor de forma eficiente e customizando o visual do framework do jeito que quisermos:

```scss
// 1. Include functions first (so you can manipulate colors, SVGs, calc, etc)
@import "bootstrap/scss/functions";

// 2. Include any default variable overrides here
$primary: #ff4f60;

// 3. Include remainder of required Bootstrap stylesheets (including any separate color mode stylesheets)
@import "bootstrap/scss/variables";
@import "bootstrap/scss/variables-dark";

// 4. Include any default map overrides here

// 5. Include remainder of required parts
@import "bootstrap/scss/maps";
@import "bootstrap/scss/mixins";
// ...
```

7. Por fim, dentro de nossa pasta scss podemos modularizar os arquivos para deixá-los mais organizados. Abaixo segue uma exemplo de organização dos arquivos:

```
src
 |-- js
 |-- Scss
    |-- _bootstrap-components.scss
    |-- _custom-maps.scss
    |-- _custom-styles.scss
    |-- _custom-variables.scss
    |-- styles.scss
 |-- index.html
```

src/scss/style.scss
```scss
// Funções e mixins mais básicos do framework
// (deve vir primeiro caso você deseje utilizá-las)
@import "bootstrap/scss/functions";

// Variáveis customizadas
@import "custom-variables";

// Cálculo das variáveis do Bootstrap (obrigatório vir após variáveis customizadas)
@import "bootstrap/scss/variables";
@import "bootstrap/scss/variables-dark";

// Mapas customizados
@import "custom-maps";

// Outros recursos obrigatórios do Bootstrap
@import "bootstrap/scss/maps";
@import "bootstrap/scss/mixins";
@import "bootstrap/scss/utilities";
@import "bootstrap/scss/root";

// Components opcionais do Bootstrap (onde escolhemos o que usar/não usar)
@import "bootstrap-components";

// Estilos próprios não relacionados ao framework
@import "custom-styles";
```