## Whale-Optimization-Algorithm-python
- simple WOA (Whale Optimization Algorithm) implementation
- used Numpy for matrix computation (**No For Loop**)
- Original Paper [here](http://fa.mie.sut.ac.ir/Downloads/AcademicStaff/5/Courses/17/The%20Whale%20Optimization%20Algorithm%202016.pdf)

## Test
- Rosenbrock function (=Banana function)
  - minimum solution : (1, 1)
```python
def f(X):
    a, b = 1, 100
    sol = []
    for x in X:
        sol.append(((a - x[0]) ** 2) + b*(x[1]-x[0]**2)**2)
    return np.array(sol)
```

- Rastrigin function
  - minimum solution : (0, 0)
```python
def f(X):
    A = 10
    sol = []
    for ind in X:
        sol.append(A*len(ind) + sum([(i**2 - A * np.cos(2 * np.pi * i)) for i in ind]) )
    return np.array(sol)
```

## WOA
- Whale Optimization Algorithm Code in woa.py
  - # of whales : **n_whale** (default: 100, __init__ parameter)
  - # of iterations : **n_iter** (default: 100, __init__ parameter)
  - Spiral Constant : **spiral_constant** (default: 0.5, __init__ parameter)
    - controls the shape of the spiral which whales follow (from [here](https://github.com/HaaLeo/swarmlib/blob/master/swarmlib/woa/main.py))

## Requirements
- matplotlib==3.5.1
- numpy==1.20.0
