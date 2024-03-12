package peliculaslhs;
import java.util.LinkedHashSet;
import java.util.Scanner;
import java.util.ArrayList;
import java.util.Collections;
import java.util.List;

public class Peliculaslhs {

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        LinkedHashSet<Peliculalhs> peliculas;
        peliculas = new LinkedHashSet<>();
        
        System.out.println("Ingrese el nombre de la pelicula seguido de su año de lanzamineto: ");
        System.out.println("(Escriba 'exit' para terminar)");
        
        while (true) {
            System.out.println("Nombre de la pelicula: ");
            String nombre = sc.nextLine();
            if (nombre.equals("exit")){
                break;
            }
            System.out.println("Ingrese el año de lanzamiento: ");
            int añoLanzamiento = sc.nextInt();
            sc.nextLine();
            
            Peliculalhs pelicula = new Peliculalhs(nombre, añoLanzamiento);
            peliculas.add(pelicula);
        }
        
        List<Peliculalhs> listaPeliculas = new ArrayList<>(peliculas);
        Collections.sort(listaPeliculas, (p1, p2) -> Integer.compare(p1.getAñoLanzamiento(), p2.getAñoLanzamiento()));
        
        System.out.println("Estas son las peliculas con sus respectivos años de lanzamiento ordenados de la más antigua a la más reciente: ");
        for (Peliculalhs pelicula : listaPeliculas){
            System.out.println(pelicula);        
        }
    }
    
}


package peliculaslhs;

class Peliculalhs {
    private final String nombre;
    private final int añoLanzamiento;
    
    public Peliculalhs(String nombre, int añoLanzamiento){
        this.nombre = nombre;
        this.añoLanzamiento = añoLanzamiento;
    }

    public String getNombre() {
        return nombre;
    }

    public int getAñoLanzamiento() {
        return añoLanzamiento;
    }
    
    @Override
    public String toString(){
        return nombre + "-" + añoLanzamiento;
    }
}
