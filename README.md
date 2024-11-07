 /*1. Manipulação Básica de Strings
Exercícios introdutórios para trabalhar com leitura e impressão de strings.*/

/*Exercício 1: Crie um programa que leia uma string e exiba seu conteúdo. Em seguida, exiba o comprimento da string usando a função strlen().*/
    #include <string.h>  

    int main() {
    char str[100]; 
         
    printf("Digite uma string: ");
     fgets(str, sizeof(str), stdin); 
    printf("Conteúdo da string: %s", str);
      str[strcspn(str, "\n")] = 0;
    printf("Comprimento da string: %zu\n", strlen(str));

/*Exercício 2: Implemente um programa que leia duas strings do usuário e verifique se elas são iguais. Exiba uma mensagem informando se as strings são iguais ou diferentes. Use a função strcmp() para a comparação.*/

  #include <stdio.h>
  #include <string.h>

    int main() {
    char str1[100], str2[100];

            
    printf("Digite a primeira string: ");
    fgets(str1, sizeof(str1), stdin);
    str1[strcspn(str1, "\n")] = '\0';  

    printf("Digite a segunda string: ");
    fgets(str2, sizeof(str2), stdin);
    str2[strcspn(str2, "\n")] = '\0';  

      if (strcmp(str1, str2) == 0) {
          printf("As strings são iguais.\n");
          } else {
            printf("As strings são diferentes.\n");
            }

/*Exercício 3: Escreva um programa que leia uma string do usuário e exiba cada caractere da string em uma linha separada.*/

    #include <stdio.h>

    int main() {
    char str[100];  
              
    printf("Digite uma string: ");
    fgets(str, sizeof(str), stdin);

    for (int i = 0; str[i] != '\0'; i++) {
                   
    if (str[i] != '\n') {
      printf("%c\n", str[i]);
        }
   }
                
/*Exercício 4: Implemente um programa que leia uma string e verifique quantas vezes o caractere 'a' aparece nela. Exiba o total de ocorrências.*/
        int main() {
            char str[100];  
            int count = 0;  

        
    printf("Digite uma string: ");
    fgets(str, sizeof(str), stdin);

    for (int i = 0; str[i] != '\0'; i++) {
        if (str[i] == 'a' || str[i] == 'A') {
         count++; 
        }
    }
    printf("O caractere('a'ou 'A') aparece %d vez(es) na string.\n", count);
/*2. Manipulação de Strings com Funções de Biblioteca
 Exercícios para introduzir funções padrão da biblioteca <string.h> para manipulação de strings.*/
/*Exercício 5: Crie um programa que leia uma string e a copie para outra variável usando a função strcpy(). Exiba as duas strings para verificar se a cópia foi bem-sucedida.*/
    int main() {
    char str1[100], str2[100];  
                
    printf("Digite uma string: ");
    fgets(str1, sizeof(str1), stdin);
    str1[strcspn(str1, "\n")] = '\0';  

                
    strcpy(str2, str1);
    printf("A string original: %s\n", str1);
    printf("A string copiada: %s\n", str2);
        
/*Exercício 6: Implemente um programa que leia duas strings e as concatene em uma nova string. Use a função strcat() para realizar a concatenação e exiba o resultado.*/
    int main() {
    char str1[100], str2[100], resultado[200];  
   
    printf("Digite a primeira string: ");
    fgets(str1, sizeof(str1), stdin);
    str1[strcspn(str1, "\n")] = '\0'; 

    printf("Digite a segunda string: ");
    fgets(str2, sizeof(str2), stdin);
    str2[strcspn(str2, "\n")] = '\0';  
    strcpy(resultado, str1);
    strcat(resultado, str2);

    printf("Resultado da concatenação: %s\n", resultado);
/*Exercício 7: Escreva um programa que leia uma string e substitua todos os caracteres minúsculos por maiúsculos. Utilize a função toupper() da biblioteca <ctype.h> para auxiliar na conversão.*/

    int main() {
    char str[100]; 

    printf("Digite uma string: ");
    fgets(str, sizeof(str), stdin);
    str[strcspn(str, "\n")] = '\0';  
    for (int i = 0; str[i] != '\0'; i++) {
    str[i] = toupper(str[i]); 
        }
    printf("A string com os caracteres em maiúsculo: %s\n", str);
/*3. Análise de Caracteres em Strings
Exercícios para prática de contagem e análise de caracteres individuais.*/

/*Exercício 8: Implemente um programa que leia uma string e conte o número de vogais presentes nela. Considere as vogais 'a', 'e', 'i', 'o', 'u' (maiúsculas e minúsculas).*/
        int contarvogais(char texto[]) {
            int contador = 0;
            for (int i = 0; i < strlen(texto); i++) {
            char letra = texto[i];
        if (letra == 'a' || letra == 'e' || letra == 'i' || letra == 'o' || letra == 'u' ||
        letra == 'A' || letra == 'E' || letra == 'I' || letra == 'O' || letra == 'U') {
    contador++;
    }
}
    return contador;
    }

   int main() {
  char texto[100];

printf("Digite uma string: ");
fgets(texto, sizeof(texto), stdin);

    int quantidadevogais = contarvogais(texto);
    printf("Número de vogais: %d\n", quantidadevogais);
       
/*Exercício 9: Crie um programa que leia uma string e conte o número de espaços em branco nela. Exiba o total de espaços.*/
    int contarespacos(char texto[]) {
    int contador = 0;
    for (int i = 0; i < strlen(texto); i++) {
        if (texto[i] == ' ') {
        contador++;
        }
    }
    return contador;
       }

    int main() {
    char texto[100];

    printf("Digite uma string: ");
    fgets(texto, sizeof(texto), stdin);

    int quantidade_espacos = contarespacos(texto);
    printf("Número de espaços em branco: %d\n", quantidadeespacos);
        
/*Exercício 10: Escreva um programa que leia uma string e conte o número de letras, dígitos e caracteres especiais presentes nela. Use as funções isalpha() e isdigit() da biblioteca <ctype.h> para verificar o tipo de cada caractere.*/


    int main() {
     char texto[100];
    int letras = 0, digitos = 0, especiais = 0;

    printf("Digite uma string: ");
    fgets(texto, sizeof(texto), stdin);

    for (int i = 0; texto[i] != '\0'; i++) {
        if (isalpha(texto[i])) {
        letras++;
        } else if (isdigit(texto[i])) {
            digitos++;
        } else if (!isspace(texto[i])) {
           especiais++;
            }
        }

    printf("Número de letras: %d\n", letras);
    printf("Número de dígitos: %d\n", digitos);
    printf("Número de caracteres especiais: %d\n", especiais);






















