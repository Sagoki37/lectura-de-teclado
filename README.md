# lectura-de-teclado

import java.util.Scanner;

public class RegistroVisitas {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        // Datos generales del visitante (sin constantes)
        System.out.println("Ingrese su número de cédula (int):");
        int cedula = sc.nextInt();

        System.out.println("Ingrese su edad (byte):");
        byte edad = sc.nextByte();

        System.out.println("Ingrese su número de teléfono (long):");
        long telefono = sc.nextLong();

        System.out.println("Ingrese su género (char):");
        char genero = sc.next().charAt(0);

        System.out.println("¿Tiene cita previa? (true/false):");
        boolean tieneCita = sc.nextBoolean();

        System.out.println("Ingrese su temperatura corporal (float):");
        float temperatura = sc.nextFloat();

        System.out.println("Ingrese latitud de ubicación (double):");
        double latitud = sc.nextDouble();

        // Registro de visitas
        System.out.println("¿Cuántas visitas hará esta semana?");
        short totalVisitas = sc.nextShort(); // Tipo short para cantidad de visitas

        int acumuladorMinutos = 0;

        for (int i = 1; i <= totalVisitas; i++) {
            System.out.println("----- Visita #" + i + " -----");

            System.out.println("Ingrese el número del departamento (short):");
            short numeroDepartamento = sc.nextShort();

            System.out.println("Ingrese el piso al que se dirige (byte):");
            byte piso = sc.nextByte();

            System.out.println("Ingrese el tiempo de estadía en minutos (int):");
            int tiempoMinutos = sc.nextInt();

            acumuladorMinutos += tiempoMinutos;
        }

        // Cálculos
        float promedioEstadia = (float) acumuladorMinutos / totalVisitas;
        boolean esMayorEdad = edad >= 18;

        // Salida
        System.out.println("\n======= RESUMEN DE VISITAS =======");
        System.out.println("Cédula: " + cedula);
        System.out.println("Teléfono: " + telefono);
        System.out.println("Género: " + genero);
        System.out.println("Edad: " + edad + " (" + (esMayorEdad ? "Mayor de edad" : "Menor de edad") + ")");
        System.out.println("Temperatura corporal: " + temperatura + "°C");
        System.out.println("Cita previa: " + (tieneCita ? "Sí" : "No"));
        System.out.println("Latitud ubicación: " + latitud);
        System.out.println("Total de visitas esta semana: " + totalVisitas);
        System.out.println("Tiempo promedio de estadía: " + promedioEstadia + " minutos");
    }
}
