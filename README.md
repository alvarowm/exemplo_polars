# PolarsExample – Exemplos com a Crate Polars em Rust

Este projeto demonstra funcionalidades essenciais da biblioteca Polars em Rust, uma engine de processamento de dados de alto desempenho.

## O que este exemplo faz?

O código em src/main.rs executa as seguintes operações com um arquivo CSV (valores.csv):

1. Leitura de um arquivo CSV com cabeçalho.
2. Estatísticas descritivas da coluna 'valor' (média, desvio padrão, mínimo, máximo, contagem).
3. Filtragem de linhas onde valor > 1000.
4. Ordenação decrescente pela coluna 'valor'.
5. Agrupamento por 'nome' com soma dos 'valores'.
6. Criação de uma nova coluna (valor_dobrado = valor * 2).
7. Remoção de linhas com valores nulos em qualquer coluna.
8. Preenchimento de nulos:
   - 'nome': preenchido com estratégia forward fill
   - 'valor': preenchido com 0.0
9. Junção (join) com um segundo DataFrame de exemplo (left join por 'nome' ↔ 'categoria').
10. Escrita do resultado final em valores_processado.csv.

## Estrutura Esperada

PolarsExample/
├── src/<br>
│   ├── main.rs<br>
│   └── valores.csv          ← seu arquivo de entrada<br>
├── valores_processado.csv   ← gerado automaticamente<br>
└── README.md<br>

Exemplo de valores.csv:

nome,valor
Notebook,1200.50
Mini PC,800.00
Notebook,1500.00
Mouse,
Teclado,50.00

> Observação: O caminho do arquivo está fixo no código como:
> C:\Users\D892630\RustroverProjects\PolarsExample\src\valores.csv
> Recomenda-se ajustar para um caminho relativo (ex: "src/valores.csv") se for compartilhar o projeto.

## Como Executar

1. Instale o Rust (https://www.rust-lang.org/tools/install) se ainda não tiver.
2. Coloque seu valores.csv na pasta src/.
3. Execute:

cargo run

Após a execução:
- O terminal exibirá todos os resultados intermediários.
- Um novo arquivo valores_processado.csv será criado na raiz do projeto.

## Dependências (Cargo.toml)

Certifique-se de ter no seu Cargo.toml:

[dependencies]
polars = { version = "0.40", features = ["lazy", "csv", "fill_null"] }

Ajuste a versão conforme necessário. A feature "fill_null" é necessária para o preenchimento de nulos.

## Recursos Úteis

- Documentação do Polars (Rust): https://pola-rs.github.io/polars/polars/index.html
- User Guide: https://pola-rs.github.io/polars/user-guide/
- Exemplos oficiais no GitHub: https://github.com/pola-rs/polars/tree/master/examples

Aproveite o poder do Polars para manipular dados com velocidade e elegância em Rust!
