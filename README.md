# Ejercicio-1-POO
import java.util.HashMap;
import java.util.Scanner;

public class Main {
    public static void main (String[] args) {
        HashMap<String, Estudiante > estudiantes = new HashMap<>();
        Scanner scanner = new Scanner(System.in);
        int numero;

        do {
            System.out.println("\n _____________ MENÚ ____________");
            System.out.println("1. Ingresar estudiante");
            System.out.println("2. Ver estudiantes");
            System.out.println("3. Buscar estudiante por carnet");
            System.out.println("4. Salir");
            System.out.print("Seleccionar un número: ");
            numero = scanner.nextInt();
            scanner.nextLine();

            switch (numero) {
                case 1:
                    System.out.println("Ingresar carnet del estudiante");
                    String carnet = scanner.nextLine();

                    System.out.println("Ingresar nombre del estudiante");
                    String nombre = scanner.nextLine();

                    System.out.println("Ingresar edad del estudiante");
                    int edad = scanner.nextInt();
                    scanner.nextLine();

                    System.out.println("Ingresar carrera del estudiante");
                    String carrera = scanner.nextLine();

                    System.out.println("Ingresar Materia");
                    String materia = scanner.nextLine();

                    Estudiante estudiante = new Estudiante(nombre, edad, carrera, materia);
                    estudiantes.put(carnet, estudiante);
                    System.out.println(" El estudiante fue agregado con éxito");
                    break;

                case 2:
                 if (estudiantes.isEmpty()) {
                     System.out.println("No hay ningun estudiante registrado.");
                 } else {
                     for (String key : estudiantes.keySet()) {
                         System.out.println("Carnet: " + key + " = " + estudiantes.get(key));
                     }
                 }
                    break;

                case 3:
                    System.out.println("Ingrese el carnet del estudiante");
                    String BuscCarnet = scanner.nextLine();
                    Estudiante encontrado = estudiantes.get(BuscCarnet);
                    if (encontrado != null) {
                        System.out.println("El estudiante fue encontrado: " + encontrado);
                    } else {
                        System.out.println("Estudiante no encontrado.");
                    }
                    break;

                case 4:
                    System.out.println("Saliendo del programa...");
                    break;

                default:
                    System.out.println("Opción no válida. Intente con otro número.");
            }
        } while (numero != 4);
    }
}
