# Gerenciador de Catálogos da Netflix com Azure Functions e Banco de Dados em C#


## Visão Geral

O arquivo `consulta-cards.html` demonstra como as APIs funcionam por meio de uma página HTML. Dependendo da execução, as portas podem ser alteradas, sendo necessário ajustar o HTML conforme os exemplos de chamadas abaixo.

## Endpoints da API

### 1. Armazenar um Arquivo no Azure Storage (CosmosDB)
```sh
curl --location 'http://localhost:7217/api/dataStorage' \
--header 'file-type: video' \
--form 'file=@"/C:/Users/valdir/devcode/dio/bootcamp-az-204/gerenciador-catalogos-netflix/handson-serverless-netflix/video.mp4"'
```

### 2. Incluir um Filme
```sh
curl --location 'http://localhost:7210/api/movie' \
--header 'Content-Type: application/json' \
--data '{
  "id": "a-random-guid-generated",
  "title": "Harry Potter e o Cálice de Fogo",
  "year": "2005",
  "video": "https://staflixdiovtbdev001.blob.core.windows.net/video/video.mp4",
  "thumb": "https://staflixdiovtbdev001.blob.core.windows.net/image/thumbvideo.jpg"
}'
```

### 3. Obter Detalhes de um Filme por ID
```sh
curl --location 'http://localhost:7296/api/detail?id=b5d9c3e9-151a-479b-be06-cf48e815299c'
```

### 4. Listar Todos os Filmes
```sh
curl --location 'http://localhost:7239/api/all'
```

## Considerações
- Certifique-se de que todas as dependências do projeto estão instaladas.
- Verifique as portas usadas durante a execução e ajuste as chamadas conforme necessário.
- O projeto utiliza o Azure Storage e CosmosDB para armazenamento de arquivos e dados.

## Autor
Desenvolvido por **Raul Ventura** no Bootcamp **DIO AZ-204**.

