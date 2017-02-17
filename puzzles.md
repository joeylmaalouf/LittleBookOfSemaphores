# Little Book of Semaphores

### Joey Maalouf

## Chapter 1

#### 1.2

Assuming that Bob is willing to follow simple instructions, is there any way you can guarantee that tomorrow you will eat lunch before Bob?

Tell Bob not to eat lunch until you call him and give him permission to do so.

#### 1.5.1

Thread A:

```
x = 5
print x
```

Thread B:

```
x = 7
```

What path yields output `5` and final value `5`?

`b1 < a1 < a2`

What path yields output `7` and final value `7`?

`a1 < b1 < a2`

Is there a path that yields output `7` and final value `5`? Can you prove it?

No. In order for the output and final value to differ, we need the output to run before the value assignment. However, we know that the program cannot output (`a2`) before assigning `5` (`a1`); that is, it is guaranteed that `a1 < a2`. Thus, since we would need the order to resemble `b1 < a2 < a1`, but `a2` cannot come before `a1`, we have proved that there is no valid path.

#### 1.5.2

Suppose that 100 threads run the following program concurrently (if you are not familiar with Python, the for loop runs the update 100 times.):
```python
for i in range (100):
  temp = count
  count = temp + 1
```
What is the largest possible value of count after all threads have completed? What is the smallest possible value?

The largest possible value is `10000` (if, say, the first thread properly reads and increments the value, then the next thread reads, increments, etc.). The smallest possible value is `100` (if a thread reads the value, waits a while, and then increments on its own after everything else has modified the original).

#### 1.5.3

See answer to __1.2__. `1` message minimum.

## Chapter 2

...
