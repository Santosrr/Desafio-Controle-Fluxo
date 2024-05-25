# Contador

Este projeto é um programa Java que recebe dois parâmetros do usuário e imprime uma contagem entre eles. Se o segundo parâmetro não for maior que o primeiro, uma exceção personalizada é lançada.

Descrição
O programa solicita ao usuário dois números inteiros. O primeiro número deve ser menor que o segundo. Se essa condição for satisfeita, o programa imprime os números de 1 até a diferença entre o segundo e o primeiro número. Caso contrário, uma exceção personalizada é lançada, informando que o segundo número deve ser maior que o primeiro.


Estrutura do Código
Contador.java
Este é o arquivo principal que contém a lógica do programa.

java
Copy code
import java.util.Scanner;

public class Contador {
    public static void main(String[] args) {
        Scanner terminal = new Scanner(System.in);
        System.out.println("Digite o primeiro parâmetro");
        int parametroUm = terminal.nextInt();
        System.out.println("Digite o segundo parâmetro");
        int parametroDois = terminal.nextInt();
        
        try {
            // Chamando o método contendo a lógica de contagem
            contar(parametroUm, parametroDois);
        
        } catch (ParametrosInvalidosException exception) {
            // Imprimir a mensagem: O segundo parâmetro deve ser maior que o primeiro
            System.out.println(exception.getMessage());
        }

        terminal.close();
    }

    static void contar(int parametroUm, int parametroDois) throws ParametrosInvalidosException {
        // Validar se parametroUm é MAIOR que parametroDois e lançar a exceção
        if (parametroUm >= parametroDois) {
            throw new ParametrosInvalidosException("O segundo parâmetro deve ser maior que o primeiro");
        }
        
        int contagem = parametroDois - parametroUm;
        // Realizar o for para imprimir os números com base na variável contagem
        for (int i = 1; i <= contagem; i++) {
            System.out.println("Imprimindo o número " + i);
        }
    }
}
ParametrosInvalidosException.java
Este é o arquivo que define a exceção personalizada.

java
Copy code
public class ParametrosInvalidosException extends Exception {
    public ParametrosInvalidosException(String mensagem) {
        super(mensagem);
    }
}
Como Executar
Certifique-se de ter o JDK instalado em sua máquina.
Compile os arquivos Java:
sh
Copy code
javac Contador.java ParametrosInvalidosException.java
Execute o programa:
sh
Copy code
java Contador
Siga as instruções na tela para inserir os parâmetros.
Exemplo de Uso
Copy code
Digite o primeiro parâmetro
3
Digite o segundo parâmetro
7
Imprimindo o número 1
Imprimindo o número 2
Imprimindo o número 3
Imprimindo o número 4
Se o primeiro parâmetro for maior ou igual ao segundo:

mathematica
Copy code
Digite o primeiro parâmetro
5
Digite o segundo parâmetro
3
O segundo parâmetro deve ser maior que o primeiro
Contribuindo
Sinta-se à vontade para abrir issues e enviar pull requests. Para grandes alterações, abra primeiro uma issue para discutir o que você gostaria de mudar.



The `JAVA PROJECTS` view allows you to manage your dependencies. More details can be found [here](https://github.com/microsoft/vscode-java-dependency#manage-dependencies).
