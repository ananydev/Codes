import java.util.*;

public class MaxCoins {
    static int maxCoins(ArrayList<Integer> a) {
        int n = a.size();
        
        // Add 1 to the beginning and end of the array
        a.add(0, 1);
        a.add(1);
        
        // Create a 2D DP array
        int[][] dp = new int[n + 2][n + 2];

        // Iterate from the end to the beginning
        for (int i = n; i >= 1; i--) {
            for (int j = 1; j <= n; j++) {
                if (i > j) continue;
                int maxi = Integer.MIN_VALUE;
                
                // Iterate through possible indices to split the array
                for (int ind = i; ind <= j; ind++) {
                    int cost = a.get(i - 1) * a.get(ind) * a.get(j + 1) +
                               dp[i][ind - 1] + dp[ind + 1][j];
                    maxi = Math.max(maxi, cost);
                }
                dp[i][j] = maxi;
            }
        }
        return dp[1][n];
    }

    public static void main(String[] args) {
        ArrayList<Integer> a = new ArrayList<>(Arrays.asList(3, 1, 5, 8));
        int ans = maxCoins(a);
        System.out.println(ans);
    }
}
