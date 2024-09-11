import java.util.Arrays;
import java.util.Scanner;

public class EstadisticasArreglo {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        
        System.out.print("Ingrese el tamaño del arreglo: ");
        int tamano = scanner.nextInt();
        
        int[] arreglo = generarArregloAleatorio(tamano);
        
        System.out.println("\nArreglo generado:");
        imprimirArreglo(arreglo);
        
        calcularYMostrarEstadisticas(arreglo);
    }
    
    private static int[] generarArregloAleatorio(int tamano) {
        int[] arreglo = new int[tamano];
        for (int i = 0; i < tamano; i++) {
            arreglo[i] = (int) (Math.random() * 101);
        }
        return arreglo;
    }
    
    private static void imprimirArreglo(int[] arreglo) {
        for (int num : arreglo) {
            System.out.print(num + " ");
        }
        System.out.println();
    }
    
    private static void calcularYMostrarEstadisticas(int[] arreglo) {
        double media = calcularMedia(arreglo);
        double mediana = calcularMediana(arreglo);
        double varianza = calcularVarianza(arreglo, media);
        double desviacionEstandar = calcularDesviacionEstandar(varianza);
        int moda = calcularModa(arreglo);
        
        System.out.println("\nResultados estadísticos:");
        System.out.printf("Media: %.2f%n", media);
        System.out.printf("Mediana: %.2f%n", mediana);
        System.out.printf("Varianza: %.2f%n", varianza);
        System.out.printf("Desviación estándar: %.2f%n", desviacionEstandar);
        System.out.printf("Moda: %d%n", moda);
    }
    
    private static double calcularMedia(int[] arreglo) {
        int suma = 0;
        for (int num : arreglo) {
            suma += num;
        }
        return (double) suma / arreglo.length;
    }
    
    private static double calcularMediana(int[] arreglo) {
        Arrays.sort(arreglo);
        int n = arreglo.length;
        if (n % 2 == 0) {
            return (arreglo[n / 2 - 1] + arreglo[n / 2]) / 2.0;
        } else {
            return arreglo[n / 2];
        }
    }
    
    private static double calcularVarianza(int[] arreglo, double media) {
        double sumaCuadratica = 0;
        for (int num : arreglo) {
            sumaCuadratica += Math.pow(num - media, 2);
        }
        return sumaCuadratica / arreglo.length;
    }
    
    private static double calcularDesviacionEstandar(double varianza) {
        return Math.sqrt(varianza);
    }
    
    private static int calcularModa(int[] arreglo) {
        int[] frecuencia = new int[101];
        for (int num : arreglo) {
            frecuencia[num]++;
        }
        int maxFrecuencia = 0;
        int moda = 0;
        for (int i = 0; i < frecuencia.length; i++) {
            if (frecuencia[i] > maxFrecuencia) {
                maxFrecuencia = frecuencia[i];
                moda = i;
            }
        }
        return moda;
    }
}
