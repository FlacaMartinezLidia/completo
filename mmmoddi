package CONCEPTOBS;
import java.io.*;
import java.util.*;

public class PRINCIPAL {

	Scanner scan= new Scanner(System.in);
	public static void main(String[] args) throws IOException {
		PRINCIPAL app = new PRINCIPAL();
		app.menu();

	}
	public void asignar() throws IOException {
	       Scanner sc=new Scanner(System.in);
	        File definicion =new File("entidad.txt");
	        
	        if(!definicion.exists()){
	            try{
	            FileWriter escribir=new FileWriter(definicion,true);

	            
	            String Entidad;
	            String nombre;
	            String tDat;
	            int longitud;
	            System.out.println("Ingrese nombre para la entidad");
	            Entidad =sc.nextLine();
	            
	            escribir.write(Entidad+"\r\n");
	            
	            Boolean seguir=false;
	            
	            while(seguir==false){
	            sc=new Scanner(System.in);
	            nombre=null;
	            tDat=null;
	            longitud=0;
	            System.out.println("Ingrese nombre del atributo");
	            nombre=sc.nextLine();
	            
	            System.out.println("seleccione tipo de dato");
	            System.out.println("1)String");
	            System.out.println("2)Date");
	            System.out.println("3)Long");
	            System.out.println("4)Double");
	            System.out.println("5)Integer");
	            
	            int dec=0;
	            dec=sc.nextInt();
	            switch(dec){
	                case 1:
	                    tDat="String";
	                break;
	                case 2:
	                    tDat="Date";
	                break;
	                case 3:
	                    tDat="Long";
	                break;
	                case 4:
	                    tDat="Double";
	                break;
	                case 5:
	                    tDat="Integer";
	                break;
	                default:
	                    tDat=null;
	                break;
	            }
	            
	            System.out.println("Ingrese longitud deseada, si el tipo de dato no lo necesita ingrese 0");
	            longitud=sc.nextInt();
	            
	            escribir.write(nombre+"\r\n");
	            escribir.write(tDat+"\r\n");
	            escribir.write(longitud+"\r\n");
	            System.out.println("entidad y atributos creados");

	            System.out.println("desea ingresar otra caracteristica?");
	            System.out.println("1)si");
	            System.out.println("cualquie numero)no");
	            int q=sc.nextInt();
	            
	            if(q!=1){
	                seguir=true;
	                escribir.close();
	            }
	            
	            }
	            
	        }catch(IOException e){
	                        System.out.println("Error de Archivo");
	        }catch(Exception e){
	                        System.out.println("Error de tipo de dato o nulo");
	        }
	        }
	        
	     
	        
	 
	    
	  
        
	}
	
	public void agregarReg() throws FileNotFoundException {
		Scanner sc= new Scanner(System.in);
		 Boolean terminar=false;
		    while(terminar==false){
		    
		    
		    System.out.println("OPERACION DE DATOS");
		    System.out.println("1)...........agregar registro");
		    System.out.println("2)...........LISTAR");
		    System.out.println("3)...........modificar registro");
		    int elecion=0;
		    elecion=sc.nextInt();
		    
		    String texto="";
		    String nEntidad="";
		    String nNombre="";
		    String tDato="";
		    
		    
		    
		    int longi;
		   
		    
		    if(elecion==1){
		    sc = new Scanner(System.in);
		    
		    try{
		    FileReader lector=new FileReader("entidad.txt");
		    BufferedReader contenido=new BufferedReader(lector);
		    RandomAccessFile salida = new RandomAccessFile("datos.dat","rw");
		  
		    salida.seek(salida.length());
		    
		    nEntidad=contenido.readLine();
		    
		    
		    
		    while((texto=contenido.readLine())!=null){
		        
		        try{
		        
		        sc=new Scanner(System.in);
		        
		    nNombre=texto;
		        
		    tDato=contenido.readLine();
		    
		    longi=Integer.parseInt(contenido.readLine());

		    
		    System.out.println("ingrese el "+nNombre+" ("+tDato+")");
		        
		    if(tDato.compareToIgnoreCase("String")==0){
		            String limit=sc.nextLine();
		            if(limit.length()>longi){
		                System.out.println("Dato excede el tamano predefinido de "+longi+" caracteres.");
		                
		            }
		            salida.writeUTF(limit);
		        }
		        if(tDato.compareToIgnoreCase("Integer")==0){
		            int S=sc.nextInt();
		            salida.writeInt(S);
		        }
		        if(tDato.compareToIgnoreCase("Date")==0){
		            System.out.println("Ingrese anio");
		            int anio=sc.nextInt();
		            System.out.println("Ingrese mes");
		            int mes=sc.nextInt();
		            System.out.println("Ingrese dia");
		            int dia=sc.nextInt();
		            
		            salida.writeInt(anio);
		            salida.writeInt(mes);
		            salida.writeInt(dia);
		        } 
		        if(tDato.compareToIgnoreCase("Long")==0){
		            long L=sc.nextLong();
		            salida.writeLong(L);
		        }
		        if(tDato.compareToIgnoreCase("Double")==0){
		            double D=sc.nextDouble();
		            salida.writeDouble(D);
		        }
		       
		        
		    
		 
		        }catch(Exception e){
		            System.out.println("Error con los datos intente otra vez");

		        }
		        
		    }
		    contenido.close();
		    salida.close();
		    }catch(IOException e){
		    System.out.println("Error al leer");
		    e.printStackTrace();
		    }
		    
		        
		    }
		    if(elecion ==2){        
		        try{
		        RandomAccessFile lec2 = new RandomAccessFile("datos.dat","rw");
		        FileInputStream fis = new FileInputStream("datos.dat");
		        File fichero=new File("datos.dat");
		        DataInputStream entrada = new DataInputStream(fis); 
		        FileReader lector=new FileReader("entidad.txt");
		        BufferedReader contenido=new BufferedReader(lector);
		        
		        String nn=contenido.readLine();
		        System.out.println(nn);
		    	long actual= lec2.getFilePointer();
				long fin   = lec2.length();
				long limite=0;
				while(actual==fin) {
					// entrada.seek(entrada.length());
		        
		        while((texto=contenido.readLine())!=null){
		      
		        String nm=texto;
		        String tipo=contenido.readLine();
		        contenido.readLine();
		        
		        if(tipo.compareToIgnoreCase("String")==0){
		            String n1=entrada.readUTF();
		            System.out.println(lec2.readUTF());
		            System.out.println(n1);
		        }
		        if(tipo.compareToIgnoreCase("Integer")==0){
		        	int n2=entrada.readInt();
		        	System.out.println(lec2.readInt());
		            System.out.println(n2);
		        }
		        if(tipo.compareToIgnoreCase("Date")==0){
		            int anio=entrada.readInt();
		            int mes=entrada.readInt();
		            int dia=entrada.readInt();
		                        System.out.println(dia+"/"+mes+"/"+anio);

		           
		        } 
		        if(tipo.compareToIgnoreCase("Long")==0){
		            long dato=entrada.readLong();
		            System.out.println(lec2.readLong());
		            System.out.println(dato);
		        }
		        if(tipo.compareToIgnoreCase("Double")==0){
		            double dato=entrada.readDouble();
		            System.out.println(lec2.readDouble());
		            System.out.println(dato);
		        }
				}
		        
		        }

		        entrada.close();
		        }catch(Exception e){
		        System.out.println("error con archivos");
		        e.printStackTrace();
		        }
		        
		        
		    }
		        
		    System.out.println("desea salir del programa?");
		    System.out.println("1)no");
		    System.out.println("0)si");

		    int f =sc.nextInt();
		        
		    if(f!=1){
		        terminar = true;
		    }
		    }
		    
		        
		        
		        
		        
		        
		    }
	public void menu() throws IOException {
		byte op1;
		do {
		System.out.println("\n menu de opciones");
   		System.out.println("1.Verificar si existe el archivo de Datos");
   		System.out.println("2.Crear Archivo");
   		System.out.println("3.CRAR ENTIDAD Y ATRIBUTOS ");
   		System.out.println("4.OPERAR REGISTROS");
   		
   		
   		
   		op1 = scan.nextByte();
 		switch(op1){
   		case 1 :
   		
   			if (verificarArchivo()){
				 System.out.print("\nEl archivo ya existe");
			 }else {
				 System.out.print("\nEl archivo no existe");
			 }
   			break;
   		case 2 :
   		 if (crearArchivo()) {
			 System.out.print("\n El archivo ha sido creado satisfactoriamente");
		}
   		 break;
   			   
   		case 3:
   			asignar();
   			break;
   		case 4 :
   			  agregarReg();
   			   break;
   		
   		
   		default:
   			break;
   			   
   			}
		}while(op1!=9);
	}
	public boolean crearArchivo() { 
		try {
			final String ruta = "c:/archivo/DATOS.txt"; 
			final String ruta2 = "c:/archivo/INDEX.txt"; 
			final String ruta3= "c:/archivo/asignar.txt";
			final String ruta4= "c:/archivo/entidad.txt";
			File archivo= new File(ruta);
			File archivo2= new File(ruta3);
			File archivo3= new File(ruta2);
			File archivo4 = new File(ruta4);
			archivo2.createNewFile();
			archivo3.createNewFile();
			archivo4.createNewFile();
			return archivo.createNewFile();
			
		}catch(IOException e ){
			System.out.print("ocurrio un error al crear el archivo\n"+e.getMessage());
			return false;
		}
	}
	public boolean verificarArchivo() {
		final String ruta = "c:/archivo/DATOS.txt"; 
		File archivo= new File(ruta);
		return archivo.exists();
		}

}
