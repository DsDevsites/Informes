# Informes — Gerador de Plano de Ação

Aplicação web para transformar uma **Planilha 01 — Controle de Informe** em vários arquivos **Planilha 02 — Plano de Ação Informe de Ato/Condição Abaixo do Padrão**.

## Fluxo
1. Carregar a Planilha 01 (XLSX/XLS/CSV).
2. Carregar a Planilha 02 oficial em XLSX. O arquivo original é usado como matriz.
3. O sistema identifica automaticamente os cabeçalhos da Planilha 01.
4. O sistema procura os cabeçalhos da tabela na Planilha 02 e sugere as células de destino.
5. Conferir/ajustar o mapeamento.
6. Validar campos obrigatórios e duplicidades.
7. Gerar um XLSX por informe dentro de um ZIP.

## Campos
Nº do informe, tipo de registro, local/área, data, informante, descrição da ocorrência, plano de ação, responsável, liderança, severidade/potencial, previsto, realizado e status.

A coluna **Liderança** é reconhecida na Planilha 01, mas não é forçada na Planilha 02 mostrada na imagem, porque a tabela do modelo não apresenta essa coluna.

## Modelo oficial
A imagem é usada apenas como referência visual. Para máxima fidelidade, o arquivo XLSX original da Planilha 02 deve ser carregado no sistema. Assim o programa trabalha sobre as próprias bordas, mesclagens, dimensões, logos e configurações de impressão do documento.

## Privacidade
Nesta primeira versão não há banco de dados nem backend. Os arquivos são processados no navegador.

## Publicação

O projeto é um site estático e está preparado para publicação na Vercel.

### Vercel
1. Importe o repositório `DsDevsites/Informes`.
2. Framework Preset: **Other**.
3. Build Command: deixe vazio.
4. Output Directory: `.` (raiz).
5. Publique.

Se o projeto da Vercel estiver conectado ao GitHub, cada atualização na branch `main` gera um novo deploy automaticamente.

### Configuração no site
Na área **Configuração local**, escolha uma vez:
- Planilha 02 original;
- logo Kaefer, se precisar substituir a logo do modelo;
- logo Gerdau, se precisar substituir a logo do modelo.

Não é necessário informar células das logos. O modelo oficial continua sendo a base do documento e as logos são opcionais.

O navegador guarda esses arquivos no **IndexedDB deste dispositivo/navegador**. Assim, o modelo padrão pode ser carregado automaticamente nas próximas utilizações. A Planilha 01 continua sendo escolhida quando você quiser processar uma nova lista.

> Por segurança, um site não pode receber um caminho físico como `C:\\Pasta\\Planilha.xlsx` e acessar esse arquivo sozinho. O fluxo correto no navegador é selecionar o arquivo uma vez e armazená-lo localmente no navegador.

### Privacidade
Nesta primeira versão não há banco de dados nem backend. Os arquivos são processados no navegador e não são enviados para um servidor pela aplicação.

## Saídas do lote

O botão **Gerar lote completo** pode produzir:
- **Excel individual:** um XLSX para cada informe;
- **Excel consolidado:** um XLSX com uma aba por informe;
- **PDF consolidado:** um único PDF com **1 informe por página**.

Os três resultados são reunidos em um único ZIP para facilitar o download.

O PDF é renderizado no navegador a partir do modelo XLSX carregado. Para preservar com máxima fidelidade o documento oficial, use sempre o XLSX original da Planilha 02.
