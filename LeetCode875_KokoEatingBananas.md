# LeetCode_875_Koko Eating Banas
### n개의 바나나 무더기를 의미하는 배열(piles[] int),
### 경비가 돌아오는 시간(h int)가 인풋으로 주어졌을때
### 코코가 바나나를 먹는 최적의 속도 (k int)를 구해서 리턴하는문제
* 코코는 바나나를 천천히 먹는걸 좋아한다
* 코코는 경비가 오기 전에 바나나를 모두 먹어야한다.
* 한번에 한 무더기(piles[idx])씩만 먹는다
* 한 무더기에 남은 양이 시간당 먹기로 한 양보다 많으면 그 무더기에 있는것만 먹는다
* <font color = pink>다음 무더기에서 바나나를 추가로 먹지 않는다</font>
#
```java
@input
int[] plies = [1,3,5,7,9];
int h =12;
```
코코는 12시간 안에 5개의 바구니 안에 있는 바나나를 먹어야한다.
<br>
시간당 최소 1개 이상을 먹어야하고, 최대한 빨리 먹으려면 바구니 안의 최대값을 먹으면 된다
<br>
```
int min = 1;
int max = Array.stream(plies).max().getAsInt();
int total = 1 <= ?? <= max
```
중간값부터 확인을 하자면 아래와같다
```
int total = (min+max)/2
```
(1+9)/2 = 5 이므로 해당값으로 소요되는 시간을 계산해보자면
<br>
(1+5)/5 = <font color = yellow> 1 </font>
<br>
(3+5)/5 = <font color = yellow> 1 </font>
<br>
(5+5)/5 = <font color = yellow> 1 </font>
<br>
(7+5)/5 =<font color = yellow> 2 </font>
<br>
(9+5)/5= <font color = yellow> 2 </font>
<br>
시간을 다 더해보면
<br>
1+1+1+2+2=7
<br>
<font color = skyblue>
1시간에 5개씩 먹었을 때 해당 조건에 충족하기 때문에 min의 값을 5로 잡아도 가능하다는 뜻이다.
<br>
그렇게 min의값과 max값이 같아지는 코딩을 짜면 된다
<br>
이걸 반복하는 코딩을 작성하게되면
</font>
```java
class Solution{
    public int minEatingSpeed(int[] plies, int h){
        //최소값
        int min= 1;
        //최대값
        int max = Array.stream(plies).max().getAsInt();

        //min값과 max값이 같아지면 while중지
        while(min < max ){
            //중간값
            int mid = (min+max)/2;
            //최종시간 구하기 배열의 갯수만큼 반복
            for(int i : plies){
                int total += (i +mid)/mid;
                if(total >h){
                    min = mid+1;
                }else{
                    max = mid;
                }
            }
        }
    }
}
```