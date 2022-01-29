# Leet Code_58_Length Of Word
### 몇개의 공백으로 구분된 몇자의 단어로 구성된 문자열 s가 주어지면 문자열의 마지막 단어 길이를 반환합니다.
* 단어는 공백이 아는 문자로만 구성된 최대 부분 문자열입니다.
```
@ex_1
Input: s = "Hello World"
Output: 5
Explanation: The last word is "World" with length 5.
```
```
@ex_2
Input: s = "   fly me   to   the moon  "
Output: 4
Explanation: The last word is "moon" with length 4.
```
```
@ex_3
Input: s = "luffy is still joyboy"
Output: 6
Explanation: The last word is "joyboy" with length 6.
```
```
@Constraints
1 <= s.length <= 104
s consists of only English letters and spaces ' '.
There will be at least one word in s.
```