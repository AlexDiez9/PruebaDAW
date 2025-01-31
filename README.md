package ActividadResuelta_8_3;
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        
    Scanner sc = new Scanner(System.in);
        
    HoraExacta_Mod h;
    byte valorHora, valorMin, valorSeg;
        
    System.out.println("¿Que hora es?");
    valorHora = sc.nextByte();
                    
    while(valorHora <= 24 && valorHora > 0){            
    System.out.println("Valor invalido");
    System.out.println("¿Que hora es?");
    valorHora = sc.nextByte();
    } 
        
    System.out.println("¿Y que minutos?");
    valorMin = sc.nextByte();
        
    while(valorMin <= 60 && valorMin > 0){            
    System.out.println("Valor invalido");
    System.out.println("¿Cuantos minutos hay?");
    valorMin = sc.nextByte();
    }
    
    System.out.println("¿En cuantos segundos?");
    valorSeg = sc.nextByte(); 
    
    while(valorSeg <= 60 && valorSeg > 0){            
    System.out.println("Valor invalido");
    System.out.println("¿Cuantos segundos hay?");
    valorSeg = sc.nextByte();
    }
        
    h = new  HoraExacta_Mod(valorHora, valorMin, valorSeg);
        
    byte opcion = 1;
        
     do{
        System.out.println("Elige una opcion");
        System.out.println("1. Ver la hora");
        System.out.println("2. Incrementar 1 minuto");
        System.out.println("3. Incrementar 1 segundo");
        System.out.println("4. Poner otra hora ");
        System.out.println("5. Comparar horas");
        System.out.println("6. Salir");
        opcion = sc.nextByte();
            
        System.out.println("");
           
        switch(opcion){
                
            case 1 ->{
                    System.out.println(h.toString());
            }                
            case 2 ->{
                h.inc();
            }
            case 3 ->{
                h.incSeg();
            }                
            case 4 ->{
                System.out.println("¿Que hora es?");
                byte valorHora2 = sc.nextByte();
                System.out.println("¿Y que minutos?");
                byte valorMin2 = sc.nextByte();
                System.out.println("¿En cuantos segundos?");
                byte valorSeg2 = sc.nextByte();
                h = new HoraExacta_Mod(valorHora2, valorMin2, valorSeg2);
            } 
            case 5 ->{
                  
                System.out.println("Dame la otra hora");
                System.out.println("Primero la hora");
                byte otraHora = sc.nextByte();
                System.out.println("Luego los minutos");
                byte otroMin = sc.nextByte();
                System.out.println("Ahora los segundos");
                byte otroSeg2 = sc.nextByte();
                   
                HoraExacta_Mod h2 = new HoraExacta_Mod(otraHora, otroMin, otroSeg2);
                    
                h.equals(h2);
            }                
            case 6 ->{
                System.out.println("¡Hasta pronto!");
            }                
            default-> System.out.println("Opcion incorrecta");            
        }    
     } while (opcion!= 6);
    }
}
