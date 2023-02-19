# 프로그래머스 - 정수 내림차순으로 배치하기.
***



![image](https://user-images.githubusercontent.com/108318494/219372954-da4b70d4-4b16-49ea-a56b-4689666c5b28.png)

처음 문제를 보고 쉽게 풀릴 것 이라고 생각했다. <br>
입력받은 정수 n을 내림차순 정렬해 리턴하면 끝 이라고 생각했지만 코드로 만드는 것은 쉬운 일이 아니었고 어떻게 풀어야할지 생각을 먼저 하고 풀어봤다.<br>
<br>
```
import java.util.*;
class Solution {
    public long solution(long n) {
        long answer = 0;

        String nString = Long.toString(n);  // n > 문자열로 변환
        String[] arr = new String[nString.length()];  // 문자열 인덱스값 넣어줄 배열 생성
        String result = "";

        // System.out.println(nString);
        for (int i=0; i<nString.length(); i++) {
            // System.out.println(nString.substring(i, i+1));
            arr[i] = nString.substring(i, i+1);
        }  // 문자열을 나눠 인덱스 값을 배열에 저장. 

        Arrays.sort(arr, Collections.reverseOrder());  // arr배열 내림차순 정렬.
        // System.out.println(String.join("", arr));
        result = String.join("", arr);  // 내림차순 정렬된 배열 > 문자열 변환

        return Long.parseLong(result);
    }
}
```


위의 코드를 설명하자면
1. 입력받은 정수 n을 배열로 만들어 정렬시키기 위해 먼저 문자열로 변환시켰다.
2. 변환시킨 문자열의 각 인덱스 값들을 담아줄 배열 생성.
3. 인덱스값 배열에 저장.
4. 저장한 배열 arr 내림차순 정렬.
5. 정렬된 배열 > 문자열 변환.

처음에 내림차순 정렬(sort)을 알지 못했었다.
그래서 for문을 이용해 max값을 구하는 코드를 만들어 새로운 배열에 순서대로 저장하기도 했었고 최종적으로 구글링을 통해 간결한 방법을 찾을 수 있었다. 앞으로 Collection에대해 조금 더 공부가 필요할 것 같다.
