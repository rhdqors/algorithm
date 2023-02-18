# 프로그래머스 - 모의고사
***

![image](https://user-images.githubusercontent.com/108318494/219835014-a5203e66-3818-4c62-a548-7226b5373ae2.png)
<br>

문제를 확인하고 어떤 방법으로 풀어야 하나 생각을 해봤다.<br>
가장 먼저 1번, 2번, 3번 수포자가 찍는 방식에 규칙이 존재했고 각각 5번 8번 10번씩 숫자가 반복 되는 것 이었다.
<br><br>

```
    int[] answer = new int[3]; // 수포자들이 각각 문제를 맞춘 개수가 들어갈 배열 (수포자가 3명이기에 길이는3)
    int[] arr = {}; // 정답이 들어갈 배열

    int[] case1 = {1,2,3,4,5};
    int[] case2 = {2,1,2,3,2,4,2,5};
    int[] case3 = {3,3,1,1,2,2,4,4,5,5};
```

그래서 각각의 배열을 만들어 문제를 찍는 규칙을 담아줬고 <br>
이 배열과 값을 넣어주는 answers 배열의 값이 일치하는 갯수를 찾는 순서가 필요했다.
<br><br>
```
for (int i=0; i<answers.length; i++) {
        if (case1[i%case1.length] == answers[i]) {answer[0]++;} // 인풋 배열의 순서와 수포자들의 찍는 순서가 몇개 일치하는지 확인 > 각각의 번호에 저장
        if (case2[i%case2.length] == answers[i]) {answer[1]++;} 
        if (case3[i%case3.length] == answers[i]) {answer[2]++;}
    }

    int max = Math.max(answer[0], Math.max(answer[1], answer[2]));
```
문제에서 요구하는 조건이 가장 많은 문제를 맞춘 사람의 번호를 return 하는 것이었기에<br>
max 변수를 만들고 수포자 배열의 각 위치에 값을 넣어줬다.<br>
그리고 각 인덱스 값을 비교해 정답 배열로 옮겨주면 끝.
<br><br>

```
if (max == answer[0] && max == answer[1] && max == answer[2]) {
            arr = new int[]{1, 2, 3};
            return arr;
        } else if (max == answer[0] && max == answer[1]) {
            arr = new int[]{1, 2};
            return arr;
        } else if (max == answer[1] && max == answer[2]) {
            arr = new int[]{2, 3};
            return arr;
        } else if (max == answer[0]) {
            arr = new int[]{1};
            return arr;
        } else if (max == answer[1]) {
            arr = new int[]{2};
            return arr;
        }
        arr = new int[]{3};
        return arr;
```
![image](https://user-images.githubusercontent.com/108318494/219835780-21bbd2a1-cccd-4821-9fa5-242f66c86e39.png)
![image](https://user-images.githubusercontent.com/108318494/219835814-b3c68fc2-27b8-4708-b78f-318b854a5618.png)

코드 실행을 눌러보고 통과하는 줄 알았다.<br>
하지만 채점하는 과정에 실패가 있었고 아직까지 문제 되는 부분을 찾아보고 있으며 해결해가는 중이다.<br>
지금 만들어둔 코드도 현재로썬 잘 만들었다고 생각하지만 일단 통과하지 못했으며 조금 더 효율적인 코드를 찾아봐야 할 것 같다. 