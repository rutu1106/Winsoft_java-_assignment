import java.util.Arrays;

public class MergeArrays {
    public static void mergeArrays(int[] X, int[] Y) {
        int m = X.length;
        int n = Y.length;

        int k = 0;
        for (int i = 0; i < m; i++) {
            if (X[i] != 0) {
                X[k++] = X[i];
            }
        }

        // Merge Y[] into X[]
        int i = k;
        int j = 0;
        int l = 0;
        while (i < m && j < n) {
            if (X[i] < Y[j]) {
                X[l++] = X[i++];
            } else {
                X[l++] = Y[j++];
            }
        }

        while (j < n) {
            X[l++] = Y[j++];
        }
    }

    public static void main(String[] args) {
        int[] X = {0, 2, 0, 3, 0, 5, 6, 0, 0};
        int[] Y = {1, 8, 9, 10, 15};
        
        System.out.println("Before merge:");
        System.out.println("X[] = " + Arrays.toString(X));
        System.out.println("Y[] = " + Arrays.toString(Y));
        
        mergeArrays(X, Y);
        
        System.out.println("\nAfter merge:");
        System.out.println("X[] = " + Arrays.toString(X));
    }
}
