# Programmers
프로그래머스

https://programmers.co.kr/learn/courses/30/lessons/43162?language=java#
<

    
    public class Solution {
    
    static boolean[][] visited;int solution(int n, int[][] computers) {
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


<h3>소수찾기</h3> 
https://programmers.co.kr/learn/courses/30/lessons/12921 <br>
참고 : https://marobiana.tistory.com/91
<
    
    class Solution {
     public int solution(int n) {
      int answer = 0;
      boolean flag;
      
      for(int i = 2; i <= n; i++){
          flag = true;
          for(int j = 2; j <= Math.sqrt(i) ; j++){
              if(i%j == 0){
                  flag = false;
                  break;
              }
          }
          if(flag == true) answer++;
      }
      return answer;
     }
    }
>


<h3>K번째수<h3>
https://programmers.co.kr/learn/courses/30/lessons/42748

다른 방법:
Arrays.copyOfRange(array, commands[i][0]-1, commands[i][1]);
<   
        
    import java.util.ArrayList;
    import java.util.Collections;
        
     class Solution {
        public int[] solution(int[] array, int[][] commands) {
         int[] answer = new int[commands.length];

        for(int a=0; a<commands.length; a++){
            ArrayList<Integer> arr = new ArrayList<Integer>();

            for(int i=commands[a][0]-1; i<commands[a][1]; i++){
                arr.add(array[i]);
            }

            Collections.sort(arr);
            answer[a] = arr.get(commands[a][2]-1);

        }
        return answer;
     }
    }
>
