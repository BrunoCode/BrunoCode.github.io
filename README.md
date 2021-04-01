# What I have been up to recently

I plan on writing decending sorted notes about my current endeavors. These notes help me keep a record of my progress toward my small and large goals.
My current medium sized goal is to get good at leetcode/hackerank style interview questions. This is likely the first step in any job interview. 
Thanks for reading.


# 2021-03-31 (March 31, 2021)

We saw the solution to the two sum problem on a sorted array yesterday. Let's see how we get to how we got there. On the original two sum problem, that makes no guarantees
about sorting.

# 2021-03-30 (March 30, 2021)

This is a continuation of my last post. Before I talk about how to get to the inuition behind the solution of the two sum problem on a sorted array. I would like to reveal my code solution in and effort to my the explaination of the intuition behind the solution easier.
    
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
