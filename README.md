# Pascal
pascal in java
import java.util.Scanner;

public class pascal {
    public pascal() {
    }

    public static int[][] pascal(int n) {
        int[][] ans = new int[n][];
        int col = 1;

        for(int i = 0; i < n; ++i) {
            ans[i] = new int[col];

            for(int j = 0; j < col; ++j) {
                if (j == 0) {
                    ans[i][j] = 1;
                } else if (j == col - 1) {
                    ans[i][j] = 1;
                } else {
                    ans[i][j] = ans[i - 1][j - 1] + ans[i - 1][j];
                }
            }

            ++col;
        }

        return ans;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int[][] ans = pascal(n);

        for(int i = 0; i < n; ++i) {
            for(int j = 0; j < ans[i].length; ++j) {
                System.out.print(ans[i][j] + " ");
            }

            System.out.println();
        }

    }
}
