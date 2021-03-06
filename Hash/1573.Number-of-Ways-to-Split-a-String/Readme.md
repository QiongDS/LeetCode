### 1573.Number-of-Ways-to-Split-a-String

基本思想是统计字符串内的“1”的个数count。首先我们必须要count%3==0才能实现满足题意的分割。

接下来我们知道，第一个cut必然位于第count/3个“1”和第count/3+1个“1”之间。第二个cut必然位于第count/3*2个“1”和第count/3*2+1个“1”之间。数一下分别有几个可供插入的位置，两者的成绩就是答案。如何快速定位第count/3个“1”在哪里呢？其实在之前统计的时候，就可以用一个hash表存储count到index的映射，这样可以快速定位。

此外，还有一个corner case，就是当字符串全为0的时候。这时候有n-1个空位，可以任意选择两个进行cut。所以答案要加上```(n-1)*(n-2)/2```.
