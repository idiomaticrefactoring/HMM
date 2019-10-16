#  Hidden Markov Model, HMM

## Problem
 对于单只股票数据，我们每日可以观测到的值可以是涨、跌，不涨不跌（相对于昨天的
收盘价）三种情况。这⾥将观测的涨跌平编码为0,1,2 三种取值（0：跌，1：涨，2：平）。
我们假设股票的涨跌由内在的隐变量驱动（这是⼀个⼗分简化的假设），即⽜市或熊市。
换⾔之，⽜市（编码为1）⽐较有可能驱动股票价格上涨，熊市（编码为0）⽐较有可能驱
动股票下跌。换⾔之，在本HMM 模型中，隐变量仅仅是1 维的0/1 离散状态。
## code 
1. `HMMViterbi `

  input:a,b,o,pi

  output: path

这里，a 是状态转移矩阵(transition matrix), b 是发射矩阵(emission matrix)，o 是观
测到的序列（例如[0; 1; 1; 1; 2; 1; 0; 1; 0], pi 是初始分布initial probabilities）输出是最有可
能的隐变量序列（0,1 序列）

2. `HMMfwd`

input:a,b,o,pi
output:beta(p(x|y)，给定状态得到观测值的概率)
