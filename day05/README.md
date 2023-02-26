# 프로그래머스 - 자연수 뒤집어 배열로 만들기
<br>

![image](https://user-images.githubusercontent.com/108318494/221417930-775fc828-9c58-4843-b652-7d51306cc145.png)


문제를 확인하고 각 자릿수를 뽑아낸 다음 반복문을 통해 반대로 넣어주면 된다고 생각했다. 
아래에서 코드를 만들어 실행해 보겠다.<br><br>


```agsl
public int[] solution(long n) {
        
        String nString = Long.toString(n);
        int[] answer = new int[nString.length()]; //숫자n - 문자 - 배열 변환
        int[] arr = new int[nString.length()]; // 역순 담을 배열

        for (int i=0; i<arr.length;i++) {
            answer[i] = Integer.parseInt(nString.substring(i,i+1));
        }

        for (int i=arr.length-1, j=0; i>=0; i--, j++) {
            arr[j] = answer[i];
        }
        return arr;
        
    }
```
숫자 -> 문자 -> 배열 두번의 변환 과정을 거치며 문제를 풀었다.<br>
하지만 과연 이러한 과정들이 필요했나 라는 생각이 있다. 두번의 과정을 거치지 않는 조금 더 쉬운 방법을 생각하며 앞으로의 문제도 풀어나가야 할 것 같다.

