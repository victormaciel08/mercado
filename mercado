#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <locale.h>
#define X 50

struct Produto{
	int cod;
	char nome[30];
	float preco;
	int qntEstq;
};

struct Carrinho{
	Produto produto; 
	int qntCarrinho;
};

void cadastrarProduto(struct Produto produto[X], int *qnt){
	int i;
	int cad = 0;
	
	printf("-------------Cadastro de Produto-------------\n\n");
	printf("Deseja cadastrar quantos produtos: ");
	scanf(" %d", &cad);
	
	system("cls");
	
	if (cad + *qnt < 51){
	for(i = *qnt; i < (cad + *qnt); i++){
		
		printf("-------------Cadastro de Produto-------------\n\n");
		
		produto[i].cod = i + 1;
		printf("Código: %d\n", produto[i].cod);
		
		printf("Digite o nome do produto: ");
		scanf(" %50[^\n]", &produto[i].nome);
		
		printf("Digite o preço do produto: ");
		scanf(" %f", &produto[i].preco);
		
		printf("Digite a quantidade do produto em estoque: ");
		scanf(" %d", &produto[i].qntEstq);
		
		system("pause");
		system("cls");	
		
		}	
	}else{
		printf("Número Máximo de Produtos cadastrados é 50.\n\n");
		system("pause");
		system("cls");
	}
	*qnt += cad;
	
}

void listarProdutos(struct Produto produto[X], int qnt){
	int i;
	printf("-------------Produtos Cadastrados-------------\n\n");
	if(qnt != 0){
		for(i = 0; i < qnt; i++){				
			printf("Código: %d\n", produto[i].cod);
			printf("Nome: %s\n", produto[i].nome);
			printf("Preço: %.2f\n", produto[i].preco);
			printf("Quantidade em Estoque: %d\n", produto[i].qntEstq);
			printf("--------------------------\n");
		}
		system("pause");
		system("cls");
	}else{
		printf("Nenhum produto foi cadastrado!\n");
		system("pause");
		system("cls");
	}
}

void buscarCod(struct Produto produto[X], int qnt) {
    int i;
	int codProd = 0;
    int prodEncontrado = 0;

	printf("-------------Busca por Código-------------\n\n");
	printf("Digite o código do produto: ");
	scanf("%d", &codProd);
	system("cls");
		
	for (i = 0; i < qnt; i++) {
	    if(produto[i].cod == codProd){
	        prodEncontrado = 1;
	            
	        printf("-------------Busca por Código-------------\n\n");
	        printf("Código: %d\n", produto[i].cod);
	        printf("Nome: %s\n", produto[i].nome);
	        printf("Preço: %.2f\n", produto[i].preco);
	        printf("Quantidade em Estoque: %d\n", produto[i].qntEstq);
	        printf("--------------------\n");
	
	        system("pause");
	        system("cls"); 
	    }
	}if(!prodEncontrado){
	    printf("-------------Busca por Código-------------\n\n");
	    printf("Produto com código %d não encontrado!\n\n", codProd);
	    system("pause");
	    system("cls");
	}
	
}

void buscarProdutos(struct Produto produto[X], int qntProd, int qnt){
	
	int op = 0;
	int sair = 0;
	
	if(qnt != 0){
		while(sair != 1){
			printf("-------------Busca de Produtos-------------\n\n");
			printf("(1). Listar Todos Produtos\n(2). Buscar Produto pelo Código\n(3). Retornar ao Menu\n");
			scanf(" %d", &op);
			system("cls");
			switch(op){
				case 1:				
					listarProdutos(produto, qnt);
					break;
				case 2:	
					buscarCod(produto, qnt);
					break;
				case 3:
					sair++;
					break;
				default:
					printf("-------------Busca de Produtos-------------\n\n");
					printf("Opção Inválida!\n\n");
					system("pause");
	    			system("cls"); 
					break;
			}
		}
	}else{
		printf("-------------Busca de Produtos-------------\n\n");
		printf("Nenhum Produto foi Cadastrado ainda.\n\n");
		system("pause");
	    system("cls"); 
	}
}

void adicionarEstoque(struct Produto produto[X], int qntProd, int qnt){
	int i;
	int j;
	int k;
	int codProd = 0;
	int qntAdd = 0;
	int prodEncontrado = 0;
	
	if(qnt != 0){
		printf("-------------Adicionar ao Estoque-------------\n\n");
		printf("Deseja adicionar quantos produtos ao Estoque? ");
		scanf(" %d", &qntProd);
		system("cls");
		
		for(i = 0; i < qntProd; i++){
			listarProdutos(produto, qnt);
			printf("-------------Adicionar ao Estoque-------------\n\n");
			printf("Digite o codigo do produto: ");
			scanf(" %d", &codProd);
			system("cls");
			prodEncontrado = 0;
			
			for(j = 0; j < qnt; j++){
				if(produto[j].cod == codProd){				
					prodEncontrado = 1;
					printf("-------------Adicionar ao Estoque-------------\n\n");
					printf("Produto: %s\n", produto[j].nome);
	                printf("Digite a quantidade a adicionar: ");
	                scanf("%d", &qntAdd);
	                system("pause");
					system("cls");
					
	                produto[j].qntEstq += qntAdd;   
	                
	                printf("-------------Adicionar ao Estoque-------------\n\n");
	                printf("%s adicionado ao estoque!\n", produto[j].nome);  	
	                printf("Quantidade em Estoque: %d\n\n", produto[j].qntEstq);
	                system("pause");
	                system("cls"); 
	                
					break;	
				}
			}
		}if(!prodEncontrado){
				printf("Produto com código %d não encontrado!\n\n", codProd);
				system("pause");
	            system("cls");
		}
				prodEncontrado == 0;
	}else{
		printf("-------------Adicionar ao Estoque-------------\n\n");
		printf("Nenhum Produto foi Cadastrado ainda.\n\n");
		system("pause");
	    system("cls"); 
	}	
}

void comprarProduto(struct Produto produto[X], struct Carrinho carrinho[X], int qntProd, int *qntProdCarrinho, int qnt){
	int i;
	int j;
	int k;
	int codProd = 0;
	int qntDesejada = 0;
	int prodEncontrado = 0;
	int prodCarrinho = 0;
	
	if(qnt != 0){
		printf("-------------Comprar Produtos-------------\n\n");
		printf("Deseja comprar quantos produtos? ");
		scanf(" %d", &qntProd);
		system("cls");
		
		for(i = 0; i < qntProd; i++){
			listarProdutos(produto, qnt);
			printf("-------------Comprar Produtos-------------\n\n");
			printf("Digite o codigo do produto: ");
			scanf(" %d", &codProd);
			system("cls");
			
			
			prodEncontrado = 0;
			
			for(j = 0; j < qnt; j++){
				if(produto[j].cod == codProd){				
					prodEncontrado = 1;
					printf("-------------Comprar Produtos-------------\n\n");
					printf("Produto: %s\n", produto[j].nome);
	                printf("Quantidade em estoque: %d\n", produto[j].qntEstq);
	                printf("Digite a quantidade desejada: ");
	                scanf("%d", &qntDesejada);
	                system("cls"); 
	                
	                if(qntDesejada <= produto[j].qntEstq){
	
	                    for(k = 0; k < *qntProdCarrinho; k++) {
	                        if (carrinho[k].produto.cod == codProd) {
	                            carrinho[k].qntCarrinho += qntDesejada;
	                            produto[j].qntEstq -= qntDesejada;
	                            prodCarrinho = 1;
	                            printf("-------------Comprar Produtos-------------\n\n");
	                            printf("Quantidade Atualizada em seu Carrinho!\n");
	                            printf("Quantidade Atual: %d\n\n", carrinho[k].qntCarrinho);
	                            system("pause");
	                        	system("cls"); 
	                            
	                        }
	                    }
	
	                    if (!prodCarrinho) {
	                        produto[j].qntEstq -= qntDesejada;  
	                        carrinho[*qntProdCarrinho].produto = produto[j];  
	                        carrinho[*qntProdCarrinho].qntCarrinho = qntDesejada;
	                        (*qntProdCarrinho)++;  
						
							printf("-------------Comprar Produtos-------------\n\n");
	                        printf("Produto adicionado ao carrinho!\n\n");  	
	                        system("pause");
	                        system("cls"); 
	                	
						}
					}else if(qntDesejada > produto[j].qntEstq){
						printf("-------------Comprar Produtos-------------\n\n");
						printf("Quantidade indisponível em estoque!\n\n");
						system("pause");
	                	system("cls");
					}
				}
			}if(!prodEncontrado){
				printf("-------------Comprar Produtos-------------\n\n");
				printf("Produto com código %d não encontrado!\n\n", codProd);
				system("pause");
	            system("cls");
			}	
		}
	}else{
		printf("-------------Comprar Produtos-------------\n\n");
		printf("Nenhum Produto foi Cadastrado ainda.\n\n");
		system("pause");
	    system("cls"); 
	}
}

void vizualizarCarrinho(struct Produto produto[X], struct Carrinho carrinho[X], int qntProdCarrinho){
	int i = 0;
	float soma = 0;
	
	if(qntProdCarrinho > 0){
		printf("-------------Carrinho-------------\n\n");
		for(i = 0; i < qntProdCarrinho; i++){
			soma = (carrinho[i].produto.preco * carrinho[i].qntCarrinho);
			printf ("Produto: %s\n", carrinho[i].produto.nome);
			printf ("Unidades: %d\n", carrinho[i].qntCarrinho);
			printf ("Valor Unitário: %.2f\n", carrinho[i].produto.preco);
			printf("Valor Total do Produto: %.2f\n", soma);
			printf("--------------------\n\n");
		}
		}else{
			printf("-------------Carrinho-------------\n\n");
			printf("Ainda não há produtos no Carrinho!\n\n");
			
		}
		system("pause");
        system("cls");				
}
	
void limparCarrinho(struct Produto produto[X], struct Carrinho carrinho[X], int *qntProdCarrinho, int qnt){
	int i;
	int j;

	for(i = 0; i < *qntProdCarrinho; i++){
		for(int j = 0; j < X; j++){
		    if (produto[j].cod == carrinho[i].produto.cod){
		        produto[j].qntEstq += carrinho[i].qntCarrinho; 
		    }
		}
	}	
		
	*qntProdCarrinho = 0;  
	    
	for(i = 0; i < X; i++){  
		carrinho[i].produto.cod = 0;
		strcpy(carrinho[i].produto.nome, "");
		carrinho[i].produto.preco = 0.0;
		carrinho[i].produto.qntEstq = 0;
		carrinho[i].qntCarrinho = 0;
	}
	printf("-------------Limpar Carrinho-------------\n\n");
	printf("Carrinho está limpo!\n\n");	
	system("pause");
    system("cls");
	qnt = 0;
}	
		
void fecharPedido(struct Produto produto[X], struct Carrinho carrinho[X], int *qntProdCarrinho, int qnt){
	int i;
	int j;
	float soma = 0;
	float valorTotal = 0;	
	char fechar;
	int op = 0;
	
	printf("-------------Fechar Pedido-------------\n\n");
	
	if (*qntProdCarrinho != 0){
	
		for(i = 0; i < *qntProdCarrinho; i++){
			soma = (carrinho[i].produto.preco * carrinho[i].qntCarrinho);
			printf ("Produto: %s\n", carrinho[i].produto.nome);
			printf ("Unidades: %d\n", carrinho[i].qntCarrinho);
			printf ("Valor Unitário: %.2f\n", carrinho[i].produto.preco);
			printf("Valor Total do Produto: %.2f\n", soma);
			printf("--------------------------\n");
			valorTotal += soma;
		}
		printf("Valor total do PEDIDO: %.2f\n", valorTotal);
		printf("--------------------------\n\n");
			
		printf("(1). Confirmar Pedido\n(2). Retornar ao Menu\n");		
		scanf(" %d", &op);
	    system("cls");
	        
	    switch(op){
	       	case 1:
	       		*qntProdCarrinho = 0;  
	    
	   			for(i = 0; i < 50; i++){  
				 	carrinho[i].produto.cod = 0;
				    strcpy(carrinho[i].produto.nome, "");
				    carrinho[i].produto.preco = 0.0;
				    carrinho[i].produto.qntEstq = 0;
				    carrinho[i].qntCarrinho = 0;
	    		}
				printf("-------------Fechar Pedido-------------\n\n");
	    		printf("Compra Concluida!\n\n");    
				qnt = 0;			
	    		break;  		
	    	case 2:
	    		printf("-------------Fechar Pedido-------------\n\n");					
	    		break;
	    	default:
	    		printf("-------------Fechar Pedido-------------\n\n");
				printf("Opção Inválida!\n\n"); 
				break;   			
			}
	}else{
		printf("Ainda não há produtos no Carrinho!\n\n");
	}
    system("pause");
    system("cls");    		
}



void menuPrincipal(struct Produto produto[X], struct Carrinho carrinho[X], int *qnt, int qntProd, int *qntProdCarrinho){
	
	int op;
	int sair = 0;
	
	while(sair == 0){
	
		printf("-------------MENU-------------\n\n");
		printf("(1). Cadastrar Produto\n(2). Adicionar ao Estoque\n(3). Busca de Produtos\n(4). Comprar Produto\n(5). Vizualizar Carrinho\n(6). Limpar Carrinho\n(7). Fechar Pedido\n(8). Sair\n");
		scanf(" %d", &op);
		
		system("cls");
		switch(op){
			case 1:
				cadastrarProduto(produto, qnt);
				break;
			case 2:
				adicionarEstoque(produto, qntProd, *qnt);
				break;	
			case 3:
				buscarProdutos(produto, qntProd, *qnt);
				break;
			case 4:
				comprarProduto(produto, carrinho, qntProd, qntProdCarrinho, *qnt);
				break;
			case 5:
				vizualizarCarrinho(produto, carrinho, *qntProdCarrinho);
				break; 
			case 6:	
				limparCarrinho(produto, carrinho, qntProdCarrinho, *qnt);
				break;
			case 7:
				fecharPedido(produto, carrinho, qntProdCarrinho, *qnt);
				break;
			case 8:
				printf("\nAté a próxima!\n");
				sair++;
				break;
			default:
				printf("\nOpção inválida!\n");
				system("pause");
				system("cls");
				break;
		}
	}
}

int main(void){
	
	setlocale(LC_ALL, "Portuguese");

	struct Produto produto[X];
	struct Carrinho carrinho[X];
	int qnt = 0;
	int quantProd = 0;
	int qntCarrinho = 0;
	
	menuPrincipal(produto, carrinho, &qnt, quantProd, &qntCarrinho);
	
	

	return 0;
}
