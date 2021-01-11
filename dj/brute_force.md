### 2798 블랙잭

```java
import java.util.Scanner;

public class Main {

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int cardCnt = sc.nextInt();
        int maximum = sc.nextInt();

        int[] cards = new int[cardCnt];
        for (int i = 0; i < cardCnt; i++) {
            cards[i] = sc.nextInt();
        }

        System.out.println(sumCards(cards, cardCnt, maximum));
    }

    static int sumCards(int[] cards, int cardCnt, int maximum) {
        int result = 0;

        for (int i = 0; i < cardCnt - 2; i++) {
            for (int j = i + 1; j < cardCnt - 1; j++) {
                for (int k = j + 1; k < cardCnt; k++) {
                    int sum = cards[i] + cards[j] + cards[k];

                    if (sum == maximum) {
                        return sum;
                    }
                    if (result < sum && sum < maximum) {
                        result = sum;
                    }
                }
            }
        }

        return result;
    }
}
```
