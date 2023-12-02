# Number-Please
import java.util.Scanner;

public class NumberPlease {
    public static void main(String[] args) {
       
        // The grid
        int[][] grid = {
                {2, 4, 5, 6, 1, 8, 9, 1, 4, 5},
                {3, 5, 7, 9, 10, 3, 2, 5, 6, 7},
                {6, 4, 4, 5, 10, 8, 5, 6, 7, 8},
                {4, 7, 7, 9, 3, 2, 7, 14, 9, 0},
                {5, 6, 8, 8, 8, 7, 7, 5, 5, 7},
                {6, 5, 4, 6, 4, 1, 3, 6, 8, 7},
                {8, 8, 3, 7, 8, 4, 4, 4, 6, 3},
                {10, 8, 16, 7, 3, 7, 8, 25, 9, 2},
                {4, 8, 3, 8, 2, 4, 6, 7, 10, 4},
                {4, 3, 6, 8, 1, 4, 3, 7, 3, 4}
        };

        Scanner s = new Scanner(System.in);

        // Get 4 sets of input
        for (int q = 0; q < 4; q++) {
            System.out.println("Enter coordinates (x1 y1 x2 y2) for query " + (q + 1) + ":");
            int x1 = s.nextInt();
            int y1 = s.nextInt();
            int x2 = s.nextInt();
            int y2 = s.nextInt();

            int sum = calculateSum(grid, x1, y1, x2, y2);
            System.out.println("Sum for query " + (q + 1) + ": " + sum);
        }
    }

    // Calculate the sum within the defined rectangle
    public static int calculateSum(int[][] grid, int x1, int y1, int x2, int y2) {
        int totalSum = 0;
        // Define the bounds of the rectangle
        int minX = Math.min(x1, x2) - 1;
        int maxX = Math.max(x1, x2);
        int minY = Math.min(y1, y2) - 1;
        int maxY = Math.max(y1, y2);

        // Calculate the sum within the rectangle
        for (int i = minY; i < maxY; i++) {
            for (int j = minX; j < maxX; j++) {
                totalSum += grid[i][j];
            }
        }
        return totalSum;
    }
}

