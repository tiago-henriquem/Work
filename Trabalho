#include<stdio.h>
#include<string.h>
#include<stdlib.h>
#include<locale.h>

typedef struct{
	int codigo;
	char nome[30];
	int qtd;
	int qtdMin;
	double precoCompra;
	double precoVenda;
	char situacao;
}regprod;
regprod Produto[2];
	
void menu(int contador[]);
void menuprodutos(int contador[]);
void menuregistro(int contador[]);
void atualizarproduto(int contador[]);
void excluirproduto(int contador[]);
//void menupesquisa(int contador[]);
/*
regprod Produto: vetor de struct.
regprod Produto[]: *uma variável* do vetor de struct.

criar vetor na main.

*/

main(){
	setlocale(LC_ALL, "Portuguese");
	int contador[1];
	for(int i=0; i<2; i++){
		Produto[i].codigo = 0;
		i++;
	}
	menu(contador);	
}




void menu(int contador[]){
	int resp;
	printf("............................................................................\n");
	printf("1 - Produtos\n");
	printf("2 - Registrar vendas\n");
	printf("3 - Relatórios\n");
	printf("4 - Sair\n");
	printf("............................................................................\n");
	scanf("%d", &resp);
	if(resp==1){
		menuprodutos(contador);
	}else if(resp==4){
		printf("Encerrando o programa...");
		system("pause");
		system("cls");
	}
}

//1

void menuprodutos(int contador[]){
	int resposta;
	printf("Contador pós incremento: %d\n", contador[1]);
	printf("===========================================================================\n");
	printf("1 - Cadastrar produto\n");
	printf("2 - Atualizar produto\n");
	printf("3 - Excluir produto\n");
	printf("4 - Pesquisar nome do produto\n");
	printf("0 - VOLTAR\n");
	printf("===========================================================================\n");
	scanf("%d", &resposta);
	if(resposta==1){
		menuregistro(contador);
	}else if(resposta==2){
		atualizarproduto(contador);
	}else if(resposta==3){
		excluirproduto(contador);
//	}else if(resposta==4){
//		menupesquisa(contador);
	}else if(resposta==0){
		system("cls");
		menu(contador);
	}else{
		printf("Opção inválida.\n");
		system("pause");
		system("cls");
		menu(contador);
	}
	
}

//1.1

void menuregistro(int contador[]){
	int erro=0;
	if(contador[1]<2){
		printf(":::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::\n");			
		printf("Código: \n");	
		scanf("%d", &Produto[contador[1]].codigo);
		printf(":::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::\n");
		for(int i=0; i<2; i++){
				if(Produto[contador[1]].codigo==Produto[i].codigo && contador[1]!=i && Produto[i].situacao!='I'){
					printf("O produto não pode ser registrado. Já existe um produto com esse código.\n");
					system("pause");
					system("cls");
					menu(contador);
					erro++;
				}
		}
		if(erro==0){
			printf("Nome do produto:\n");
			scanf("%s", &Produto[contador[1]].nome[30]);
			printf(":::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::\n");
			printf("Quantidade em estoque:\n");
			scanf("%d", &Produto[contador[1]].qtd);
			printf(":::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::\n");
			printf("Quantidade mínima: ");
			scanf("%d", &Produto[contador[1]].qtdMin);
			printf(":::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::\n");
			printf("Preço de compra: ");
			scanf("%d", &Produto[contador[1]].precoCompra);
			printf(":::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::\n");
			printf("Preço de venda: ");
			scanf("%d", &Produto[contador[1]].precoVenda);
			printf(":::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::\n");
			printf("Situação: ");
			scanf("%s", &Produto[contador[1]].situacao);
			printf(":::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::\n");
			system("pause\n");
			printf("Contador: %d\n", contador[1]);
			contador[1]++;		
			printf("\nProduto registrado com sucesso!\n");
			system("pause");
			menu(contador);
		}
	}else{
		printf("Limite máximo de produtos atingido.\n");
		system("pause");
		system("cls");
		menu(contador);
	}
}

//1.2
//Nota: em tese funcionando.

void atualizarproduto(int contador[]){
	int code, i=0, respp, error=0;
	printf("Informe o código do produto a ser atualizado: ");
	scanf("%d", &code);
	while(i<2){
		if(code==Produto[i].codigo){
			printf(":::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::\n");
			printf("1 - Nome\n");
			printf("2 - Quantidade\n");
			printf("3 - Quantidade mínima\n");
			printf("4 - Preço de compra\n");
			printf("5 - Preço de venda\n");
			printf("6 - Situação\n");
			printf(":::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::\n");
			printf("Informe o que deseja alterar: ");
			scanf("%d", &respp);
			if(respp==1){
				printf("\nInforme o novo nome: ");
				scanf("%s", &Produto[i].nome[30]);
			}else if(respp==2){
				printf("Informe a nova quantidade: ");
				scanf("%d", &Produto[i].qtd);
			}else if(respp==3){
				printf("Informe a nova quantidade mínima: ");
				scanf("%d", &Produto[i].qtdMin);
			}else if(respp==4){
				printf("Informe o novo preço de compra: ");
				scanf("%d", &Produto[i].precoCompra);
			}else if(respp==5){
				printf("Informe o novo preço de venda: ");
				scanf("%d", &Produto[i].precoVenda);
			}else if(respp==6){
				printf("Informe a nova situação: ");
				scanf("%s", &Produto[i].situacao);
			}else{
				printf("Opção inválida.");
				system("pause");
				system("cls");
				menu(contador);
			}
		}
		i++;
	}
	system("pause"); 
	system("cls");
	menu(contador);	
}

//1.3
//Nota: em tese funcionando. Tem um glich de excluir produto antes de nenhum ser registrado, esse com código 0. Resolver.
void excluirproduto(int contador[]){
	int codem, i=0, error=0;
	printf("Informe o código do produto a ser excluído: ");
	scanf("%d", &codem);
	while(i<2){
		if(codem==Produto[i].codigo && Produto[i].situacao!='I'){
			Produto[i].situacao = 'I';
			printf("Produto excluído com sucesso!\n");
			system("pause");
			system("cls");
			menu(contador);
		}else{
			error++;
		}
		++i;
	}
	if(error==2){
		printf("Produto não encontrado no sistema.\n");
		system("pause");
		system("cls");
		menu(contador);
	}
}

/*1.4

Está full 'comentado' porque não está funcional.

void menupesquisa(int contador[]){
	char name[30];
	int result, ii, errorr=0;
	printf("Insira o nome do produto: ");
	scanf("%s", &name);
	ii=0;
	while(ii<2){
		result = strcmp(Produto[ii].nome, name);
		if(result==0){
			printf("%d \n", Produto[ii].codigo);
			printf("%s \n", Produto[ii].nome);
			printf("%d \n", Produto[ii].qtd);
			printf("%d \n", Produto[ii].precoVenda);
			system("pause");
			system("cls");
			menuprodutos(contador);
		}else{
			errorr++;
		}
		ii++;	
	}
	if(errorr==2){
		printf("Não foi possível encontrar o produto no sistema.\n");
		system("pause");
		system("cls");
		menu(contador);
	}
}
*/
