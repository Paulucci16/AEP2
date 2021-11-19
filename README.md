# AEP2
package teste;

import java.util.Scanner;

public class estoque {
    
    public static void main(String[] args) {
        
    Scanner ler = new Scanner(System.in); 
    Scanner dados = new Scanner(System.in);
    Scanner dados1 = new Scanner(System.in);            
    Scanner dados2 = new Scanner(System.in);
    Scanner dados3 = new Scanner(System.in);
    Scanner dados4 = new Scanner(System.in);
    Scanner dados5 = new Scanner(System.in);
    Scanner dados6 = new Scanner(System.in);
    Scanner dados7 = new Scanner(System.in);
    Controle produtoController = new Controle();
    produto c1 = new produto();
    
    
    int boi, rac, dia;
    int aft, qtdrac;
    String nome = "";
    String modelo = "";
    String tamanho = "";
    String raca = "";
    String qtdBoi = "";
    String ano = "";
    String numIdem = "";
    double preco = 0;
    Boolean g = true;
    int numopc = 0;
   

    
    while (g == true) {
       
        if (numopc == 0) {
            System.out.println(
            "Opçoes\n 1-Cadastrar produto\n 2-Soma Manual\n 3-Raça bovina\n 4-Sair\n ");
            System.out.print("nº: ");
            
            numopc = dados.nextInt();
            if(numopc == 4){
                g = false;
            }else{
                g = true;
            }
        }else{
        switch (numopc) {

            case 1:
                System.out.println("Nome do produto: ");
                nome = dados1.nextLine();
                c1.setNome(nome);

                System.out.println("Modelo do produto: ");
                modelo = dados2.nextLine();
                c1.setModelo(modelo);

                System.out.println("Tamanho do produto: ");
                tamanho = dados3.nextLine();
                c1.setTamanho(tamanho);

                System.out.println("Preço do produto: ");
                preco = dados.nextDouble();
                c1.setPreco(preco);

                System.out.println("\n Cadastrar mais produtos?\n  1-Sim\n  0-Não\n");
                numopc = dados.nextInt();

                produtoController.adicionar(c1);
                c1 = new produto();
                break;
               
            case 2: 
                System.out.println(" Informe o valor da Aftosa\n");
                aft = ler.nextInt();

                System.out.println("Informe a quantidade de Bovinos: ");
                boi = ler.nextInt(); 

                System.out.println("Informe a quantidade de ração (kg): ");
                qtdrac = ler.nextInt();

                System.out.println("Informe o valor da ração (kg): ");
                rac = ler.nextInt(); 

                System.out.println("Informe a quantidade de dias que deseja saber total da ração: ");
                dia = ler.nextInt(); 

                System.out.println("\nResultados:\n");
                System.out.println("Aftosa é aplicada anualmente, entao o custo é de: " + aft*boi + "R$");
                System.out.println("Bovino come em media 13 kg de ração por dia, entao os " + boi + " bovinos" + " irão se alimentar por " + qtdrac/13 + " dias ");
                System.out.println("Total de ração nos dias desejados: " + qtdrac*dia + "kg");
                System.out.println("Voce ira gastar com ração: " + qtdrac*rac + "R$\n");
                numopc = 0;
                break;
            case 3: 
                System.out.println("Raça do boi: \n");
                raca = dados4.nextLine();
                c1.setRaca(raca);
                   
                System.out.println("Quantidade de bovino: ");
                qtdBoi = dados5.nextLine();
                c1.setQtdBoi(qtdBoi);
                
                System.out.println("Ano de nascimento: ");
                ano = dados6.nextLine();
                c1.setAno(ano);

                System.out.println("Numero de identificação: ");
                numIdem = dados7.nextLine();
                c1.setNumIdem(numIdem);
                
                numopc = 0;
                break;
        }
    }
    
    produtoController.listaProdutos();
    
    }
    }

}
