# Aula 04 - Classes auxiliares e utilitárias

O Bootstrap possui uma grande variedade de classes auxiliares básicas. Coisas como layouts, cores, alinhamento, manipulação de fontes e textos, espaçamento, bordas, sombras e muito mais.

O objetivo dessa aula não é apresentar todas, mas mostrar as mais básicas e te ajudar a entender como navegar na documentação para encontrar as classes que você precisa em cada situação.

1. Para começar, crie uma nova pasta para a aula e um arquivo index.html nela que inclua o Bootstrap via CDN:

```html
<!DOCTYPE html>
<html lang="pt-br">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Componentes do Bootstrap</title>
  <link href="<https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css>" rel="stylesheet"
    integrity="sha384-QWTKZyjpPEjISv5WaRU9OFeRpok6YctnYmDr5pNlyT2bRjXh0JMhjY6hW+ALEwIH" crossorigin="anonymous">
</head>

<body>
  <main>
    <h1>Classes Básicas do Bootstrap</h1>
    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Esse dolores unde dicta dignissimos earum quis
      doloremque facere dolor velit molestiae minima aliquam ut, quia accusamus. Accusamus at veritatis nihil quidem?
    </p>
    <ul>
      <li>Item 1</li>
      <li>Item 2</li>
      <li>Item com mais margem</li>
      <li>Item 4</li>
      <li>Item 5</li>
    </ul>
  </main>

  <section>
    <div>
      <h2>Seção com Cor de Fundo</h2>
      <p>Lorem ipsum, dolor sit amet consectetur adipisicing elit. Animi ad tempore, totam quae repellat qui commodi est
        sapiente possimus fugiat porro maiores rerum eligendi quidem maxime sequi, excepturi facere reprehenderit!</p>
    </div>
  </section>

  <section>
    <h2>Seção Centralizada</h2>
    <p>Lorem ipsum, dolor sit amet consectetur adipisicing elit. Animi ad tempore, totam quae repellat qui commodi est
      sapiente possimus fugiat porro maiores rerum eligendi quidem maxime sequi, excepturi facere reprehenderit!</p>
  </section>

  <section>
    <div>
      <h2>Utilitários de Display</h2>
      <div>
        <div>
          Item 1
        </div>
        <div>
          Item 2
        </div>
        <div>
          Item 3
        </div>
        <div>
          Item 4
        </div>
      </div>
      <div>
        <div>
          Item 1
        </div>
        <div>
          Item 2
        </div>
        <div>
          Item 3
        </div>
      </div>
    </div>
  </section>

  <script src="<https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js>"
    integrity="sha384-YvpcrYf0tY3lHB60NNkmXc5s9fDVZLESaAA55NDzOxhy9GkcIdslK1eN7N6jIeHz"
    crossorigin="anonymous"></script>
</body>

</html>
```

2. Após a demonstração da aula seu código deverá estar semelhante ao código abaixo:

```html
<!DOCTYPE html>
<html lang="pt-br" data-bs-theme="dark">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Componentes do Bootstrap</title>
  <link href="<https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css>" rel="stylesheet"
    integrity="sha384-QWTKZyjpPEjISv5WaRU9OFeRpok6YctnYmDr5pNlyT2bRjXh0JMhjY6hW+ALEwIH" crossorigin="anonymous">
</head>

<body>
  <main class="container py-3">
    <h1 class="text-center">Classes Básicas do Bootstrap</h1>
    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Esse dolores unde dicta dignissimos earum quis
      doloremque facere dolor velit molestiae minima aliquam ut, quia accusamus. Accusamus at veritatis nihil quidem?
    </p>
    <ul class="border border-primary border-4 rounded-0 shadow-lg">
      <li>Item 1</li>
      <li>Item 2</li>
      <li class="mx-3">Item com mais margem</li>
      <li>Item 4</li>
      <li>Item 5</li>
    </ul>
  </main>

  <section class="container-fluid bg-primary text-light py-5">
    <div>
      <h2>Seção com Cor de Fundo</h2>
      <p>Lorem ipsum, dolor sit amet consectetur adipisicing elit. Animi ad tempore, totam quae repellat qui commodi est
        sapiente possimus fugiat porro maiores rerum eligendi quidem maxime sequi, excepturi facere reprehenderit!</p>
    </div>
  </section>

  <section class="text-center mx-auto w-50 py-5">
    <h2>Seção Centralizada</h2>
    <p class="fs-5">Lorem ipsum, dolor sit amet consectetur adipisicing elit. Animi ad tempore, totam quae repellat qui commodi est
      sapiente possimus fugiat porro maiores rerum eligendi quidem maxime sequi, excepturi facere reprehenderit!</p>
  </section>

  <section class="min-vh-100">
    <div>
      <h2>Utilitários de Display</h2>
      <div class="d-flex align-items-center justify-content-center gap-5 fs-2">
        <div class="bg-primary">
          Item 1
        </div>
        <div class="bg-secondary py-3">
          Item 2
        </div>
        <div class="bg-success">
          Item 3
        </div>
        <div class="bg-danger">
          Item 4
        </div>
      </div>
      <div class="d-flex justify-content-center gap-3 fs-3 mt-5">
        <div class="bg-primary d-md-none">
          Item 1: Apenas Mobile
        </div>
        <div class="bg-success">
          Item 2: Mobile e Telas Grandes
        </div>
        <div class="bg-danger d-none d-xxl-block">
          Item 3: Apenas telas grandes
        </div>
      </div>
    </div>
  </section>

  <script src="<https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js>"
    integrity="sha384-YvpcrYf0tY3lHB60NNkmXc5s9fDVZLESaAA55NDzOxhy9GkcIdslK1eN7N6jIeHz"
    crossorigin="anonymous"></script>
</body>

</html>
```