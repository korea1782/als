### 2798 블랙잭

```java
import java.util.Scanner;

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
```

### 2231 분해합

```java
import java.util.Scanner;

class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int N = sc.nextInt();
        int size = String.valueOf(N).length();
        int start = N - (9 * size);

        Decomposition(start, N);
    }

    static void Decomposition(int start, int N) {
        for(int i = start; i < N; i += 1) {
            int answer = i;
            int j = i;
            while (j > 0) {
                answer += j % 10;
                j /= 10;
            }
            if (answer == N) {
                System.out.print(i);
                break;
            }
        }
    }
}
```

### 7568 덩치

```java
import java.util.Scanner;

class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int N = sc.nextInt();
        int arr[][] = new int[N][3];

        for(int i = 0; i < N; i += 1) {
            arr[i][0]= sc.nextInt();
            arr[i][1]= sc.nextInt();
        }

        int cnt;
        for(int i = 0; i < arr.length; i += 1) {
            cnt =0;
            for(int j = 0; j < arr.length; j+= 1) {
                if(arr[i][0]<arr[j][0] && arr[i][1]<arr[j][1]) {
                    cnt++;
                }
            }
            arr[i][2]=cnt+1;
        }

        for(int i = 0; i < arr.length; i += 1) {
            System.out.print(arr[i][2]+" ");
        }
    }
}
```
