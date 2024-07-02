# calculadora.parcial FINAL
import java.util.Scanner;

public class Main {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        double num1, num2, resultado;
        int opcion;

        System.out.println("Calculadora Básica");

        while (true) { // Bucle infinito para repetir el proceso hasta que el usuario decida salir
            System.out.print("Ingrese el primer número (o 's' para salir): ");
            if (scanner.hasNextDouble()) {
                num1 = scanner.nextDouble();
            } else if (scanner.next().equalsIgnoreCase("s")) {
                break; // Salir del bucle si el usuario ingresa 's'
            } else {
                System.out.println("Entrada inválida. Intente de nuevo.");
                continue; // Volver al inicio del bucle si la entrada no es válida
            }

            System.out.print("Ingrese el segundo número: ");
            if (scanner.hasNextDouble()) {
                num2 = scanner.nextDouble();
            } else {
                System.out.println("Entrada inválida. Intente de nuevo.");
                continue; // Volver al inicio del bucle si la entrada no es válida
            }

            System.out.println("\nSeleccione la operación:");
            System.out.println("1. Suma");
            System.out.println("2. Resta");
            System.out.println("3. Multiplicación");
            System.out.println("4. División");
            System.out.print("Opción: ");
            opcion = scanner.nextInt();

            switch (opcion) {
                case 1:
                    resultado = num1 + num2;
                    break;
                case 2:
                    resultado = num1 - num2;
                    break;
                case 3:
                    resultado = num1 * num2;
                    break;
                case 4:
                    if (num2 == 0) {
                        System.out.println("Error: División por cero");
                        continue; // Volver al inicio del bucle si se intenta dividir por cero
                    }
                    resultado = num1 / num2;
                    break;
                default:
                    System.out.println("Opción inválida");
                    continue; // Volver al inicio del bucle si la opción no es válida
            }

            System.out.println("Resultado: " + resultado);
        }

        System.out.println("¡Hasta luego!");
    }
}

