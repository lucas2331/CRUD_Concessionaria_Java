# CRUD Concessionaria | Java

```java

package crudconcessionaria;
import java.util.ArrayList;
import java.util.Scanner;

public class CrudConcessionaria {

    public static void main(String[] args) {
        
        Scanner Leitor = new Scanner(System.in);

        String VerificaMenu1;
        
        AçõesCRUD Funções = new AçõesCRUD();
        ArrayList<AçõesCRUD> ListaTotal = new ArrayList();
        
        do{
            System.out.println("\n[X]Olá, bem vindo ao Crud de Concessionaria!");
            System.out.println("[1]Cadastrar.");
            System.out.println("[2]Apresentar.");
            System.out.println("[3]Alterar.");
            System.out.println("[4]Excluir.");
            System.out.println("[5]Sair.");
            System.out.println("[X]Escolha uma opção!");    
            VerificaMenu1 = Leitor.next();
            
            switch(VerificaMenu1){
                
                case "1":
                
                    Funções = new AçõesCRUD();
                    String Codigo, Nome, Ano, Combustivel, Configuração, Lugares, Tração;
                    
                    System.out.println("\n[X]Opção de cadastro!");
                    
                    System.out.println("\n[X]Digite o codigo do carro:");
                    Codigo = Leitor.next();
                    Funções.setCodigo(Codigo);
                    
                    System.out.println("\n[X]Digite o nome do carro:");
                    Nome = Leitor.next();
                    Funções.setNome(Nome);
                    
                    System.out.println("\n[X]Digite o ano do carro:");
                    Ano = Leitor.next();
                    Funções.setAno(Ano);
                    
                    System.out.println("\n[X]Digite o tipo do combustivel do carro:");
                    Combustivel = Leitor.next();
                    Funções.setCombustivel(Combustivel);
                    
                    System.out.println("\n[X]Digite a configuração do carro:");
                    Configuração = Leitor.next();
                    Funções.setConfiguração(Configuração);
                    
                    System.out.println("\n[X]Digite a quantidade de lugares do carro:");
                    Lugares = Leitor.next();
                    Funções.setLugares(Lugares);
                    
                    System.out.println("\n[X]Digite o tipo de tração do carro:");
                    Tração = Leitor.next();
                    Funções.setTração(Tração);
                    
                    ListaTotal.add(Funções);
                    
                break;
                
                case "2":
                    
                    System.out.println("\n[X]Opção de Apresentação!");
                    
                    if(ListaTotal.size() == 0){
                        System.out.println("[X]Nenhum usuário registrado!");
                    }
                    else{
                        for(int i = 0; i < ListaTotal.size(); i++){
                            System.out.println("\nCarro: " + i);
                            System.out.println("Codigo: "         + ListaTotal.get(i).getCodigo());
                            System.out.println("Nome: "           + ListaTotal.get(i).getNome());
                            System.out.println("Ano: "            + ListaTotal.get(i).getAno());
                            System.out.println("Combustivel: "    + ListaTotal.get(i).getCombustivel());
                            System.out.println("Configuração: "   + ListaTotal.get(i).getConfiguração());
                            System.out.println("Lugares: "        + ListaTotal.get(i).getLugares());
                            System.out.println("Tração: "         + ListaTotal.get(i).getTração());
                        }
                    }
                    
                    
                break;
                
                case "3":
                    
                    System.out.println("\n[X]Opção de Alteração!");
                    
                    if(ListaTotal.size() == 0){
                        System.out.println("[X]Nenhum usuário registrado!");
                    }
                    
                    else{
                        
                        int CarroAlteração;
                        int VerificaContadorVerifica = 0;
                    
                        System.out.println("\n[X]Digite o carro a ser alterado: ");
                        CarroAlteração = Leitor.nextInt();
                    
                        for(int i = 0; i < ListaTotal.size(); i++){
                            if(CarroAlteração == i){
                                VerificaContadorVerifica = VerificaContadorVerifica + 1;
                            }
                        }
                    
                        if(VerificaContadorVerifica == 0){
                            System.out.println("Nenhum carro encontrado nesse indice!");
                        }
                    
                        else{
                            
                            String CodigoAltera, NomeAltera, AnoAltera, CombustivelAltera, ConfiguraçãoAltera, LugaresAltera, TraçãoAltera;
                            
                            System.out.println("\n[X]Digite o codigo do carro: ");
                            CodigoAltera = Leitor.next();
                            ListaTotal.get(CarroAlteração).setCodigo(CodigoAltera);
                            
                            System.out.println("\n[X]Digite o nome do carro: ");
                            NomeAltera = Leitor.next();
                            ListaTotal.get(CarroAlteração).setNome(NomeAltera);
                        
                            System.out.println("\n[X]Digite o ano do carro: ");
                            AnoAltera = Leitor.next();
                            ListaTotal.get(CarroAlteração).setAno(AnoAltera);
                        
                            System.out.println("\n[X]Digite o tipo de combustivel do carro: ");
                            CombustivelAltera = Leitor.next();
                            ListaTotal.get(CarroAlteração).setCombustivel(CombustivelAltera);
                            
                            System.out.println("\n[X]Digite a configuração do carro: ");
                            ConfiguraçãoAltera = Leitor.next();
                            ListaTotal.get(CarroAlteração).setConfiguração(ConfiguraçãoAltera);
                        
                            System.out.println("\n[X]Digite a quantidade de lugares do carro: ");
                            LugaresAltera = Leitor.next();
                            ListaTotal.get(CarroAlteração).setLugares(LugaresAltera);
                        
                            System.out.println("\n[X]Digite o tipo de tração do carro: ");
                            TraçãoAltera = Leitor.next();
                            ListaTotal.get(CarroAlteração).setTração(TraçãoAltera);
                        }    
                    }
                    
                break;
                
                case "4":
                    
                    System.out.println("\n[X]Opção de Exclusão!");
                    
                    if(ListaTotal.size() == 0){
                        System.out.println("[X]Nenhum usuário registrado!");
                    }
                    
                    else{
                        
                        int CarroExclusão;
                        int VerificaContadorExclui = 0;
                    
                        System.out.println("\n[X]Digite o carro a ser excluido: ");
                        CarroExclusão = Leitor.nextInt();
                    
                        for(int i = 0; i < ListaTotal.size(); i++){
                            if(CarroExclusão == i){
                                VerificaContadorExclui = VerificaContadorExclui + 1;
                            }   
                        }
                    
                        if(VerificaContadorExclui == 0){
                            System.out.println("Nenhum carro encontrado nesse indice!");
                        }
                    
                        else{
                            ListaTotal.remove(CarroExclusão);
                        }
                    }
                    
                break;
                
                case "5":
                    
                    System.out.println("\n[X]Opção de saida. Obrigado!");
                    System.exit(0);
                    
                break;
                
                default:
                    System.out.println("\n[X]Digite uma opção válida!");
                break;
                
            }
            
        }while(VerificaMenu1 != "");  
    }
}

```
