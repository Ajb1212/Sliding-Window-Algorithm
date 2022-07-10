# Sliding-Window-Algorithm

Description:

Window Sliding Technique is a computational technique which aims to reduce the use of nested loop and replace it with a single loop, thereby reducing the time complexity.

What is Sliding Window?

Consider a long chain connected together. Suppose you want to apply oil in the complete chain with your hands, without pouring the oil from above.
One way to do so is to: 

* pick some oil, 
* apply onto a section of chain, 
* then again pick some oil
* then apply it to the next section where oil is not applied yet
* and so on till the complete chain is oiled

Another way to do so, is to use a cloth, dip it in oil, and then hold onto one end of the chain with this cloth. Then instead of re-dipping it again and again, just slide the cloth with hand onto the next section, and next, and so on till the other end.

The second way is known as the Sliding window technique and the portion which is slided from one end to end, is known as Sliding Window.

Problem:

[Link to the problem in leetcode for future assessment](https://leetcode.com/problems/k-radius-subarray-averages/)

Solution:

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
