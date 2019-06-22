---
layout: post
title:  "The Bit"
date:   2019-06-21 22:10:17 -0400
categories: data_types
tag: [bit]
author: taimorekhan
---
## Bits, Bytes, and Primitive Data Types: Part 1

###  Defining the bit
Bit is actually short for 'binary digit'. It stores an electrical signal that is either above or below a specific voltage level as either  `1` or `0` (commonly also known as as electricity `on` or `off`, as well as boolean operators `true` or `false`). 

*It is the most basic unit of digital information.* 

By grouping bits together, we can use the binary system to represent information in a way the computer can store and manipulate it. Future Me will explore this concept later and (hopefully) put link to that [here](#).

In the examples below, for the sake of simplicity, we will use voltage difference between 0 and 3V. A voltage between 1.5V and 3V will register a bit value of `1`, whereas anything less than 1.5V will register a bit value of `0`. 

### Binary vs decimal
So why is it that we store information in binary - why not use decimal numbers? 

When using binary, we only need to differentiate between only two values: `0` and `1`. By registering everything above 1.5V as `1` and anything below it as `0` - we get two fairly large and distinct 'sections' as seen in Figure 1 below: 

Figure 1
![binary visualization](/assets/images/binary-visualization.png)

In order to store decimal values in bits* (it probably would have to be renamed then, wouldn't it?), it would be necessary to divide the difference of 3V into 10 parts instead of 2 - and then reliably distinguish between the smaller 10 voltage 'sections' as in Figure 2 below:

Figure 2
![decimal visualization](/assets/images/decimal-visualization.png)

This is incredibly difficult due to voltage fluctuation and stabilization.  

In the world of binary, because the voltage 'section' that resolves into a bit value is quite large, it can tolerate a fair degree of voltage inconsistency or fluctuation. When storing decimal values, however, those same fluctuations can result in errors since the voltage 'section' (or tolerance) is much smaller. 

In order to overcome the errors caused by voltage fluctuations, even simple solutions can become intricate (read: expensive). For example, simply increasing to a larger voltage difference (0V to 10V) would result in the system running hot, thus requiring more extensive cooling, ventilation, and  additional space. 

Imagine a decimal-bit smart phone: it's twice as big, running twice as hot, probably costs twice as much as its binary-bit counterpart, but isn't really doing anything at all better in terms of processor performance (it might even be worse!). It's no surprise that the most basic building block of computers wound up being binary.

### The downsides of binary
The binary system is not 100% superior to the decimal. The tradeoff is space: representing a number in binary takes up more space than representing it in decimal. 

This magic formula reveals exactly how much more space: log<sub>2</sub> 10 = 3.322

What that means is using bits to represent a number will require a constant multiplier of 3.322 more bits than if we were to use decimal values. 

Consider the decimal number `99`. Its binary representation is `1100011`. The decimal representation has two values - one indicating the tens place (`90`) and one indicating the ones place (`9`). The binary representation requires 7 bits, each from right to left representing an increasing power of 2 (for more on understanding binary representation of numbers, see [this](https://medium.com/@LindaVivah/learn-how-to-read-binary-in-5-minutes-dac1feb991e) article). 

We can see that `2 * 3.322 = 6.644`. Since you can't have `.644` of a bit we'll round up to get: `7` - which is exactly how many bits the magic formula told us we'd need to represent a decimal value. 

In the grand scheme of things, taking up 3.322 times the amount of space to represent a value isn't enough of an setback to be an arguement against the use of the binary system as the smallest unit or building block for digital information. In fact, there are a lot of clever arithmetic tricks that can be done thanks to binary - probably also another topic for Future Me to invest some time in.  

### Related topic: clock speed 
In the real world, voltage does not just go from `1` to `0` or vice versa instantaenously. While it may be an incredibly fast, it still takes some time for the voltage to drop enough to switch values. A chip's clock speed is essentially how long the processor needs to wait before reading that bit again to make sure that it's had enough time to stabilize. 

Figure 3
![clock speed visualization](/assets/images/clock-speed-visualization.png)

### Also related: overclocking
Overclocking is decreasing the time the processor is told to wait before re-reading the bit. While this may increase the speed at which processes are done, decreasing the time too drastically can result in errors.  

Figure 4
![overclocking visualization](/assets/images/overclocking-visualization.png)

Given this tidbit of knowledge, we can now see why dividing a 'bit' into ten is incredibly difficult. In order to get an accurate result, the voltage would have to stabilize perfectly when the 'clock strikes' - being off even slightly would result in an erroneous value. 

### Concluding Thoughts
While it may seem like `0`s and `1`s are pretty straightforward, hopefully you see that it can be really interesting. I've only presented one small subset of information on this topic. Read more about bits in [this article](
https://medium.com/coderscorner/what-exactly-is-in-a-1-bit-of-digital-memory-d5395f9001a6).

Also, a big thanks to Conrad Poelman for learning me more about the bit today and making this a much more interesting piece!

Future Me will (hopefully) continue this series with a discusson on the byte - see you next time!