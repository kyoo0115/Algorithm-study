# BFS를 활용한 그리드 탐색 문제 (그림)

---

이 문제는 2차원 그리드에서 BFS(너비 우선 탐색) 알고리즘을 사용하여 특정 조건을 만족하는 영역의 개수와 가장 큰 영역의 크기를 찾는 문제입니다.
- 문제 출처: https://www.acmicpc.net/problem/1926

## 문제 설명
- 주어진 2차원 그리드에서 1로 표시된 영역을 찾아야 합니다.
- 각 영역은 상하좌우로 인접한 1들로 구성됩니다.
- 문제의 목표는 다음과 같습니다:
  1. 전체 그리드에서 영역의 개수를 찾습니다.
  2. 가장 큰 영역의 크기를 계산합니다.

## 입력 형식
- 첫 번째 줄에는 그리드의 행(`n`)과 열(`m`)의 크기가 주어집니다.
- 다음 `n`개의 줄에 걸쳐서 각 행의 그리드 상태가 주어집니다. 여기서 1은 영역을 나타내고 0은 빈 공간을 나타냅니다.

## 출력 형식
- 첫 번째 줄에는 전체 그리드에서 찾은 영역의 개수를 출력합니다.
- 두 번째 줄에는 가장 큰 영역의 크기를 출력합니다.

## 예제
### 입력 예제

```
6 5
1 1 0 1 1
0 1 1 0 0
0 0 0 0 0
1 0 1 1 1
0 0 1 1 1
0 0 1 1 1
```
### 출력 예제
```
4
9
```
## 해결 방법
이 문제는 BFS를 사용하여 각 영역을 탐색하고, 영역의 크기를 계산하는 방식으로 해결할 수 있습니다. 
BFS를 사용하여 각 1이 나타내는 영역을 탐색하고, 연결된 모든 1들을 방문 처리하여 영역의 크기를 계산합니다. 
모든 그리드를 탐색하여 영역의 개수와 가장 큰 영역의 크기를 찾습니다.

## 구현 코드

```java
import java.io.BufferedReader;
import java.io.InputStreamReader;
import java.io.IOException;
import java.util.*;

public class Main {
    static int[][] grid;
    static boolean[][] visited;
    static int n, m;
    static int[] dx = {-1, 0, 1, 0};
    static int[] dy = {0, 1, 0, -1};

    public static void main(String[] args) throws IOException {
        BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
        StringTokenizer st = new StringTokenizer(br.readLine());

        n = Integer.parseInt(st.nextToken());
        m = Integer.parseInt(st.nextToken());
        grid = new int[n][m];
        visited = new boolean[n][m];

        for (int i = 0; i < n; i++) {
            st = new StringTokenizer(br.readLine());
            for (int j = 0; j < m; j++) {
                grid[i][j] = Integer.parseInt(st.nextToken());
            }
        }

        int maxArea = 0;
        int count = 0;

        for (int i = 0; i < n; i++) {
            for (int j = 0; j < m; j++) {
                if (grid[i][j] == 1 && !visited[i][j]) {
                    maxArea = Math.max(maxArea, bfs(i, j));
                    count++;
                }
            }
        }

        System.out.println(count);
        System.out.println(maxArea);
    }

    static int bfs(int x, int y) {
        Queue<int[]> queue = new LinkedList<>();
        queue.offer(new int[]{x, y});
        visited[x][y] = true;
        int area = 0;

        while (!queue.isEmpty()) {
            int[] current = queue.poll();
            area++;

            for (int i = 0; i < 4; i++) {
                int nx = current[0] + dx[i];
                int ny = current[1] + dy[i];

                if (nx >= 0 && ny >= 0 && nx < n && ny < m) {
                    if (grid[nx][ny] == 1 && !visited[nx][ny]) {
                        queue.offer(new int[]{nx, ny});
                        visited[nx][ny] = true;
                    }
                }
            }
        }

        return area;
    }
}
```
