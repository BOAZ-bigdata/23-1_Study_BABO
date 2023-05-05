### 2. N과 M (2)
#### 수열인데 오름차순으로 이뤄진 수열

### 문제풀이 핵심아이디어 또는 새롭게 알게된 내용: 
    처음에 result 길이가 m인 경우 정렬해서 이전에 같은 경우 있는지 체크한 후 출력하는 아이디어로 짜보는데 런타임 에러가 뜨고....
    dfs함수에 입력변수를 start로 넣어주고 i+1로 재귀해주면 2부터 넣으면 2,1이 아니라 2,3으로 들어가니까 중복도 안되고 오름차순 경우만 넣게 됨
            
### 코드의 시간복잡도와 그 이유:    
    O(N^2)   
    > nCm 만큼 반복되므로 n(n-1)/m!
   
    
### 주석이 가득 담긴 코드:
```python

n,m = map(int,input().split())

result = []

def dfs(start):
  if len(result) == m:
    print(*result)
    return

  for i in range(start,n+1):
    if i not in result:
      result.append(i)
      dfs(i+1)
      result.pop(-1)

dfs(1)

## 조합으로 갖다 쓸 수 있다고 한다.. 코테에서 말한 조합이 이거였군아.....ㅋ
from itertools import combinations

n, m = map(int, input().split())
C = combinations(range(1, n+1), m)  # iter(tuple)

for i in C:
    print(' '.join(map(str, i)))  # tuple -> str
```
