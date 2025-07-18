import java.util.Arrays;

class StockProfit {
    static int maxProfit(int[] prices) {
        int n = prices.length;

        // Create a 2D array 'ahead' and 'cur' to store profit values
        int[][] ahead = new int[2][3];
        int[][] cur = new int[2][3];

        // Loop through the prices array, starting from the second last stock (ind=n-1)
        for (int ind = n - 1; ind >= 0; ind--) {
            for (int buy = 0; buy <= 1; buy++) {
                for (int cap = 1; cap <= 2; cap++) {

                    if (buy == 0) { // We can buy the stock
                        cur[buy][cap] = Math.max(0 + ahead[0][cap],
                                -prices[ind] + ahead[1][cap]);
                    }

                    if (buy == 1) { // We can sell the stock
                        cur[buy][cap] = Math.max(0 + ahead[1][cap],
                                prices[ind] + ahead[0][cap - 1]);
                    }
                }
            }

            // Update 'ahead' with the values in 'cur'
            for (int i = 0; i < 2; i++) {
                for (int j = 1; j < 3; j++) {
                    ahead[i][j] = cur[i][j];
                }
            }
        }

        // The maximum profit with 2 transactions is stored in ahead[0][2]
        return ahead[0][2];
    }

    public static void main(String[] args) {
        int[] prices = {3, 3, 5, 0, 0, 3, 1, 4};
        int n = prices.length;

        // Calculate and print the maximum profit
        System.out.println("The maximum profit that can be generated is " + maxProfit(prices));
    }
}
