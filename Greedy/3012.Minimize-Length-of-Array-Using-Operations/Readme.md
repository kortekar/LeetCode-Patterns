### 3012.Minimize-Length-of-Array-Using-Operations

这是一道精彩的构造性问题。

我们注意到，对于任意x<y，那么通过x%y的操作，本质上可以将y剔除。所以我们必然会将nums排序。任何大于nums[0]的元素都可以删除，剩下的就是与nums[0]的元素。那么接下来是否还有操作的可能呢？

事实上，如果nums里有k个最小值，依照以上的方法，最多只能缩减到k/2个元素。我们希望有一个“全局唯一的最小值”，这样就可以将其他所有元素都剔除。怎么构造出来呢？只要看是否有除以`min_value`余数不为零的元素即可。如果有，那么我们就能构造出这个“全局唯一最小值”，而把总数缩减到1个。

于是，剩下的情况就是，有若干个相同的最小值（记做k个），其他元素也都是min_value的倍数。这种情况下，我们只能采用第一种策略，去除所有非最小值元素后，最后剩下(k+1)/2个元素。