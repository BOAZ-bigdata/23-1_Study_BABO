### 2. N과 M

### 문제풀이 핵심아이디어 또는 새롭게 알게된 내용: 
    처음에 반복문을 n,m 이중중첩문으로 짜다가 무한 반복으로 도저히 안돼서 재귀함수를 써야하는구나를 깨달음^.^
    dfs 배웠던 거를 좀 참고해서 dfs 함수 안에 반복문을 구현해서 result 길이가 m이 아닐 때까지 반복문 반복할 수 있게끔!
    m 길이 되기 전까지는 append와 pop을 반복해줘야 함

            
### 코드의 시간복잡도와 그 이유:    
    O(N^2)   
    > nCm 만큼 반복되므로 n(n-1)/m!
   
    
### 주석이 가득 담긴 코드:
```python

n,m = map(int,input().split())

result = []

def dfs():
  if len(result) == m:
    print(*result)
    return

  for i in range(1,n+1):
    if i not in result:
      result.append(i)
      dfs()
      result.pop(-1)

dfs()

```
