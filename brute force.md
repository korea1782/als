---
### 2798 블랙잭

by. korea1782

```python3
def blackjack(num_list, max_num):
    ans = num_list[0]
    # i, j, k 번째 카드를 더하는 모든 경우를 찾는다
    for i in range(len(num_list)-2):
        for j in range(i+1, len(num_list)):
            for k in range(j+1, len(num_list)):
                hap = num_list[i]+num_list[j]+num_list[k]
                if hap == max_num:
                    return hap
                elif hap < max_num and hap > ans:
                    ans = hap
    return ans

import sys
N, M = map(int, sys.stdin.readline().split())
num_list = list(map(int, sys.stdin.readline().split()))
num_list.sort()
print(blackjack(num_list, M))

```

---
### 2231 분해합

by. korea1782

```python3
def brute_force(N):
    for num in range(1,N+1):
        div_num = list(map(int,str(num)))
        # 문제에 주어진 것처럼 단순히 분해합을 구한다.
        if num + sum(div_num) == N:
            return num
        if num == N:
            return 0
import sys
N = int(sys.stdin.readline())
print(brute_force(N))
```

---
### 7568 덩치

by. korea1782

```python3
N = int(input())
people = []
for _ in range(N):
    people.append(tuple(map(int, input().split())))
for std_w, std_h in people:
    rank = 1
    for w, h in people:
        # 다른 것들과 비교하며 작은 경우가 있을 때마다 +1
        if std_w < w and std_h < h:
            rank += 1
    print(rank, end=' ')
```

---
### 1018 체스판 다시 칠하기

by. korea1782

```python3
N, M = map(int, input().split())
board = []
for _ in range(N):
    board.append(list(input()))
answer = []
for i in range(N-7):
    for j in range(M-7):
        cnt = 0
        # 입력받은 체스판에서 가능한 8 by 8 체스판을 모두 구한다.
        test_board = [board[i+k][j:j+8] for k in range(8)]
        # 각각의 8 by 8 체스판의 시작을 W라 하고 WBWB... BWBW 배열로 나열된다.
        # 이와 다를 경우 cnt +1
        for p in range(8):
            for q in range(8):
                if p%2 == 0:
                    if q%2 == 0:
                        if test_board[p][q] == 'B':
                            cnt+=1
                    elif q%2 == 1:
                        if test_board[p][q] == 'W':
                            cnt+=1
                else:
                    if q%2 == 0:
                        if test_board[p][q] == 'W':
                            cnt+=1
                    elif q%2 == 1:
                        if test_board[p][q] == 'B':
                            cnt+=1
        answer.append(min(cnt, 64-cnt))
        # 위에서 BW로 시작하는 경우는 세지 않았는데 이는 WB로 시작한 경우에서 64-cnt 해주면 된다.
        # 그리고 둘 중 더 작은 값이 answer에 추가된다.
print(min(answer))
```

---
### 1436 영화감독 숌

by. korea1782

```python3
N = int(input())
num = 666
while N:
    if '666' in str(num):
        N -= 1
    num+=1
print(num-1)
```
