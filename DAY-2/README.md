# EX 5B Coin Change Problem

### DATE: 01/05/2025

## AIM:
To compute the fewest number of coins that we need to make up the amount given.

## Algorithm:

1. Define a class Solution containing the method coinChange(self, coins, amount).
2. If amount is 0, return 0 because no coins are needed.
3. If the smallest coin value is greater than the amount, return -1 as it's impossible to form the amount.
4. Initialize a list dp of size amount + 1 with all values as -1 to represent unreachable amounts.
5. Iterate through each coin in the coins list.
6. If the coin value is greater than amount, skip to the next coin.
7. Set dp[coin] = 1 because the amount equal to the coin can be formed using one coin.
8. For each value j from coin + 1 to amount, do the following:
9. If dp[j - coin] is -1, skip because that sub-amount cannot be formed.
10. If dp[j] is -1, update dp[j] = dp[j - coin] + 1.
11. If dp[j] is not -1, update it to the minimum of its current value and dp[j - coin] + 1.
12. After processing all coins, return dp[amount] as the result.

## Program:

```
# Create a python function to compute the fewest number of coins that we need to make up the amount given.
# Developed by: SUJITHRA B K N
# Register Number: 212222230153

class Solution(object):
    def coinChange(self, coins, amount):
        if amount == 0 :
            return 0
        if min(coins) > amount:
            return -1
        dp = [-1 for i in range(0, amount + 1)]
        for i in coins:
            if i > len(dp) - 1:
                continue
            dp[i] = 1
            for j in range(i + 1, amount + 1):
                if dp[j - i] == -1:
                    continue
                elif dp[j] == -1:
                    dp[j] = dp[j - i] + 1
                else:
                    dp[j] = min(dp[j], dp[j - i] + 1)
        return dp[amount]
      
ob1 = Solution()
n=int(input())
s=[]
amt=int(input())
for i in range(n):
    s.append(int(input()))
print(ob1.coinChange(s,amt))
```

## Output:

![image](https://github.com/user-attachments/assets/439bf402-11ac-4b9a-a490-29116975a891)

## Result:
Thus the program was executed successfully for finding the minimum number of coins required to make amount.
