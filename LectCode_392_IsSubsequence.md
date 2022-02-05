# LectCode_392_Is Subsequence
### 두 개의 문자열 s와 t가 주어지면 s가 t의 하위 시퀀스이면 true를 반환하고 그렇지 않으면 false를 반환합니다.

### 문자열의 하위 시퀀스는 나머지 문자의 상대적 위치를 방해하지 않고 문자 중 일부(없을 수 있음)를 삭제하여 원래 문자열에서 형성된 새로운 문자열입니다. (즉, "ace"는 "abcde"의 하위 시퀀스이고 "aec"는 그렇지 않음).

``` 
@ex_1
Input: s = "abc", t = "ahbgdc"
Output: true
```
```
@ex_2
Input: s = "axc", t = "ahbgdc"
Output: false
```
# 풀이
```
class Solution {
    public boolean isSubsequence(String s, String t) {
    int sIndex = 0;
    int tIndex = 0;
    boolean answer = false;
    while (tIndex >= 0) { // 해당 문자열이 없으면 순회 끝 false
        tIndex = t.indexOf(s.charAt(sIndex)); // substring의 값이 t에 있는지 확인
        if (tIndex >= 0) { // 있으면 
            t = t.substring(tIndex); // 해당 인덱스 전에 있는 문자열 버림
            sIndex++; // 다음 substring의 문자열을 향해
        } else {
            answer = false;
        }
        if (s.length() == sIndex) { // 마지막까지 확인했는데 다 있으면 true
            answer = true;
            break;
        }
    }
    return answer;
}
}
```
```
func isSubsequence(s string, t string) bool {

    si := 0

    ti := 0

    for si < len(s) && ti < len(t) {

        if s[si] == t[ti] {

            si++

            ti++

        }else {

            ti++

        }

    }

 return si == len(s)

}
```