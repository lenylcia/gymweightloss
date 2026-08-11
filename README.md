public class GymWeightLoss {
    public static void main(String[] args) {
        // rows = gyms, cols = Month 1, Month 2, Month 3
        int[][] weightLoss = {
            {10, 20, 27}, // Gym 1
            {22,  5, 20}, // Gym 2
            {30, 20, 10}  // Gym 3
        };
        String[] months = {"Month 1", "Month 2", "Month 3"};
        String[] gyms = {"Gym 1", "Gym 2", "Gym 3"};

        // Print the monthly weight loss table first
        System.out.printf("%-10s%-10s%-10s%-10s%n", "Gym", months[0], months[1], months[2]);
        for (int g = 0; g < gyms.length; g++) {
            System.out.printf("%-10s%-10d%-10d%-10d%n", gyms[g], weightLoss[g][0], weightLoss[g][1], weightLoss[g][2]);
        }
        System.out.println();

        // Then the total and average per gym
        for (int g = 0; g < gyms.length; g++) {
            int total = 0;
            for (int m = 0; m < weightLoss[g].length; m++) {
                total += weightLoss[g][m];
            }
            double avg = total / (double) weightLoss[g].length;
            System.out.printf("%s -> Total: %dkg, Average: %.1fkg%n", gyms[g], total, avg);
        }
    }
}
