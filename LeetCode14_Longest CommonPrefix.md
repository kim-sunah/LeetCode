# LeetCode_14_Longest Common Prefix
### input으로 string배열이 주어집니다.
### 주어진 배열의 string 에서 공통으로 가진 prefix(접두사)중 가장 긴 녀석을 찾아 리턴하는 문제입니다.
* 만약 공통된 접두사가 없으면 "" 빈문자열을 리턴하시오

```java
public String longestCommonPrefix(String[] strs){
    
    String prefix = strs[0];

    for(int i = 1; i <= strs.length; i++){
        String cut = strs[i];
        while(cut.indexOf(prefix) != 0){
            prefix = prefix.substring(0, prefix.length()-1);
        }
    }
    return prefix;
}
```

## 해석
※indexOf()
<br>
주어진 요소가 배열에 있다면 그 첫번째 인덱스값을 반환하고 없으면 -1을 반환
<br>
```
@test
String[] strs = {"hellow","hello","hi"}
```
prefix = "hello"
<br>
for cut = 
"hello"
"hi"
<Br>
"hello".indexOf("Hello")
```
for(i=1시작){
    hello에 hellow가 속해있지 않다 -> 마지막 1문자를 제외한 hello ->while문
    hello에 hello가 0번째로 속해있다 -> while문 종료
}
for(i=2 시작){
    hi에 hello가 속해있지 않다 -> 마지막 1문제를 제거한 hell ->while문
    hi에 hell가 속해있지 않다 -> 마지막 1문제를 제거한 hel ->while문
    .
    .
    .
    hi에 he가 속해있지 않다 -> 마지막 1문제를 제거한 h ->while문
    hi에 h가 속해있지 있다 -> while문 종료
}
