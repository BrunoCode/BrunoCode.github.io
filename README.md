# What I have been up to recently

I plan on writing decending sorted notes about my current endeavors. These notes help me keep a record of my progress toward my small and large goals.
My current medium sized goal is to get good at leetcode/hackerank style interview questions. This is likely the first step in any job interview. 
Thanks for reading.


# 2021-03-31 (March 31, 2021)

We saw the solution to the two sum problem on a sorted array yesterday. Let's see how we get to how we got there. On the original two sum problem, that makes no guarantees
about sorting, the optimal solution is to use a hashmap to store complements that we are looking for in the rest of the array. 

This optimal solution has O(n) complexity. And it has a O(n) space complexity. So how could we get a better solution if our input is a sorted array? Can we get better than O(n) complexity? Most likely not because you may likely have to check every element in the array. What we might be able to do is reduce the space complexity. The only way we could reduce space complexity is if we could remove the use of the hashmap. The hashmap was storing complements to look for in the rest of the array to sum up to the target.

So in what way can we use the fact that the array is sorted to avoid storing complaments. Let's narrow the question: What new information can we now easily obtain from a sorted array. Even better said what information can I now obtain in O(1) time? On a sorted array:

* I can get the min value.
* I can also get the max value.
* I can get the median.
* I can know exactly where in the array the above 3 values exist.
* I can calculate the diff between the min and max.

Okay let's analyze this information. 

* Because I know the min and max and the diff between them I know that there are no two other numbers in the array with a greater diff than the min and max.
* I know that if I wanted to get the smallest sum I could sum the value at index 0, and index 1.
* I know that if I wanted to get the largest sum I could sum the last value with the second to last value.

# 2021-03-30 (March 30, 2021)

This is a continuation of my last post. Before I talk about how to get to the inuition behind the solution of the two sum problem on a sorted array. I would like to reveal my code solution in and effort to simplify my the explaination of the intuition behind the solution easier.
    
    var twoSum = function(numbers, target) {
      let minIdx = 0;
      let maxIdx = numbers.length - 1;

      while (minIdx < maxIdx) {
          let currMin = numbers[minIdx];
          let currMax = numbers[maxIdx];
          if (currMin + currMax === target) {
              return [ minIdx + 1, maxIdx + 1 ];
          }
          if (currMin + currMax < target ) {
              minIdx++;
          } else {
              maxIdx--;
          }
      }
    }

# 2021-03-29 (March 29, 2021)

Today I worked on breaking down the intuition behind the two sum problem on a sorted integer array. This is a simple problem that anyone could eventually intuitively solve. I wanted to focus on clearly defining what that intuition was. I believe this is an important aspect of critical thinking. Reflecting on the intuition behind these problems will help us develop a strategy to tackle future coding problems.
