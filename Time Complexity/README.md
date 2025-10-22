# Time Complexity

Use of time complexity makes it easy to estimate the running time of a program. Performing an accurate calculation of a program’s operation time is a very labour-intensive process (it depends on the compiler and the type of computer or speed of the processor). Therefore, we will not make an accurate measurement; just a measurement of a certain order of magnitude. Complexity can be viewed as the maximum number of primitive operations that a program may execute. Regular operations are single additions, multiplications, assignments etc. We may leave some operations uncounted and concentrate on those that are performed the largest number of times. Such operations are referred to as dominant. The number of dominant operations depends on the speciﬁc input data. We usually want to know how the performance time depends on a particular aspect of the data. This is most frequently the data size, but it can also be the size of a square matrix or the value of some input variable.

### 3.1: Which is the dominant operation?
```python
def dominant(n):
    result = 0
    for i in xrange(n):
        result += 1
    return result
```

The operation in line 4 is dominant and will be executed n times. The complexity is described in Big-O notation: in this case O(n) — linear complexity.
The complexity speciﬁes the order of magnitude within which the program will perform its operations. More precisely, in the case of O(n), the program may perform c · n operations, where c is a constant; however, it may not perform n^2 operations, since this involves a diﬀerent order of magnitude of data. In other words, when calculating the complexity we omit constants: i.e. regardless of whether the loop is executed 20 · n times or 5 n times, we still have a complexity of O(n), even though the running time of the program may vary. When analyzing the complexity we must look for speciﬁc, worst-case examples of data that the
program will take a long time to process.

## 3.1. Comparison of different time complexities

### 3.2: Constant time — O(1).

```python
 def constant(n):
 result = n * n
 return result
```
There is always a ﬁxed number of operations.

### 3.3: Logarithmic time — O(log n).

```python
 def logarithmic(n):
 result = 0
 while n > 1:
 n //= 2
 result += 1
 return result
```
The value of n is halved on each iteration of the loop. If n = 2x then log n = x. How long
would the program below take to execute, depending on the input data?

### 3.4: Linear time — O(n).
```python
 def linear(n, A):
 for i in xrange(n):
 if A[i] == 0:
 return 0
 return 1
```
Let’s note that if the ﬁrst value of array A is 0 then the program will end immediately. But
remember, when analyzing time complexity we should check for worst cases. The program
will take the longest time to execute if array A does not contain any 0.

### 3.5: Quadratic time — O(n2).
```python
 def quadratic(n):
 result = 0
 for i in xrange(n):
 for j in xrange(i, n):
 result += 1
 return result
```
The result of the function equals $`\frac{1}{2}\times (n\times(n+1)) = \frac{1}{2}\times n^2 + \frac{1}{2} \times n`$ (the explanation is in the exercises). When calculating the complexity we are interested in a term that grows fastest, so we not only omit constants, but also other terms ( 12 · n in this case). Thus we get quadratic time complexity. Sometimes the complexity depends on more variables (see example below).

### 3.6: Linear time — O(n + m).

```python
 def linear2(n, m):
 result = 0
 for i in xrange(n):
 result += i
 for j in xrange(m):
 result += j
 return result
```

### Exponential and factorial time
It is worth knowing that there are other types of time complexity such as factorial time O(n!)
and exponential time O(2n ). Algorithms with such complexities can solve problems only for
very small values of n, because they would take too long to execute for large values of n.

## 3.2. Time limit

Nowadays, an average computer can perform $`10^8`$ operations in less than a second. Sometimes we have the information we need about the expected time complexity (for example, Codility speciﬁes the expected time complexity), but sometimes we do not.

The time limit set for online tests is usually from 1 to 10 seconds. We can therefore
estimate the expected complexity. During contests, we are often given a limit on the size of
data, and therefore we can guess the time complexity within which the task should be solved.
This is usually a great convenience because we can look for a solution that works in a speciﬁc
complexity instead of worrying about a faster solution. For example, if:
- n <= 1 000 000, the expected time complexity is O(n) or O(n log n),
- n <= 10 000, the expected time complexity is O(n^2),
- n <= 500, the expected time complexity is O(n^3).

Of course, these limits are not precise. They are just approximations, and will vary depending
on the speciﬁc task.

## 3.3. Space complexity
Memory limits provide information about the expected space complexity. You can estimate
the number of variables that you can declare in your programs.
In short, if you have constant numbers of variables, you also have constant space com-
plexity: in Big-O notation this is O(1). If you need to declare an array with n elements, you
have linear space complexity — O(n).

More speciﬁcally, space complexity is the amount of memory needed to perform the com-
putation. It includes all the variables, both global and local, dynamic pointer data-structures
and, in the case of recursion, the contents of the stack. Depending on the convention, input
data may also be included. Space complexity is more tricky to calculate than time complexity
because not all of these variables and data-structures may be needed at the same time. Global
variables exist and occupy memory all the time; local variables (and additional information
kept on the stack) will exist only during invocation of the function.

## 3.4. Exercise
**Problem**: You are given an integer n. Count the total of 1 + 2 + . . . + n.

**Solution**: The task can be solved in several ways. Some person, who knows nothing about
time complexity, may implement an algorithm in which the result is incremented by 1:

### 3.7: Slow solution — time complexity O(n2 ).
```python
def slow_solution(n):
    result = 0
    for i in xrange(n):
        for j in xrange(i + 1):
            result += 1
    return result
```
Another person may increment the result respectively by 1, 2, . . . , n. This algorithm is much
faster:
### 3.8: Fast solution — time complexity O(n).
```python
def fast_solution(n):
    result = 0
    for i in xrange(n):
        result += (i + 1)
    return result
```
But the third person’s solution is even quicker. Let us write the sequence 1, 2, . . . , n and
repeat the same sequence underneath it, but in reverse order. Then just add the numbers
from the same columns:
The result in each column is n + 1, so we can easily count the ﬁnal result:

| 1   | 2   | 3   | ... | n-1 | n   |
|-----|-----|-----|-----|-----|-----|
| n   | n-1 | n-2 | ... | 2   | 1   |
| n+1 | n+1 | n+1 | ... | n+1 | n+1 |

### 3.9: Model solution — time complexity O(1).
```python
def model_solution(n):
result = n * (n + 1) // 2
return result
```