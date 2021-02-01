# 分治（Divide-and-Conquer）

## 1. 什么是分治

分治本质上就是递归，只不过它是递归的其中一个细分类。

递归：实质上是找重复性
+ 最近重复性：分治、递归等
+ 最优重复性：动态规划

## 2. 分治代码模板

```JavaScript
const divide_conquer = (problem, params) => {
    // recursion terminator
    
    if (problem == null) {
        process_result
        return
    }

    // process current problem

    subproblems = split_problem(problem, data)

    subresult1 = divide_conquer(subproblems[0], p1)
    subresult2 = divide_conquer(subproblems[1], p1)
    subresult3 = divide_conquer(subproblems[2], p1)

    // ...


    // merge
    result = process_result(subresult1, subresult2, subresult3)

    // revert the current level status
}
```