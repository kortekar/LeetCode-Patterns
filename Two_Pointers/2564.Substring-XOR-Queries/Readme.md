### 2564.Substring-XOR-Queries

首先我们知道`x^a=b`可以推出`x=a^b`。于是本题本质就是给出了一系列的val，问在二进制串里最早出现val的子串。暴力枚举子串的时间复杂度是o(N^2)，本题能够优化的地方在于，val的长度是有上限的，最多31位（因为整型不超过2^32）。所以我们只要遍历长度分别为1,2,...,31的子串，跑31次双指针即可：查看固定长度的滑窗里的数值是否出现在query里即可。时间复杂度就是o(31N).
