# Reagentário LEQUIM — IQ-USP

Catálogo de reagentes alimentado pela aba **Base de dados - HTML** do Google Sheets.

- Site: https://lequim-iq-usp.github.io/
- Protótipo de origem: https://github.com/Nico-Araujo/LEQUIM
- Responsável inicial pelo código: Nico-Araujo.

## Atualizar o catálogo

A equipe atualiza a planilha. O navegador lê o CSV publicado ao abrir o site, pelo botão **Atualizar dados** e a cada 5 minutos enquanto a página estiver visível. A republicação do Google pode levar alguns minutos. O horário exibido é o horário da consulta, não da última edição da planilha.

Mantenha os cabeçalhos usados pelo site e a publicação automática da aba consolidada. A planilha publicada e o catálogo são públicos.

## Atualizar o site

Edite `index.html` neste repositório e faça commit na branch `main`. O GitHub Pages publica a raiz da branch `main` automaticamente. Não há etapa de build ou instalação para publicar.

## Consulta e códigos de barras

- Busca por nome, CAS, fórmula, Reagent ID e outros campos, sem diferenciar acentos ou maiúsculas.
- Filtros por localização e categoria, ordenação e páginas de 40 itens.
- Tabela no computador e cartões em telas pequenas. Detalhes acessíveis pelo nome ou pelo botão de abertura.
- A coluna **Reagent ID** é lida como texto, preservando zeros iniciais. IDs preenchidos geram códigos **Code 128**, com download em SVG e impressão de uma etiqueta individual de 85 mm de largura.
- Reagentes sem ID não recebem códigos artificiais. Caracteres incompatíveis e erros da planilha são indicados no painel.
- Botões para copiar ID e CAS. A cópia requer um navegador que permita acesso à área de transferência.
- FISPQ/SDS aponta para o link cadastrado na planilha, quando válido, ou para uma busca. As estruturas do PubChem são carregadas apenas nos detalhes.
- Em falhas de consulta, o site avisa o usuário; não exibe a antiga amostra fixa como estoque atual. Uma falha de atualização conserva apenas os dados já consultados na página, com aviso.

As bibliotecas `papaparse.min.js` (5.4.1) e `JsBarcode.code128.min.js` (3.11.0) estão no repositório para que a consulta e a geração de códigos não dependam de CDNs. Preserve esses arquivos. Ambas usam licença MIT, reproduzida em `THIRD-PARTY-LICENSES.txt`.

Para impressão, use escala de 100% e desative cabeçalhos e rodapés do navegador. Teste uma etiqueta com o leitor do laboratório antes de imprimir em lote.

## Hospedagem

Repositório público no plano GitHub Free e hospedagem pelo GitHub Pages, sem domínio registrado pago ou serviços pagos adicionais.

`.nojekyll` permite publicar os arquivos estáticos diretamente.
