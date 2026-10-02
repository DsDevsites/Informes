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

## Cloudflare Pages

O projeto já está preparado como site estático para o Cloudflare Pages.

### Opção pelo painel do Cloudflare
1. Entre no Cloudflare.
2. Vá em **Workers & Pages** → **Create application** → **Pages**.
3. Conecte o GitHub e selecione `DsDevsites/Informes`.
4. Branch: `main`.
5. Como não há build, deixe o comando de build vazio.
6. Diretório de saída: `/` (raiz do projeto).
7. Publique.

### Configuração dos arquivos no próprio site
Depois de publicado, abra **Configuração local** e escolha:
- Planilha 02 original;
- logo Kaefer;
- logo Gerdau.

O navegador guarda esses arquivos no **IndexedDB deste dispositivo/navegador**. Assim, o modelo padrão pode ser carregado automaticamente nas próximas utilizações. A Planilha 01 continua sendo escolhida quando você quiser processar uma nova lista.

> Por segurança, um site não pode receber um caminho físico como `C:\\Pasta\\Planilha.xlsx` e acessar esse arquivo sozinho. O fluxo correto no navegador é selecionar o arquivo uma vez e armazená-lo localmente no navegador.

### Observação
A versão atual gera os arquivos no navegador e não envia os dados das planilhas para um servidor. Isso permite usar o sistema hospedado no Cloudflare sem banco de dados e sem login nesta primeira fase.
