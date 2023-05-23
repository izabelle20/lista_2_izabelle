# lista_2_izabelle


#include <stdio.h>
#include <string.h>

typedef struct {
    char nome[50];
    int funcional;
    char titulacao[20];
} Professor;

typedef struct {
    char nome[50];
    int codigo;
    int carga_horaria;
    Professor professor_responsavel;
} Disciplina;

typedef struct {
    char nome[50];
    int matricula;
    int idade;
} Estudante;


int le_valida_idade(int idade) {
    if (idade >= 16 && idade <= 26) {
        return 1; 
    } else {
        return 0; 
    }
}

void bubble_sort(Estudante estudantes[], int tamanho) {
    int i, j;
    Estudante temp;
    
    for (i = 0; i < tamanho - 1; i++) {
        for (j = 0; j < tamanho - i - 1; j++) {
            if (estudantes[j].idade > estudantes[j + 1].idade) {
                temp = estudantes[j];
                estudantes[j] = estudantes[j + 1];
                estudantes[j + 1] = temp;
            }
        }
    }
}

int main() {
    printf("--------------------------------------------------------\n");
    printf("                        Lista 2                             ");
    printf("\n--------------------------------------------------------\n");
    
    Professor professores[3];
    
    strcpy(professores[0].nome, "Jose");
    professores[0].funcional = 123;
    strcpy(professores[0].titulacao, "Mestre");
    
    strcpy(professores[1].nome, "Maria");
    professores[1].funcional = 456;
    strcpy(professores[1].titulacao, "Doutor");
    
    strcpy(professores[2].nome, "Joao");
    professores[2].funcional = 789;
    strcpy(professores[2].titulacao, "Especialista");
    
    Disciplina disciplinas[2];
    
    strcpy(disciplinas[0].nome, "IHC - Interação Humana e Compultador");
    disciplinas[0].codigo = 985;
    disciplinas[0].carga_horaria = 60;
    disciplinas[0].professor_responsavel = professores[0];
    
    strcpy(disciplinas[1].nome, "Algoritmo e Programacao Estruturadas");
    disciplinas[1].codigo = 222;
    disciplinas[1].carga_horaria = 80;
    disciplinas[1].professor_responsavel = professores[1];
    
 
    Estudante estudantes[15];
    
    strcpy(estudantes[0].nome, "Manuel");
    estudantes[0].matricula = 1001;
    estudantes[0].idade = 20;
    
    strcpy(estudantes[1].nome, "Carlos");
    estudantes[1].matricula = 1002;
    estudantes[1].idade = 22;
    
    strcpy(estudantes[2].nome, "eduarda");
    estudantes[2].matricula = 1003;
    estudantes[2].idade = 26;
    
    strcpy(estudantes[3].nome, "Rafael");
    estudantes[3].matricula = 1004;
    estudantes[3].idade = 21;
    
    strcpy(estudantes[4].nome, "Benicio");
    estudantes[4].matricula = 1005;
    estudantes[4].idade = 16;
    
    strcpy(estudantes[5].nome, "Lais");
    estudantes[5].matricula = 1006;
    estudantes[5].idade = 17;
    
     strcpy(estudantes[6].nome, "Manuel");
    estudantes[6].matricula = 1007;
    estudantes[6].idade = 18;
    
    strcpy(estudantes[7].nome, "Mariana");
    estudantes[7].matricula = 1008;
    estudantes[7].idade = 19;
    
    strcpy(estudantes[8].nome, "Marcia");
    estudantes[8].matricula = 1009;
    estudantes[8].idade = 23;
    
    strcpy(estudantes[9].nome, "Ivonete");
    estudantes[9].matricula = 1010;
    estudantes[9].idade = 16;
    
    strcpy(estudantes[10].nome, "Francisco");
    estudantes[10].matricula = 1011;
    estudantes[10].idade = 17;
    
    strcpy(estudantes[11].nome, "Lorrane");
    estudantes[11].matricula = 1012;
    estudantes[11].idade = 25;
    
    strcpy(estudantes[12].nome, "Frorinda");
    estudantes[12].matricula = 1013;
    estudantes[12].idade = 21;
    
    strcpy(estudantes[13].nome, "Ana Luisa");
    estudantes[13].matricula = 1014;
    estudantes[13].idade = 22;
    
    strcpy(estudantes[14].nome, "Ana Vitoria");
    estudantes[14].matricula = 1015;
    estudantes[14].idade = 22;
    
    int matriculados_disciplina1 = 10; 

  
    for (int i = 2; i < 15; i++) {
        if (matriculados_disciplina1 == 10) {
            break;
        }


        strcpy(estudantes[i].nome, "Estudante");
        estudantes[i].matricula = 1003 + i;
        estudantes[i].idade = 16 + i;
        matriculados_disciplina1++;
    }

    printf("Relatório dos alunos matriculados na primeira disciplina ordenados por idade:\n");
    printf("codigo_disciplina  nome_professor nome_estudante idade_estudante\n");
    for (int i = 0; i < matriculados_disciplina1; i++) {
        printf("    %d                %s              %s           %d\n", disciplinas[0].codigo, disciplinas[0].professor_responsavel.nome, estudantes[i].nome, estudantes[i].idade);
    }

    bubble_sort(estudantes, matriculados_disciplina1);

    printf("\nRelatório dos alunos matriculados na segunda disciplina ordenados por idade (em ordem decrescente):\n");
    printf("codigo_disciplina  nome_professor nome_estudante idade_estudante\n");
    for (int i = matriculados_disciplina1 - 1; i >= 0; i--) {
        printf("    %d                %s             %s            %d\n", disciplinas[1].codigo, disciplinas[1].professor_responsavel.nome, estudantes[i].nome, estudantes[i].idade);
    }

    return 0;
}
