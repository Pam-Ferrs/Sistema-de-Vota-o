# Sistema-de-Vota-o
/***********************************/
/* Aluno:Leonardo Henrique         */
/* Aluno:Pamela Ferreira           */
/* Aluno:Rhayssa Raimundo          */
/* Linguagem de Programacao        */
/* Prof. Eliane                    */
/***********************************/
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

/* run this program using the console pauser or add your own getch, system("pause") or input loop */

int main(int argc, char *argv[]) {
	
	int i = 0;
	
	//::. Variavel para colocar o numero de eleitores .::
	int qtdEleitores = 1;
	int indiceMaisVotado[2] = {0, 0};
	int qdtMaisVotados[2] = {0, 0};
	
	char votosPrefeito[qtdEleitores][4];
	char votosVereador[qtdEleitores][4];
	int votosContadosPrefeito[6] = {0, 0, 0, 0, 0, 0};
	int votosContadosVereador[6] = {0, 0, 0, 0, 0, 0};
	int votosPartidos[2] = {0, 0};
	 
	 do {
	 	printf("\nEleitor %d\n\n", i + 1);
	 	
	 	printf("\nREALIZE SEU VOTO PARA PREFEITO:");
	 	scanf("%s", &votosPrefeito[i]);
	 	
	 	printf("\nREALIZE SEU VOTO PARA VEREADOR:");
	 	scanf("%s", &votosVereador[i]);
	 	
	 	i = i + 1;
	 } while(i < qtdEleitores);
	 
	 printf("\nVOTACAO INDIVIDUAL:\n");
	 i = 0;
	 while(i < qtdEleitores) {
	 	printf("\nEleitor %d\n\n", i + 1);
	 	printf("Voto ao Candidato à Prefeitura..: %s\n", votosPrefeito[i]);
	 	printf("Voto ao Candidato a Vereador....: %s\n", votosVereador[i]);
	 	
	 	i = i + 1;
	 }
	 
	 i = 0;
	 //conta votos prefeito
	 while(i < qtdEleitores) {
	 	
	    if (votosPrefeito[i][(strlen (votosPrefeito[i]) -1)] == '1' ) {
	    	votosContadosPrefeito[0] = votosContadosPrefeito[0] + 1;
	    	votosPartidos[0] = votosPartidos[0] + 1;
		} else if ( votosPrefeito[i][(strlen (votosPrefeito[i]) -1)] == '2' ) {
	    	votosContadosPrefeito[1] = votosContadosPrefeito[1] + 1;
	    	votosPartidos[0] = votosPartidos[0] + 1;
		} else if ( votosPrefeito[i][(strlen (votosPrefeito[i]) -1)] == '3' ) {
	    	votosContadosPrefeito[2] = votosContadosPrefeito[2] + 1;
	    	votosPartidos[1] = votosPartidos[1] + 1;
		} else if ( votosPrefeito[i][(strlen (votosPrefeito[i]) -1)] == '4' ) {
	    	votosContadosPrefeito[3] = votosContadosPrefeito[3] + 1;
	    	votosPartidos[1] = votosPartidos[1] + 1;
		} else if ( votosPrefeito[i][(strlen (votosPrefeito[i]) -1)] == 'b' || votosVereador[i][(strlen (votosVereador[i]) -1)] == 'B') {
	    	votosContadosPrefeito[4] = votosContadosPrefeito[4] + 1;
		} else {
			votosContadosPrefeito[5] = votosContadosPrefeito[5] + 1;
		}
            
	 	i = i + 1;
	 }
	 
	 i = 0;
	 //conta votos prefeito
	 while(i < qtdEleitores) {
	 	
	    if (votosVereador[i][(strlen (votosVereador[i]) -1)] == '1' ) {
	    	votosContadosVereador[0] = votosContadosVereador[0] + 1;
	    	votosPartidos[0] = votosPartidos[0] + 1;
		} else if ( votosVereador[i][(strlen (votosVereador[i]) -1)] == '2' ) {
	    	votosContadosVereador[1] = votosContadosVereador[1] + 1;
	    	votosPartidos[0] = votosPartidos[0] + 1;
		} else if ( votosVereador[i][(strlen (votosVereador[i]) -1)] == '3' ) {
	    	votosContadosVereador[2] = votosContadosVereador[2] + 1;
	    	votosPartidos[1] = votosPartidos[1] + 1;
		} else if ( votosVereador[i][(strlen (votosVereador[i]) -1)] == '4' ) {
	    	votosContadosVereador[3] = votosContadosVereador[3] + 1;
	    	votosPartidos[1] = votosPartidos[1] + 1;
		} else if ( votosVereador[i][(strlen (votosVereador[i]) -1)] == 'b' || votosVereador[i][(strlen (votosVereador[i]) -1)] == 'B') {
	    	votosContadosVereador[4] = votosContadosVereador[4] + 1;
		} else {
			votosContadosVereador[5] = votosContadosVereador[5] + 1;
		}
            
	 	i = i + 1;
	 }
	 
	for (i = 0; i < 6; ++i) {
        if (qdtMaisVotados[0] < votosContadosPrefeito[i]) {
        	qdtMaisVotados[0] = votosContadosPrefeito[i];
            indiceMaisVotado[0] = i;
		}
		
		if (qdtMaisVotados[1] < votosContadosVereador[i]) {
        	qdtMaisVotados[1] = votosContadosVereador[i];
            indiceMaisVotado[1] = i;
		}   
    }
	 
	 printf("\nNUMERO DE VOTOS PARA O PARTIDO PDB.....: %d", votosPartidos[0]);
	 printf("\nNUMERO DE VOTOS PARA O PARTIDO PSB.....: %d", votosPartidos[1]);
	 
	 printf("\nNUMERO DE VOTOS PARA O CANDIDATO C1.....: %d", votosContadosPrefeito[0]);
	 printf("\nNUMERO DE VOTOS PARA O CANDIDATO C2.....: %d", votosContadosPrefeito[1]);
	 printf("\nNUMERO DE VOTOS PARA O CANDIDATO C3.....: %d", votosContadosPrefeito[2]);
	 printf("\nNUMERO DE VOTOS PARA O CANDIDATO C4.....: %d", votosContadosPrefeito[3]);
	 printf("\nNUMERO DE VOTOS BRANCOS.................: %d", votosContadosPrefeito[4]);
	 printf("\nNUMERO DE VOTOS NULOS...................: %d", votosContadosPrefeito[5]);
	 
	 printf("\nNUMERO DE VOTOS PARA O CANDIDATO V1.....: %d", votosContadosVereador[0]);
	 printf("\nNUMERO DE VOTOS PARA O CANDIDATO V2.....: %d", votosContadosVereador[1]);
	 printf("\nNUMERO DE VOTOS PARA O CANDIDATO V3.....: %d", votosContadosVereador[2]);
	 printf("\nNUMERO DE VOTOS PARA O CANDIDATO V4.....: %d", votosContadosVereador[3]);
	 printf("\nNUMERO DE VOTOS BRANCOS.................: %d", votosContadosVereador[4]);
	 printf("\nNUMERO DE VOTOS NULOS...................: %d", votosContadosVereador[5]);
	 
	 printf("\n\nCANDIDATO A PREFEITO MAIS VOTADO........: C%d - %d votos", indiceMaisVotado[0] + 1, qdtMaisVotados[0]);
	 
	 printf("\nCANDIDATO A VEREADOR MAIS VOTADO........: V%d - %d votos", indiceMaisVotado[1] + 1, qdtMaisVotados[1]);													
	
	return 0;
}


