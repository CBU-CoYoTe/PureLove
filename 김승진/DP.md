# 다이나믹 프로그래밍 (Dynamic Programming)
### 중복되는 연산을 줄이자
- DP 라고도 하며, 점화식을 코드로 옮기는 경우가 많다.
- 메모이제이션 기법을 활용해 해결하는 경우가 많다.

```
dp = [0] * 100

def fibo(x):
    if x == 1 or x == 2:
        return 1
    if dp[x] != 0:
        return dp[x]
    dp[x] = fibo(x - 1) + fibo(x - 2)
    return dp[x]

print(fibo(99))
```