import java.util.Arrays;
import java.util.Scanner;

public class IterativePermutations {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter a string to permute: ");
        String input = scanner.nextLine();

        if (input == null || input.isEmpty()) {
            System.out.println("Error: Input string must not be empty.");
            return;
        }

        // Convert to char array and sort for lexicographic start
        char[] chars = input.toCharArray();
        Arrays.sort(chars);

        System.out.println("All permutations:");
        do {
            System.out.println(new String(chars));
        } while (nextPermutation(chars));
    }

    /**
     * Generates the next lexicographic permutation of the char array in-place.
     * Returns false if it was the last permutation.
     */
    private static boolean nextPermutation(char[] array) {
        // Step 1: Find longest non-increasing suffix
        int i = array.length - 2;
        while (i >= 0 && array[i] >= array[i + 1]) {
            i--;
        }

        // If no such i, we're at the last permutation
        if (i < 0) {
            return false;
        }

        // Step 2: Find rightmost successor to pivot in suffix
        int j = array.length - 1;
        while (array[j] <= array[i]) {
            j--;
        }

        // Step 3: Swap pivot with successor
        swap(array, i, j);

        // Step 4: Reverse suffix
        reverse(array, i + 1, array.length - 1);

        return true;
    }

    // Swaps two elements in an array
    private static void swap(char[] array, int i, int j) {
        char temp = array[i];
        array[i] = array[j];
        array[j] = temp;
    }

    // Reverses a subsection of an array
    private static void reverse(char[] array, int start, int end) {
        while (start < end) {
            swap(array, start++, end--);
        }
    }
}
