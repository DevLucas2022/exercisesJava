# javaExercises
<h2>Exercícios de java sobre lógica de programação </h2>


*1) Faça um programa na Linguagem Java para ler dois valores inteiros
para as variáveis A e B e efetuar a troca dos valores de forma que a
variável A passe a possuir o valor da variável B e a variável B passe
a possuir o valor da variável A. Apresentar os valores trocados.*

```java
public class Main{
    public static void main(String[] args){
        Scanner entrada = new Scanner(System.in);
        Integer a,b,aux;

  
        System.out.println("Digite o valor que deseja armazenar em A ");
        a = entrada.nextInt();
        System.out.println("Digite o valor que deseja armazenar em B ");
        b = entrada.nextInt();
        
        aux = a;
        a = b;
        b = aux;
        System.out.println("A = "+a+" B = "+b);
    
}
```

*2) Faça um programa na Linguagem Java que leia 3 (três) valores inteiros e
apresente os 3 números em ordem crescente.*

```java
import java.util.Arrays;
import java.util.Scanner;

public class Main{
    public static void main(String[] args){
        Scanner sc = new Scanner(System.in);
        int[] lista = new int[3];
        System.out.println("Digite os números");
        for(int i = 0;i<3;i++){
            lista[i] = sc.nextInt();
            System.out.println("-----------------------------");
        }
        Arrays.sort(lista);
        System.out.println("Estes são os números em ordem : ");
        for(int i = 0; i<3;i++){
            System.out.println("-----------------------------");
            System.out.println(lista[i]);
        }
    }
}
```

*3)Faça um programa na Linguagem Java que efetue a leitura de cinco
números inteiros e identificar o maior e o menor valor. Não execute a
ordenação de valores.*

```java
import java.util.Arrays;
import java.util.Scanner;

public class App{
    public static void main(String[] args){
        int lista[] = new int[5];
        Scanner sc = new Scanner(System.in);
        System.out.println("Digite 5 valores inteiros :");
        for(int i = 0; i< lista.length; i++){
            lista[i] = sc.nextInt();
        }
        Arrays.sort(lista);
        System.out.println("O maior valor é o "+lista[4]);
        System.out.println("O menor valor é o "+lista[0]);
         
    }
}
```

*4)Uma empresa concederá um aumento de salário aos seus funcionários,
variável de acordo com o cargo, conforme a tabela abaixo. Faça um programa
na Linguagem Java que leia o salário e o cargo de um funcionário e calcule o
novo salário. Se o cargo do funcionário não estiver na tabela, ele deverá,então, receber 40% de aumento. Mostre o salário antigo, o novo salário e a
diferença.*
```java
import java.util.Scanner;

public class Main{
    public static void main(String[] args){
        Scanner sc = new Scanner(System.in);
        
        System.out.println("Código     Cargo     Percentual");
        System.out.println(" 101     Gerente         10%   ");
        System.out.println(" 102     Engenheiro      20%   ");
        System.out.println(" 103     Técnico         30%   ");

        System.out.println("-------------------------");
        System.out.println("Digite o seu cargo :");
        String a = sc.next();
        System.out.println("Digite o seu salário : ");
        double b = sc.nextDouble();
        
        switch(a){
            case "Gerente":
            System.out.println("Seu salário irá para R$"+(b + (b*0.10)));
            break;
            case "Engenheiro":
            System.out.println("Seu salário irá para R$"+(b + (b*0.20)));
            break;
            case "Técnico":
            System.out.println("Seu salário irá para R$"+(b + (b*0.30)));
            break;
            default:
            System.out.println("Seu salário irá para R$"+(b + (b*0.40)));
        }

    }
}
```

<h2> Criação de Classes, Atributos e Métodos </h2>

*5)Fazer um programa para ler os dados de uma conta corrente*
```java
// Lucas de Oliveira Santos
// Exercicío para criação de atributos e métodos de uma conta bancária
public class Conta {
   private String nomeCorrentista;
   private String sexo;
   private int idade;
   private int numeroConta;
   private boolean contaConjunta;
   private double Saldo;

    

   public String getNomeCorrentista(){
    return nomeCorrentista;
   }
 
   public void  setNomeCorrentista(String nomeCorrentista){
    this.nomeCorrentista = nomeCorrentista;
   }

   public String getSexo(){
    return sexo;
   }
   
   public void setSexo(String sexo){
    this.sexo = sexo;
   }

   public int getIdade(){
    return idade;
   }

   public void setIdade(int idade){
    this.idade = idade;
   }

   public int getNumeroConta(){
    return numeroConta;
   }

   public void setNumeroConta(int numeroConta){
    this.numeroConta = numeroConta;
   }

   public boolean getContaConjunta(){
    return contaConjunta;
   }

   public void setContaConjunta(boolean contaConjunta){
    this.contaConjunta = contaConjunta;
   }

   public double getSaldo(){
    return Saldo;
   }
   public void setSaldo(double Saldo){
    this.Saldo = Saldo;
   }

   public void Saque(double Saldo, double valor){
    if(Saldo<0){
        System.out.println("Você não tem saldo suficiente");
    }else{
        Saldo = Saldo - valor;
        System.out.println("Seu saque foi realizado, você possui: "+Saldo);
    }
   }
   public void Saldo(){
    System.out.println("Nome correntista: "+nomeCorrentista);
    System.out.println("Numero Conta: "+numeroConta);
    System.out.println("Conta Conjunta: "+contaConjunta);
    System.out.println("Saldo: "+Saldo);
   }
   
   public void Deposito(double valorDepositar){
    Saldo = Saldo + valorDepositar;
    System.out.println("Seu valor após esse depósito é: "+ Saldo);
   }
}
```
<h3> Instanciando e declarando a Classe </h3>

```java
// LUCAS DE OLIVEIRA SANTOS
// RA : 
// main.java
public class main{

    public static void main(String[] args) {
                Conta conta1 = new Conta();
                Conta conta2 = new Conta();
                Conta conta3 = new Conta();
        
                conta1.setNomeCorrentista("Fernando");
                conta2.setNomeCorrentista("Maria");
                conta3.setNomeCorrentista("Joao");

                conta1.setNumeroConta(1234);
                conta2.setNumeroConta(5312);
                conta3.setNumeroConta(9621);

                conta1.setContaConjunta(false);
                conta2.setContaConjunta(true);
                conta3.setContaConjunta(true);

                conta1.setSaldo(1500.00);
                conta2.setSaldo(530.31);
                conta3.setSaldo(4325.12);

                conta1.setSexo("Masculino");
                conta2.setSexo("Feminino");
                conta3.setSexo("Masculino");

                conta1.setIdade(29);
                conta2.setIdade(45);
                conta3.setIdade(54);
            }
    }
``` 
