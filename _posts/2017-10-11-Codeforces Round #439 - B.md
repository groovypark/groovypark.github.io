---
title: Codeforces Round #439 - B
description:
categories:
tags: algorithm codeforce
---

# Codeforces Round #439 - B (The Eternal Immortality)

외국사이트인 [Codeforces](http://codeforces.com/)에서 #439번째 대회를 참가하였다.
문제는 총 5문제로,  2시간동안 문제를 푸는 것이다. A부터 E까지의 문제 중 B문제를 풀었다.


## 문제 - B. The Eternal Immortality

<center>
time limit per test1 second<br/>
memory limit per test256 megabytes<br/>
inputstandard input<br/>
outputstandard output<br/>
</center><br/>

Even if the world is full of counterfeits, I still regard it as wonderful.<br/>
Pile up herbs and incense, and arise again from the flames and ashes of its predecessor — as is known to many, the phoenix does it like this.<br/>
The phoenix has a rather long lifespan, and reincarnates itself once every a! years. Here a! denotes the factorial of integer a, that is, a! = 1 × 2 × ... × a. Specifically, 0! = 1.<br/>
Koyomi doesn't care much about this, but before he gets into another mess with oddities, he is interested in the number of times the phoenix will reincarnate in a timespan of b! years, that is, . Note that when b ≥ a this value is always integer.<br/>
As the answer can be quite large, it would be enough for Koyomi just to know the last digit of the answer in decimal representation. And you're here to provide Koyomi with this knowledge.<br/>

### Input

The first and only line of input contains two space-separated integers a and b (0 ≤ a ≤ b ≤ 1018).

### Output

Output one line containing a single decimal digit — the last digit of the value that interests Koyomi.

### Examples

| **input** |
|	2	4	|
| **output** |
|  	2   	|

| **input** |
|	0	10	|
| **output** |
| 	0		|

| **input** |
|	107	109	|
| **output** |
| 	2		|

### Note

In the first example, the last digit of 12 is 2.<br/>
In the second example, the last digit of 3628800 is 0.<br/>
In the third example, the last digit of 11772 is 2.<br/>


## 풀이

<script src="https://gist.github.com/groovypark/2f7672cedf66444f2d5d8654c97e91ab.js"></script>

처음에 단순히 분자(b) 나누기 분모(a)만 생각하여 b값부터 1씩 감소하며 b-a횟수만큼 곱해주면 된다고 생각했다. 그래서 결과값이 나온 뒤 %10을 하여 10의 나머지값을 받아 1의 자릿수를 구하였다.<br/>
하지만 제출을 해보니, input값이 커졌을 때 런타임 에러가 나왔다. 그래서 input 값인 a, b를 int에서 long으로 고쳤다. 또한 일의 자릿수만 곱해주기 위해 b%10으로 계산하였다.