
package mysql.www;
import java.util.Scanner;
public class tastMain {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int n=scanner.nextInt();
        int [] arr = new int[n];
        for (int i = 0; i < n; i++) {
            arr[i]=scanner.nextInt();
        }
        int min =arr[0];
        for (int i : arr) {
            min = Math.min(min, i);
        }
        for (int i : arr) {
            int tastmin=Math.abs(min);
            Runnable run = () -> {
                try {
                    Thread.sleep(i+ tastmin);
                } catch (InterruptedException e) {
                    e.printStackTrace();
                }
                System.out.println(i);
            };
            new Thread(run).start();
        }
    }
}
