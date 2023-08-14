## 1. Longest Subarray Zero Sum

```cpp
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

## 2. Subarray Sums Divisible by K

```cpp
class Solution {
public:
    int subarraysDivByK(vector<int>& nums, int k) {
        int count = 0;
        int sum = 0;
        map<int,int>mp;
        mp[0]++;
        for(int x:nums){
            sum+=x;
            if(mp[(sum%k+k)%k]>0) count+=mp[(sum%k+k)%k];
            mp[(sum%k+k)%k]++;
        }
        return count;

    }
};
```
## 3. Group Anagrams

```cpp
class Solution {
public:
    vector<vector<string>> groupAnagrams(vector<string>& strs) {
        vector<vector<string>>res;
        map<string, vector<string>>mp;
        for(auto x: strs){
            string temp = x;
            sort(temp.begin(),temp.end());
            mp[temp].push_back(x);
        }
        for(auto it:mp){
            res.push_back(it.second);
        }
        return res;
        }
};
```
