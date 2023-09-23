import java.io.File;
import java.util.Scanner;

public class Loader 
{
  public static void main(String[] args) 
  {
    try 
    {
      File file = new File("dataset.csv");
      Scanner sc = new Scanner(file);
      String data = sc.nextLine();
      String[] lines = data.split("\n");
      int vendaDebito = 0;
      int vendaCredito = 0;
      int vendaMesUm = 0;
      int vendaMesDois = 0;
      int vendaMesTres = 0;
      int somaTt = 0;
      int meta = 10000;

      
      // Leitura e impressão dos dados do arquivo:

      while (sc.hasNextLine()) 
      {        
        String tester = sc.nextLine();
        for (String NaoSeiPorQueMasTemQueExistir : lines) {
            String[] line = tester.split(";");
            // System.out.println(line[4]);
            int convert2 = Integer.parseInt(line[2]);
            int convert3 = Integer.parseInt(line[3]);
            int convert4 = Integer.parseInt(line[4]);
            int convert5 = Integer.parseInt(line[5]);
            int convert6 = Integer.parseInt(line[6]);
            
            vendaDebito += convert2;
            vendaCredito += convert3;
            vendaMesUm += convert4;
            vendaMesDois += convert5;
            vendaMesTres += convert6;
            }

        }
    System.out.println("\nRELATÓRIO DE VENDAS DA 'BRENO SALES TI SOLUTIONS':");
    System.out.println("--+--++---+---+-----+++-----+------+++-----++-");
    System.out.println("TOTAL DE VENDAS NO DEBITO: " + vendaDebito);
    System.out.println("TOTAL DE VENDAS NO CREDITO: "+ vendaCredito);
    System.out.println("--+--++---+---+-----+++-----+------+++-----++-");
    System.out.println("TOTAL DE VENDA NO PRIMEIRO MÊS: " + "R$" + vendaMesUm);
    System.out.println("TOTAL DE VENDA NO SEGUNDO MÊS: " + "R$" + vendaMesDois);
    System.out.println("TOTAL DE VENDA NO TERCEIRO MÊS: " + "R$" + vendaMesTres);
    System.out.println("--+--++---+---+-----+++-----+------+++-----++-");
    somaTt = vendaMesUm + vendaMesDois + vendaMesTres;
    String metaBatida = somaTt < meta ? "VENDA MAIS, ESTÁ A BAIXO DA META!" : "META BATIDA!";
    System.out.println("--+--++---+---+-----+++-----+------+++-----++-");
    System.out.println("TOTAL DE VENDAS NO MÊS: R$" + somaTt );
    System.out.println(metaBatida);


        // System.out.println(colums[4]);
        // System.out.println(colums[5]);
        // System.out.println(colums[6]);
       sc.close();   
  
    }
    //Tratamento de erro:
    catch (Exception e) 
    {
        System.out.println("Erro:");
        e.printStackTrace();

    }
  }
}