## Sobre o Projeto

Aplicação web desenvolvida em **Blazor WebAssembly (WASM)** (.NET) para consulta de endereço e dados do IBGE através do CEP utilizando a API pública do [BrasilAPI](https://brasilapi.com.br/).

O foco desta aula foi:
- Criar uma aplicação moderna SPA em **Blazor WebAssembly**.
- Configurar o `HttpClient` no `Program.cs` com a URL base da BrasilAPI (`https://brasilapi.com.br/`).
- Mapear retornos de APIs REST com modelos estruturados em C# (`Cep.cs` e `Ibge.cs`).
- Manipular formulários reativos com `@bind` e eventos de clique com feedback visual (`Buscando...`).
- Exibir os dados de endereço e do IBGE formatados conforme especificação visual.

## Funcionalidades

- **Consulta de CEP:** Aceita o CEP digitado (com ou sem formatação/pontuação).
- **Validação de Entrada:** Garante que o CEP contenha exatamente 8 dígitos antes de chamar a API.
- **Integração com BrasilAPI:** Requisição assíncrona para o endpoint `/api/cep/v1/{cep}`.
- **Exibição dos Dados do Endereço:**
  - CEP
  - Logradouro (Rua)
  - Bairro
  - Cidade e Estado (UF)
  - Serviço provedor do dado (ex: `open-cep`, `viacep`)
  - **Dados do IBGE:** Código da Cidade no IBGE e Código do Estado no IBGE.
- **Tratamento de Erros:** Exibe avisos caso o CEP não seja encontrado ou a conexão falhe.

## API Utilizada

- **Endpoint:** `https://brasilapi.com.br/api/cep/v1/{cep}`
- **Método:** GET
- **Exemplo de Retorno:**
  ```json
  {
    "cep": "30130000",
    "state": "MG",
    "city": "Belo Horizonte",
    "neighborhood": "Centro",
    "street": "Avenida Afonso Pena",
    "service": "open-cep",
    "ibge": {
      "city": "3106200",
      "state": "31"
    }
  }
  ```

## Tecnologias Utilizadas

- **C#** / **.NET**
- **Blazor WebAssembly (Standalone App)**
- **System.Net.Http.Json** (`GetFromJsonAsync`)
- **Bootstrap 5** (Estilização responsiva)

