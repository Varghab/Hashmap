## 1. Longest Subarray Zero Sum

```py
#include <bits/stdc++.h> 
#include <bits/stdc++.h> 
int LongestSubsetWithZeroSum(vector < int > arr) {
    int maxAns=0;
    map<int,int>mp;
    mp[0] = -1;
    int sum = 0;
    for(int i=0;i<arr.size();i++){
      sum+=arr[i];
      if(mp.find(sum-0)!=mp.end()){
        int subArray = i-mp[sum-0];
        maxAns = max(maxAns, subArray);
      }
      else mp[sum] = i;
    }
    return maxAns;
}
```
