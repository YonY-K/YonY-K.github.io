---
title: "이차원 리스트(배열)"
tag: basics_training
---

### 정수를 나선형으로 배치하기
![정수를 나선형으로 배치하기](https://github.com/yony-k/yony-k.github.io/assets/109204976/a8ee8952-f9a9-416e-8ed8-9a4b150fa3a3)

```java
class Solution {
    public int[][] solution(int n) {
         int[][] answer = new int[n][n];

        int num = 1; // 배열에 채워질 정수 값
        int rowStart = 0; // 행의 시작 인덱스
        int rowEnd = n - 1; // 행의 끝 인덱스
        int colStart = 0; // 열의 시작 인덱스
        int colEnd = n - 1; // 열의 끝 인덱스

        while (num <= n * n) {
            // 왼쪽 -> 오른쪽
            for (int i = colStart; i <= colEnd; i++) {
                answer[rowStart][i] = num++;
            }
            rowStart++; // 행의 시작 인덱스 증가

            // 위쪽 -> 아래쪽
            for (int i = rowStart; i <= rowEnd; i++) {
                answer[i][colEnd] = num++;
            }
            colEnd--; // 열의 끝 인덱스 감소

            // 오른쪽 -> 왼쪽
            for (int i = colEnd; i >= colStart; i--) {
                answer[rowEnd][i] = num++;
            }
            rowEnd--; // 행의 끝 인덱스 감소

            // 아래쪽 -> 위쪽
            for (int i = rowEnd; i >= rowStart; i--) {
                answer[i][colStart] = num++;
            }
            colStart++; // 열의 시작 인덱스 증가
        }

        return answer;
    }
}
```

- 내가 짠 코드가 아님 
- 나중에 천천히 이해하자

---

### 특별한 이차원 배열 2
![특별한 이차원 배열 2](https://github.com/yony-k/yony-k.github.io/assets/109204976/79c775f0-5793-4f3e-9cdf-4fc5a713bf9b)

```java
class Solution {
    public int solution(int[][] arr) {
        int answer = 0;
        
        boolean ok = true;
		for(int i=0;i<arr.length;i++) {
			for(int j=0;j<arr[i].length;j++) {
				if(arr[i][j]==arr[j][i]) continue;
				else ok = false;
			}
		}
		
		answer = ok ? 1 : 0;
        
        return answer;
    }
}
```

---

### 정사각형으로 만들기
![정사각형으로 만들기](https://github.com/yony-k/yony-k.github.io/assets/109204976/f0d1d08e-5636-49db-90d6-c0098f9b34b6)

```java
class Solution {
    public int[][] solution(int[][] arr) {
        int[][] answer = null;
        
        int a1 = arr.length;
		int a2 = arr[0].length;
		
		if(a1>a2) {
			answer = new int[a1][a1];
			for(int i=0;i<a1;i++) {
				for(int j=0;j<a2;j++) {
					answer[i][j] = arr[i][j];
				}
			}
		} else if(a1<a2) {
			answer = new int[a2][a2];
			for(int i=0;i<a1;i++) {
				for(int j=0;j<a2;j++) {
					answer[i][j]=arr[i][j];
				}
			}
		} else {
			return arr;
		}
        
        return answer;
        
    }
}
```

---

### 이차원 배열 대각선 순회하기
![이차원 배열 대각선 순회하기](https://github.com/yony-k/yony-k.github.io/assets/109204976/5c6cf0e8-8d40-4313-a9f3-13b2c87c6d34)

```java
class Solution {
    public int solution(int[][] board, int k) {
        int answer = 0;
        
        for(int i=0;i<board.length;i++) {
			for(int j=0;j<board[0].length;j++) {
				if(i+j<=k) answer += board[i][j];
			}
		}
        
        return answer;
    }
}
```