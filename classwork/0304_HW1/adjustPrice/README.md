# 阿龍的生意經

阿龍是一個成功的生意人，他有一個拉攏顧客的小撇步：「結帳時去小數也去尾數」，讓顧客都很喜歡和他買東西！請完成adjustPrice() function的多載設計。adjustPrice()函式接受一個數值做為參數，依據參數的型態，請完成以下的設計：

1. 該數值若為大於10的整數，則將該數值捨棄個位數，例如如92調整後為90，158調整後為150；若原本個位數就是0，則不做調整。
2. 該數值若為大於10的浮點數，則先無條件捨棄小數，再將個位數捨棄，例如43.14調整後為40，784.6調整後為780，10.05調整後為10。
3. 該數值若為小於等於10的浮點數，則無條件捨棄小數，例如3.14調整後為3，10.0調整後為10。


此題的執行結果可參考如下：

```
執行結果1
輸入	92
13.12
輸出	90
10

執行結果2
輸入	100
33.6
輸出	100
30

執行結果3
輸入	7
3.8
輸出	7
3

執行結果4
輸入	3
0
輸出	3
0
```

完整程式碼如下：
```
#include<iostream>
using namespace std;
int adjustPrice(int);
int adjustPrice(double);

int main()
{
	double x;
	cin >> x;
	cout<<adjustPrice(x);
}
int adjustPrice(int x)
{
	x = x - x % 10;
	return x;
}
int adjustPrice(double x)
{
	x = int(x) - (int(x) & 10);
	return x;
}
```
