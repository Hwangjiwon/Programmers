# Programmers
프로그래머스

https://programmers.co.kr/learn/courses/30/lessons/43162?language=java#
<
class Solution {
    static boolean[][] visited;
    
    public int solution(int n, int[][] computers) {
        int answer = 0;
        visited = new boolean[n][n];
        
        for(int i = 0; i < n; i++){
            if(!visited[i][i]){
                dfs(i, n, computers);
                answer++;
            }
        }
        
        return answer;
    }
    
    public static void dfs(int from, int n, int[][] computers){
        for(int to = 0; to < n; to++){
            if(computers[from][to] == 1 && !visited[from][to]){
                visited[from][to] = true;
                visited[to][from] = true;
                dfs(to, n, computers);
            }
        }
    }
}
>
