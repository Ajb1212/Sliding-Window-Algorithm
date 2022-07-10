# Sliding-Window-Algorithm

[Link to the problem in leetcode for future assessment](https://leetcode.com/problems/k-radius-subarray-averages/)

The solution:

    public class Solution
      {
          public int[] GetAverages(int[] nums, int k)
          {
              int[] result = Enumerable.Repeat(-1, nums.Length).ToArray();
  
              int twoK = k * 2;
              int windowSize = twoK + 1;
              int sum = 0;
              for (int i = 0; i < nums.Length; i++)
              {
                  sum += nums[i];
                  if (i >= twoK)
                  {
                      result[i - k] = sum / windowSize;
                      sum -= nums[i - twoK]; 
                  }
              }
  
              return result;
          }
    }
