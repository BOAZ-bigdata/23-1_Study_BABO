### 4. N과 M (4)

### 문제풀이 핵심아이디어 또는 새롭게 알게된 내용: 
    2번 문제랑 다르게 오름차순이되 중복 허용이므로
    not in result 조건문 삭제, dfs(start)로 해주되 자기 자신은 고려해야하므로 길이 만족시 start +1해주고 dfs(i)로 재귀

            
### 코드의 시간복잡도와 그 이유:    
    O(N^2)   
    > 중복하니까 N*N 만큼 돌게 됨
   
    
### 주석이 가득 담긴 코드:
```python

n,m = map(int,input().split())

result = []

def dfs(start):
  if len(result) == m:
    print(*result)
    start += 1 #길이 만족 후에는 start를 1 늘려줌
    return

  for i in range(start,n+1):
    result.append(i)
    dfs(i) # i+1로 하면 2,2의 경우를 고려 못 함
    result.pop(-1)

dfs(1)


```
