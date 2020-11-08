---
template: post
title: Kalman Filter Source Code Analysis
slug: kalman_filter_analysis
socialImage: /media/wjlm5dqwlp.png
draft: false
date: 2020-11-07T23:37:50.967Z
description: Kalman Filter Source Code Analysis
category: programming
tags:
  - cpp
---
- source: [hmartiro/kalman-cpp: Basic Kalman filter implementation in C++ using Eigen](https://github.com/hmartiro/kalman-cpp) => in test.cpp, there are a few mistakes made when initiating the class.

### The structure of the code
The main structure of this code follows the equations in [kalman_intro](https://www.cs.unc.edu/~welch/media/pdf/kalman_intro.pdf).
![](https://i.imgur.com/bdtAieZ.png)


![](https://i.imgur.com/kFO7Osu.png)
1. the constructor function will take matrix A, B, Q in control update and matrix H, R in measurement update as input.
2. The function overloading in the init() can decide whether the function will set the initial state as zero.


### The more concise way to write in cpp
- initialize list
    - When a instance of a class is declared, the member variable inside can be initialized in a compact way.
- `this`
    - `this` is an implicit variable for every member function inside a class. But if there are varaibles having same name as parameters, one have to use `this` to refer to the member variable.
    ![](https://i.imgur.com/Sv9Xips.png)

- Function Overloading
    - [C++ Function Overloading in Classes | Studytonight](https://www.studytonight.com/cpp/function-overloading.php)
- public variables vs private variables
    - If a member variable don't need to be modified outside a class, one should use `private` to encapsulate the variable.


### `Eigen` tips
- Use `Eigen::MatrixXd` to specify matrix that have no fixed dimension.
    - use `Eigen::MatrixXd` to specify different shape of Matrix, and we can write our prediction and correction rule in the more general way.



##### Reference:
- https://www.cs.unc.edu/~welch/media/pdf/kalman_intro.pdf
- [Types of function arguments in python | getKT](https://getkt.com/blog/types-of-function-arguments-in-python/)
