# Renúncias fiscais sobre empresas em Santos (SP)

Este repositório reúne um notebook em Python e um painel em HTML para examinar a base de beneficiários de renúncias fiscais do Portal da Transparência no recorte do município de Santos.

O trabalho está organizado para responder três perguntas simples:

- onde estão os maiores valores;
- quais setores econômicos aparecem com mais peso;
- quais tipos de benefício explicam a maior parte do total.

A leitura principal exige um cuidado metodológico: a base não mede, por si só, perda de arrecadação da Prefeitura de Santos. Os valores observados recaem majoritariamente sobre tributos federais incidentes sobre empresas sediadas no município.

## Retrato da base utilizada

Com o arquivo `dados/beneficiario.csv` atualmente incluído no repositório, o recorte de Santos apresenta:

- `837` registros;
- `308` empresas beneficiárias;
- `107` classificações de CNAE;
- `19` tipos de benefício fiscal;
- total de `R$ 5.897.833.221,41`.

Alguns pontos chamam atenção logo de saída:

- a empresa com maior valor individual responde por `34,0%` do total;
- as `5` primeiras empresas concentram `67,4%`;
- as `10` primeiras concentram `83,4%`;
- COFINS e Imposto de Importação, sozinhos, somam mais de `82%` do valor observado.

## Principais destaques

No arquivo atualmente analisado, os maiores beneficiários são:

1. `ALFA LULA ALTO OPERACOES MARITIMAS LTDA` — `R$ 2,01 bi`
2. `EQUINOR BRASIL ENERGIA LTDA.` — `R$ 740,87 mi`
3. `PETROLEO BRASILEIRO S A PETROBRAS` — `R$ 492,13 mi`
4. `BUNGE ALIMENTOS S/A` — `R$ 396,96 mi`
5. `TRSP - TERMINAL DE REGASEIFICACAO DE GNL DE SAO PAULO S.A` — `R$ 340,51 mi`

Os CNAEs com maior peso são:

1. `09106 - Atividades de apoio à extração de petróleo e gás natural`
2. `06000 - Extração de petróleo e gás natural`
3. `10627 - Moagem de trigo e fabricação de derivados`
4. `52117 - Armazenamento`
5. `00000 - Sem informação`

Os benefícios com maior valor agregado são:

1. `COFINS` — `45,38%`
2. `Imposto de Importação` — `36,68%`
3. `PIS` — `9,48%`
4. `Horário Eleitoral` — `2,74%`
5. `IPI` — `2,49%`

## Arquivos do projeto

- `analise_renuncias_santos.ipynb`: leitura, limpeza e análise do CSV.
- `dashboard_renuncias_santos.html`: painel estático para apresentação dos resultados.
- `requirements.txt`: dependências mínimas para executar o notebook.
- `dados/`: pasta com a base CSV utilizada na análise.

## Fonte dos dados

Os dados vêm do Portal da Transparência do Governo Federal, na seção de beneficiários de renúncias fiscais. O CSV usado nesta versão do projeto já acompanha o repositório em `dados/beneficiario.csv`.

Se quiser atualizar a análise com uma extração mais recente, basta substituir esse arquivo por um novo CSV com o mesmo nome.

O notebook procura o arquivo nestes caminhos:

- `dados/beneficiario.csv`
- `dados/beneficiario (1).csv`
- `beneficiario.csv`
- `beneficiario (1).csv`

## Como executar

Crie um ambiente virtual, instale as dependências e abra o notebook:

```bash
python -m venv .venv
```

No Windows:

```bash
.venv\Scripts\activate
```

No macOS ou Linux:

```bash
source .venv/bin/activate
```

Depois:

```bash
pip install -r requirements.txt
jupyter lab analise_renuncias_santos.ipynb
```

Se preferir, o arquivo `.ipynb` também pode ser aberto diretamente no VS Code com a extensão do Jupyter.

## Dashboard

O painel HTML pode ser aberto direto no navegador, sem servidor local:

```bash
start dashboard_renuncias_santos.html
```

Os números usados no arquivo estão concentrados em um único objeto JavaScript, no fim do HTML. O painel já foi atualizado com base no CSV atualmente presente na pasta do projeto.

## Observações de interpretação

- O montante analisado descreve benefícios fiscais incidentes sobre empresas localizadas em Santos, e não arrecadação própria do município.
- COFINS, Imposto de Importação, PIS e IPI tendem a responder pela maior parte do total, o que reforça o peso da esfera federal na base.
- Sem cruzamento com emprego, arrecadação municipal e contrapartidas dos programas, a análise não basta para medir retorno econômico ou social dos incentivos.

## Publicação no GitHub

O repositório foi preparado para publicação com o CSV já incluído:

- o `.gitignore` exclui ambiente virtual, cache e arquivos auxiliares;
- a pasta `dados/` concentra a base usada na análise;
- o `requirements.txt` deixa explícitas as dependências do notebook.

## Estrutura esperada

```text
.
├── analise_renuncias_santos.ipynb
├── dashboard_renuncias_santos.html
├── README.md
├── requirements.txt
└── dados/
    ├── beneficiario.csv
    └── README.md
```
