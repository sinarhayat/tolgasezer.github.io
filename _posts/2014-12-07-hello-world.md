---
title: Technological Innovation In Asset Management
date: 2014-12-07
tags: Agent-Based Simulation Investor Heterogeneity
layout: post
---

Can asset management companies set themselves apart through
technological innovation? In our ongoing research titled "Investor
Heterogeneity and Investment Decision", we try to tackle this question
using an Agent-Based Simulation framework.

Our preliminary results provide evidence that asset management firms
can achieve better investor retention through a process innovation
which utilizes investor-centric utility-driven allocation style.

<!-- more -->

Let's assume following artificial world:

### Heterogenous Investors 

In our artificial world, we have 1000 investors who randomly define
their own utility-function at the beginning of the period based on:

- expected return
- expected volatility
- maximum drawdown limit
- expected carry 

<br>

$$utility^{i} = f(r\_{exp}^{i}, \sigma\_{exp}^{i}, maxDD\_{exp}^{i},
carry\_{exp}^{i})$$

<br>

Once defined at the beginning of
the period, investors do not update their utility function.

Let's also assume that investors have a primitive behavioural
rule. They choose a asset management company randomly and exit when
their maximum drawdown is hit. They re-enter at random at the next time
tick. Everytime the investor enters, he informs the asset managment
company of his individual utility function.

In this artificial world, we further assume a minimum level of consiousness,
i.e. "ZIP", and do not consider attributes such as "{Memory", "Conscioussness", "Reasoning".

### Heterogenous Asset Managers

There are 5 asset management companies. All of them are fund-of-fund
companies who can choose among a pool of 1000 funds in the
market. The 1000 funds belong to one of the two fund strategies:

- Global Macro
- Long/Short Equity

They pick one fund or a composition of funds within each fund
strategy category and then allocate between the funds they have
picked.

Each of the asset management companies has 5 styles of
picking from within the fund strategy category. These "picking styles" are:

- Dice (uniform random)
- Diversified (weighted by asset under management)
- Popular (maximum asset under management)
- Skilled (hit probability > 0.50)
- Lousy (hit probability < 0.50)

When it comes to allocating between the two fund strategies, the 5 asset
management companies differentiate themselves through their allocation styles:

- GoSharpe (mean-variance optimisation)
- Timid (minimum variance optimisation)
- Rambo (maximum return)
- Balanced (inverse volatility weighted)
- Thumbprint (investor-centric utility-function optimisation)

Since there are 1000 investors, each asset management company has initially 200
investors who are evenly distributed among the 5 picking
styles. That means we have 25 investment products offered each having
40 investors subscribed. Among the 25 products, only 5 products
consider the utility-function of the investor when deciding on the
allocation.

### Data & Rules
We have monthly historical hedgefund data starting from 1998 of which
we consider two relatively uncorrelated investment strategy
categories namely "Long-Short Equity" and "Global Macro".



<br>

##### Investor

<table class="table table-stripped table-hover">
<tr><th align="left"></th><th align="left"># Utility Function</th><th align="left"># Entry/Exit</th></tr>
<tr><td>Action</td><td align="left">inform asset manager</td><td align="left">exit when maxDD is hit, enter randomly</td></tr>
<tr><td>Characteristics</td><td align="left">f(R, Vol, maxDD, Sharpe, Carry)</td><td align="left">maxDD, random (ZIP)</td></tr>
</table>

##### Asset Manager

<table class = "table table-stripped table-hover">
<tr><th align="left"></th><th align="left"># Picking Style</th><th align="left"># Allocation Style</th></tr>
<tr><td>Action</td><td align="left">pick hedge-funds</td><td
align="left">allocate weights</td></tr>
<tr><td>Characteristics</td><td align="left">{rand, aumW, maxAUM,
goodP, badP}</td><td align="left">{meanVAR, minVAR, maxReturn,
VolWeighted, uFunction}</td></tr>
</table>

<br>

### Results

<br>

### Graph 1: Investor Migration
<p align="center">
  <img />
<img src="/assets/posts/graphs/plot1.png" width="70%">
</p>

<br>

Graph 1 shows the migration pattern of investors over time. It is apparent
that the "Lousy" picking style looses almost all of his investors
regardless of the allocation style. Interestingly, we experience on
market regime during which there is a major migration across the
investment products. 

<br>

### Table 1: Investor Emigration
<table class = "table table-stripeed table-hover"><tbody><tr><th></th><th>AUM WEIGHTED </th><th>BAD PICK </th><th>GOOD PICK </th><th>MAX AUM </th><th>RANDOM</th></tr><tr><td>MEAN VAR </td><td>           1 </td><td>      41 </td><td>       17 </td><td>      1 </td><td>    11</td></tr><tr><td>MIN VAR  </td><td>           1 </td><td>      40 </td><td>       16 </td><td>      1 </td><td>     5</td></tr><tr><td>RETURN        </td><td>           0 </td><td>      42 </td><td>       20 </td><td>      4 </td><td>    19</td></tr><tr><td>UF            </td><td>           7 </td><td>      41 </td><td>       13 </td><td>      4 </td><td>    18</td></tr><tr><td>VOLATILITY    </td><td>           3 </td><td>      41 </td><td>       16 </td><td>      1 </td><td>    23</td></tr></tbody></table>


### Table 2: Fatal Period (highest number of redemptions in a single period)
<table class = "table table-stripeed table-hover"><tbody><tr><th></th><th>AUM WEIGHTED </th><th>BAD PICK </th><th>GOOD PICK </th><th>MAX AUM </th><th>RANDOM</th></tr><tr><td>MEAN VAR </td><td>          -1 </td><td>     -22 </td><td>       -6 </td><td>     -1 </td><td>    -9</td></tr><tr><td>MIN VAR  </td><td>          -1 </td><td>     -19 </td><td>       -8 </td><td>     -1 </td><td>    -5</td></tr><tr><td>RETURN        </td><td>           0 </td><td>      -8 </td><td>       -9 </td><td>     -4 </td><td>   -14</td></tr><tr><td>UF            </td><td>          -6 </td><td>     -11 </td><td>       -6 </td><td>     -3 </td><td>   -10</td></tr><tr><td>VOLATILITY    </td><td>          -1 </td><td>     -12 </td><td>       -8 </td><td>     -1 </td><td>   -11</td></tr></tbody></table>
























