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
O projeto é estático e pode ser publicado em Cloudflare Pages, GitHub Pages ou outro serviço de hospedagem estática.