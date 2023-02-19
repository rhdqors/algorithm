# 프로그래머스 - 숫자 문자열과 영단어
***

![image](https://user-images.githubusercontent.com/108318494/219958302-58e54476-6bfa-4d2c-99c5-4f3cd85d962e.png)
<br><br><br>

문제를 확인 했을 때 주어진 문자열 "one4seveneight" 에서 원하는 문자만 추출해 바꿔주면 될 것 같았다.<br>
원하는 문자를 추출하고 바꾸기 위해 숫자와 영단어 각각의 배열을 만들어 주었다.



```
String[] num = {"0","1","2","3","4","5","6","7","8","9"};
String[] word = {"zero", "one", "two", "three", "four", "five", "six", "seven", "eight", "nine"};
```
<br><br>
이제 주어진 문자열에 위의 배열 값들이 있는지 확인이 필요했고
contains로 true/false를 판단해 replace로 문자열을 바꿔주었고 마지막으로 바꾼 문자열을 숫자로 형변환을 거쳐 답을 구할 수 있었다.
```
for (int i=0; i<10; i++) {
            if (s.contains(word[i])) {
                s = s.replace(word[i], num[i]);
            }
        }
answer = Integer.parseInt(s);
return answer;
```
<br>

***
<br>
사실 이번 문제에 큰 어려움은 없었다.
하지만 문자열에서 원하는 문자를 변경할 수 있는 replace와 포함 여부를 확인하는 contains 등
앞으로 활용도가 높을 것 같다는 생각이 들었고 이번 기회에 사용법을 제대로 알고갈 수 있었던 것 같다.