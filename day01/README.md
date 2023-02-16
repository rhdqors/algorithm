# 프로그래머스 - 핸드폰 번호 가리기
***

오늘부터 Java 언어에 익숙해질겸 알고리즘 문제 풀이를 시작했다.
문제는 프로그래머스 사이트의 핸드폰 번호 가리기.
<br><br>


![캡처](https://user-images.githubusercontent.com/108318494/219030185-064f2f63-4c11-4ce3-b8cb-8e91315d072d.JPG)<br>
문자열 phone_number의 뒷 4자리를 제외하고 "*"로 표시하면 된다.<br>
내가 생각한 방법은 변하지 않는 뒷 4자리를 구하고 나머지를 *로 바꾸는 것이었고 문자열을 자르는 방법이 필요했다.
<br><br><br>




```
    String phone_number = "01033334444";
    String answer = "";
    String frontNum = phone_number.substring(0, phone_number.length()-4);
    String backNum = phone_number.substring(phone_number.length()-4);

    for (int i=1; i<=frontNum.length(); i++) {
        answer += "*";
        System.out.println(answer);
    }
    answer += backNum;
    System.out.println(answer);
    return answer;
```
인덱스 번호 시작값, 끝값을 입력해 원하는 위치의 문자를 추출할 수 있는 substring이 있었고<br>
변수 frontNum와 backNum로 구분해 문자열을 나눠주었다. 그리고 각각의 문자열을 더해 답을 완성했다.


substring을 사용하지 않았다면 for문을 사용해 뒷 4자리를 구하는 방법도 있을 수 있을 것이다. 



