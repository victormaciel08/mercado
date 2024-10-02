# mercado

# README - Sistema de Controle de Estoque e Carrinho de Compras
# Descrição do Projeto
  Este é um sistema básico de controle de estoque e gerenciamento de carrinho de compras desenvolvido em C. Ele permite cadastrar produtos, adicionar ao estoque, buscar e visualizar produtos, adicionar produtos ao carrinho de compras, visualizar e limpar o carrinho, além de fechar o pedido. O sistema simula um ambiente de compras onde é possível gerenciar os produtos disponíveis e as transações dos clientes.

# Funcionalidades Implementadas
- Cadastro de Produto: O usuário pode cadastrar até 50 produtos, informando nome, preço e quantidade em estoque.
- Adicionar ao Estoque: É possível adicionar mais unidades a produtos já cadastrados.
- Busca de Produtos: O sistema permite listar todos os produtos ou buscar por um produto específico através do código.
- Comprar Produto: O usuário pode adicionar produtos ao carrinho, especificando a quantidade desejada, desde que haja estoque disponível.
- Visualizar Carrinho: Exibe os produtos que estão no carrinho, com a quantidade e o valor total de cada item.
- Limpar Carrinho: Remove todos os produtos do carrinho e devolve suas quantidades ao estoque.
- Fechar Pedido: Exibe o total da compra e finaliza o pedido, limpando o carrinho.
- Sair: Encerra o programa.
  
# Estrutura do Código
- struct Produto: Armazena as informações do produto, como código, nome, preço e quantidade em estoque.
- struct Carrinho: Armazena os produtos adicionados ao carrinho e a quantidade de cada produto.
# Funções:
- cadastrarProduto(): Realiza o cadastro dos produtos.
- listarProdutos(): Lista os produtos cadastrados.
- buscarCod(): Realiza a busca de um produto pelo código.
- buscarProdutos(): Oferece opções de busca de produtos.
- adicionarEstoque(): Adiciona mais unidades a produtos já existentes.
- comprarProduto(): Adiciona produtos ao carrinho, verificando a quantidade disponível no estoque.
- vizualizarCarrinho(): Exibe os produtos no carrinho e o valor total.
- limparCarrinho(): Remove todos os produtos do carrinho.
- fecharPedido(): Finaliza o pedido, limpa o carrinho e confirma a compra.
- menuPrincipal(): Exibe o menu principal com as opções de ação para o usuário.
