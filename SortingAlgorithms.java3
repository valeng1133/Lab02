import java.util.Arrays;
import java.util.Random;

public class SortingAlgorithms {

    public static void bubbleSort(double[] arr) {
        int n = arr.length;
        for (int i = 0; i < n - 1; i++) {
            for (int j = 0; j < n - i - 1; j++) {
                if (arr[j] > arr[j + 1]) {
                    double temp = arr[j];
                    arr[j] = arr[j + 1];
                    arr[j + 1] = temp;
                }
            }
        }
    }

    public static void insertionSort(double[] arr) {
        int n = arr.length;
        for (int i = 1; i < n; i++) {
            double key = arr[i];
            int j = i - 1;
            while (j >= 0 && arr[j] > key) {
                arr[j + 1] = arr[j];
                j--;
            }
            arr[j + 1] = key;
        }
    }

    public static void selectionSort(double[] arr) {
        int n = arr.length;
        for (int i = 0; i < n - 1; i++) {
            int minIndex = i;
            for (int j = i + 1; j < n; j++) {
                if (arr[j] < arr[minIndex]) {
                    minIndex = j;
                }
            }
            double temp = arr[i];
            arr[i] = arr[minIndex];
            arr[minIndex] = temp;
        }
    }

    public static void mergeSort(double[] arr) {
        if (arr.length <= 1) return;
        int mid = arr.length / 2;
        double[] left = Arrays.copyOfRange(arr, 0, mid);
        double[] right = Arrays.copyOfRange(arr, mid, arr.length);

        mergeSort(left);
        mergeSort(right);

        merge(left, right, arr);
    }

    private static void merge(double[] left, double[] right, double[] result) {
        int i = 0, j = 0, k = 0;
        while (i < left.length && j < right.length) {
            if (left[i] <= right[j]) {
                result[k++] = left[i++];
            } else {
                result[k++] = right[j++];
            }
        }
        while (i < left.length) result[k++] = left[i++];
        while (j < right.length) result[k++] = right[j++];
    }
}

class SortingPerformanceTest {

    public static void main(String[] args) {
        int sizes[] = {100, 500, 1000, 5000, 10000};
        SortingAlgorithms sa = new SortingAlgorithms();

        for (int size : sizes) {
            double[] originalArray = generateRandomArray(size);

            testAlgorithm(() -> sa.bubbleSort(originalArray), "Burbuja", size);
            testAlgorithm(() -> sa.insertionSort(originalArray), "Inserción", size);
            testAlgorithm(() -> sa.selectionSort(originalArray), "Selección", size);
            testAlgorithm(() -> sa.mergeSort(originalArray), "Mezcla", size);
        }
    }

    private static double[] generateRandomArray(int size) {
        double[] arr = new double[size];
        Random rand = new Random();
        for (int i = 0; i < size; i++) {
            arr[i] = rand.nextDouble() * 1000000;
        }
        return arr;
    }

    private static void testAlgorithm(Runnable sorter, String name, int size) {
        long startTime = System.nanoTime();
        sorter.run();
        long endTime = System.nanoTime();
        long duration = endTime - startTime;
        System.out.printf("%s (%d elementos): %.6f ms%n", name, size, duration / 1_000_000.0);
    }
}
