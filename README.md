<h3 align="center">
  Desafio: Database upload
</h3>

## Sobre o desafio
Nesse desafio, foi criado uma aplicação Node.js que permite incluir,listar, deletar e importar dados nos repositórios criados, além disso é gerado um balanço com o valor de soma de entradas, retiradas e total de crédito.

**Observação**: Este desafio está utilizando o gerenciador de pacotes **yarn**, sendo assim para instalar todas as dependências é necessário dar o comando `yarn` no terminal.

### Funcionalidades da Aplicação

- **`POST /transactions`**: A rota recebe `title`, `value`, `type`, e `category` dentro do corpo da requisição, sendo o `type` o tipo da transação, que deve ser `income` para entradas (depósitos) e `outcome` para saidas (retiradas). Ao cadastrar uma nova transação, ela armazena dentro do banco de dados, possuindo os campos `id`, `title`, `value`, `type`, `category_id`, `created_at`, `updated_at`.

- **`GET /transactions`**: Essa rota retorna uma listagem com todas as transações que foram cadastradas até agora, junto com o valor de soma de entradas, retiradas e total de crédito.

- **`DELETE /transactions/:id`**: A rota deleta uma transação com o id presente nos parâmetros da rota;

* **`POST /transactions/import`**: A rota permiti a importação de um arquivo com formato `.csv` contendo as mesmas informações necessárias para criação de uma transação `id`, `title`, `value`, `type`, `category_id`, `created_at`, `updated_at`, onde cada linha do arquivo CSV gera um novo registro para o banco de dados, e por fim retorna todas as `transactions` que foram importadas para o banco de dados. O arquivo csv, deve seguir o seguinte [modelo](./src/assets/file.csv)
