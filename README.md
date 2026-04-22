# 🍔 Smash It - Gestão de Preços, Fornecedores e Relatórios

Sistema web completo para gestão de preços de custo/venda, controle de quantidades, cadastro de fornecedores e geração de relatórios estratégicos. Ideal para restaurantes, hamburguerias e pequenos negócios que precisam organizar seu estoque, margens e compras.

## ✨ Funcionalidades

- **Gestão de produtos**  
  - Categorias e itens personalizáveis  
  - Preço de custo e preço de venda por item  
  - Controle de quantidade em estoque  
  - Cálculo automático da margem de lucro (%)  
  - Visibilidade individual (ocultar itens do relatório)

- **Fornecedores**  
  - Cadastro completo (nome, contato, produto fornecido, preço)  
  - Associação de produtos a fornecedores  
  - Exibição do fornecedor e seu preço ao lado do produto

- **Relatórios**  
  - **Resumo de gestão** (WhatsApp) – todos os itens visíveis com quantidades, preços e margem  
  - **Relatório para diretoria** (WhatsApp) – levantamento de preços por fornecedor, alerta de itens sem fornecedor  
  - **PDF** – relatório completo com produtos, fornecedores e observações

- **Sincronização e partilha**  
  - Exportar todos os dados para arquivo JSON  
  - Importar dados de outro usuário  
  - Sincronização entre abas do mesmo navegador (BroadcastChannel)  
  - Tema claro/escuro isolado (preferência local)

- **Utilitários**  
  - Calculadora integrada  
  - Pesquisa global (categorias e itens)  
  - Modo de edição rápida (renomear, adicionar, excluir)  
  - Botões de zerar preços/quantidades e reset completo

## 🚀 Como usar

1. **Acesse o sistema** – Basta abrir o arquivo `index.html` em qualquer navegador moderno (funciona offline após o primeiro carregamento).
2. **Dados iniciais** – Já vêm com categorias e produtos de exemplo (hamburgueria).
3. **Modo gestão** – Clique no ícone de engrenagem (⚙️) para ativar a edição:
   - Adicionar/editar categorias
   - Adicionar/renomear/remover itens
   - Associar fornecedores aos produtos
4. **Preencher preços e quantidades** – Digite diretamente nos campos:
   - `Qtd` – quantidade em estoque
   - `Custo` – preço de custo (€)
   - `Venda` – preço de venda (€)
   - A margem é calculada automaticamente
5. **Cadastrar fornecedores** – Clique no ícone de caminhão 🚚 e adicione nome, contacto, produto e preço.
6. **Gerar relatórios** – Use os botões no rodapé:
   - `ENVIAR RESUMO` – relatório geral para WhatsApp
   - `RELATÓRIO DIRETORIA` – foco em fornecedores e preços
   - Ícone PDF 📄 – gera e baixa um PDF completo
7. **Partilhar dados** – Ícones de download/upload no cabeçalho permitem exportar/importar toda a configuração (produtos, preços, fornecedores, observações). Envie o arquivo `.json` para outro usuário ou dispositivo.

## 🛠️ Tecnologias utilizadas

- **HTML5 / CSS3** – estrutura e estilos responsivos
- **Tailwind CSS** – utilitários CSS (via CDN)
- **Font Awesome 6** – ícones
- **JavaScript (ES6+)** – toda a lógica de negócio, persistência local, geração de PDF e integração com WhatsApp
- **jsPDF** – geração de relatórios em PDF
- **LocalStorage** – armazenamento persistente dos dados no navegador
- **BroadcastChannel API** – sincronização entre abas

## 📱 Responsividade

A interface adapta-se automaticamente a:
- Celulares (largura mínima 320px)
- Tablets (768px)
- Computadores (1024px+)

Em telas pequenas, os campos de quantidade/preço e as ações são reorganizados para melhor toque e legibilidade.

## 🔒 Persistência e privacidade

- Todos os dados ficam apenas no **localStorage** do seu navegador.
- Nenhum dado é enviado para servidores externos.
- A preferência de tema (claro/escuro) é salva separadamente e não é compartilhada na exportação.

## 📄 Exportação/importação

O formato do arquivo JSON exportado contém:
```json
{
  "inventory": [ ... ],   // categorias, itens, preços, quantidades, fornecedores associados
  "suppliers": [ ... ],   // lista de fornecedores com ID, nome, contacto, produto, preço
  "notes": "...",         // texto das observações
  "version": "1.0"
}
