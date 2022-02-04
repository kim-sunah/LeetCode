# LeetCode_18_4Sum
### n개의 정수 배열이 주어지면 고유한 사중항[nums[a],nums[b],nums[c],nums[d]]의 배열을 반환합니다.
<br>
ex) 0 <= a,b,c,d < n
<br>
<br>
a,b,c,d는 별개입니다. 
<br>
 nums[a] + nums[b] + nums[c] + nums[d] == target
<br>
 어떤 순서로든 답은 반환할 수 있습니다.

 ```
 @ex_1

Input: nums = [1,0,-1,0,-2,2], target = 0
Output: [[-2,-1,1,2],[-2,0,0,2],[-1,0,0,1]]
```
```
@ex_2
Input: nums = [2,2,2,2,2], target = 8
Output: [[2,2,2,2]]
```

