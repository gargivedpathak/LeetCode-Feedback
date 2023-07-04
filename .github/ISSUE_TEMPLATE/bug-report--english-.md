---
name: Bug report (English)
about: Create a bug report to help us improve our content.
title: ''
labels: ''
assignees: ''

---

<!--
Note - Any content mentioned below in `<!-- ->` blocks are just comments
to help you fill-up the issue. It won't be visible in the actual issue after
you click on submit.
-->

#### Your LeetCode username
<!-- Your LeetCode username -->
gargii09


#### Category of the bug
- [ ] Question
- [-] Solution
- [ ] Language
- [ ] Missing Test Cases 


#### Description of the bug
<!-- A clear and concise description of what the bug is. -->
373. Find K Pairs with Smallest Sums
The above question doesn't submit even after writing the correct solution. It fails test cases, or shows Time Limit Exceeded error for all the correct solutions that I have submitted till now.


#### Code you used for Submit/Run operation
<!-- 
Please make sure you wrap your code with ``` tags. 
Otherwise we may reject your request. 
-->

```
// Find K Pairs with Smallest Sums
class Solution {
public:
    vector<vector<int>> kSmallestPairs(vector<int>& nums1, vector<int>& nums2, int k)
    {
        vector<vector<int>> ans;
        priority_queue<pair<int, pair<int, int>>> pq;

        for (int i = 0; i < nums1.size(); i++) {
            for (int j = 0; j < nums2.size(); j++) {
                int sum = nums1[i] + nums2[j];
    
                if (pq.size() < k)
                    pq.push({sum, {nums1[i], nums2[j]}});
                else if (sum < pq.top().first) {
                    pq.pop();
                    pq.push({sum, {nums1[i], nums2[j]}});
                } else if (sum > pq.top().first) {
                    break;
                }
            }
        }

        while (!pq.empty()) {
            ans.push_back({pq.top().second.first, pq.top().second.second});
            pq.pop();
        }
    
        return ans;
    }
};

```

#### Language used for code
<!-- C++ -->
C++


#### Expected behavior
<!-- A clear and concise description of what you expected to happen in
contrast with what actually happened. -->
I expected the code to pass all test cases because I'm 100% sure it is the correct solution. However, it is giving me time limit exceeded for some of the other correct answers of others that I tried out and not passing any testcases for some solutions.
Moreover, I can also not see the expected answer.


#### Screenshots
<!-- If applicable, add screenshots to explain your issue. -->
<img width="457" alt="image" src="https://github.com/LeetCode-Feedback/LeetCode-Feedback/assets/81381638/f75a4fa0-99e6-49e7-9627-281dcceef5fb">
<img width="512" alt="image" src="https://github.com/LeetCode-Feedback/LeetCode-Feedback/assets/81381638/744e1400-e885-4de2-b6db-f2909e142bea">





#### Additional context
<!-- Add any other additional context about the bug. -->
