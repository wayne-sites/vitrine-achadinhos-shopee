# Vitrine de Achadinhos Shopee

Catálogo estático responsivo conectado ao feed de afiliados da Shopee.

## Conteúdo do catálogo

- 100.000 produtos importados do CSV de feed fornecido.
- Imagem principal, título e descrição resumida.
- Preço atual, preço de referência e desconto informado pelo feed.
- Categorias, avaliação do produto e da loja.
- Link de redirecionamento de afiliado gerado no feed.
- Pesquisa, filtro por categoria, ordenação e paginação de 24 itens.

## Arquivos obrigatórios

Mantenha os dois arquivos na raiz do repositório:

- `index.html`
- `products.json.gz`

O arquivo compactado de catálogo tem aproximadamente 18 MB. Ele não contém o endereço/token privado de download do feed; contém apenas os dados de produto necessários para a vitrine.

## Executar localmente

O catálogo é carregado via `fetch`, portanto não abra o HTML diretamente com `file://`. Na pasta dos arquivos, execute:

```powershell
python -m http.server 8000
```

Depois abra http://localhost:8000.

## Publicar com GitHub Pages

1. Envie `products.json.gz` para a raiz deste repositório, na branch `main` (Add file → Upload files → Commit changes).
2. Em **Settings → Pages**, selecione **Deploy from a branch**.
3. Escolha a branch `main` e a pasta `/(root)`; salve.
4. Aguarde a publicação do Pages e abra a URL indicada em Settings → Pages.

## Observações

- O navegador baixa e descompacta o catálogo gzip. Use uma versão atual do Chrome, Edge, Firefox ou Safari.
- A interface renderiza 24 produtos por página, mas pesquisa e filtros consideram todo o catálogo.
- Preços, disponibilidade, frete e condições podem mudar; confirme sempre no anúncio da Shopee.
- Os links de compra são os campos de redirecionamento afiliado presentes no CSV recebido.
