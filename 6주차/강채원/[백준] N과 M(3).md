### 3. N과 M (3)

### 문제풀이 핵심아이디어 또는 새롭게 알게된 내용: 
    1번 문제랑 다르게 1,1 의 경우처럼 중복 가능하며 2,1 부터 다시 시작하니까 if i not in result 의 조건문만 지워줌

            
### 코드의 시간복잡도와 그 이유:    
    O(N^2)   
    > 중복하니까 N*N 만큼 돌게 됨
   
    
### 주석이 가득 담긴 코드:
```python

n,m = map(int,input().split())

result = []

def dfs():
  if len(result) == m:
    print(*result)
    return

  for i in range(1,n+1):
    result.append(i)
    dfs()
    result.pop(-1)

dfs()


```
