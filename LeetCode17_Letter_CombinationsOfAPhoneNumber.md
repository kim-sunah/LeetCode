# LeetCode_18_Letter Combinations of a Phone Number
### 2에서 9까지의 숫자를 포함하는 문자열이 주어지면 숫자가 나타낼 수 있는 모든 가능한 문자 조합을 반환합니다. <br>임의의 순서로 답을 반환하십시오.
### 전화 버튼과 마찬가지로 숫자 대 문자 매핑이 아래에 나와 있습니다. <br>1은 어떤 문자에도 매핑되지 않습니다.
 ```
 @ex_1

Input: digits = "23"
Output: ["ad","ae","af","bd","be","bf","cd","ce","cf"]
```
```
@ex_2
Input: digits = ""
Output: []
```
```
@ex_3
Input: digits = "2"
Output: ["a","b","c"]
```

```
func letterCombinations(digits string) []string {

    m := make(map[string] []string)

    m["2"] = []string{"a","b","c"}

    m["3"] = []string{"d","e","f"}

    m["4"] = []string{"g","h","i"}

    m["5"] = []string{"j","k","l"}

    m["6"] = []string{"m","n","o"}

    m["7"] = []string{"p","q","r","s"}

    m["8"] = []string{"t","u","v"}

    m["9"] = []string{"w","x","y","z"}

 

    return helper(digits, []string{}, m)

}



func helper(digits string, result []string, m map[string] []string) []string{

    if len(digits) == 0 {

        return result

    }

    if len(result) == 0 {

        return helper(digits[1:], m[string(digits[0])], m) 

    }

    

    number := string(digits[0])

    digits = digits[1:]

    letters := m[number]

    temp := []string{}

    for _, comb := range result {

        for _, letter := range letters {

            newComb := string(comb) + string(letter)

            temp = append(temp, newComb)

        }

    }

    return helper(digits, temp, m) 

 

}
```


