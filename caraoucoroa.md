#include <stdio.h>
#include <stdlib.h>
#include <time.h> // biblioteca para o sran(time(NULL))

//aqui é a função que valida se a pessoa quer continuar o jogo ou não
int continuar(){
 char continuar;

  printf("vai continuar véi?:"); // imprime a pergunta se pessoa quer continuar jogando
  scanf("  %c", &continuar); //aloca na memória/lê a resposta do usuário  - tem espeço entre o " e o %c pq o código tava lendo o buffer ao apertar enter e só rodava duas vezes
 
 if (continuar == 's'|| continuar == 'S'){   //condição de se a resposta do usuário for 's' ou 'S' então o programa roda

   return 1; // retorna valor verdadeiro e continua o jogo
 }
  else {

    return 0; //retorno valor falso e para o jogo  
  }

    
}


int main(){

  srand(time(NULL)); // função que gera números aleatórios 
  int comecar = 1; //começa o jogo já com verdeiro para iniciar código jogando

  while (comecar){   //comecar só retorna 1 ou 0 pq da função continuar que faz isso
  int cara_coroa = rand()%2; // estabelece que o valor aleatório vá de 0 à 1 - o 2 ali está dividindo o valor que rand() gerar e pegando seu resto para saber se vai ser 0 ou 1 ( cara ou coroa)

// condição para ser cara ou coroa
  if (cara_coroa == 0){
  printf("cara\n");
  }
  else {
  printf("coroa\n");
  }
  comecar = continuar(); // chama a função continuar para saber se vai continuar o loop
  }

  
}
