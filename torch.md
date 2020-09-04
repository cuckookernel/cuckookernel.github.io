#  Pytorch sheet cheat

## Basics

`import torch; import numpy as np` is assumed

_Notation_: `t` denotes a tensorflow tensor, `a` a numpy array, `df` a data frame, `17` an arbitrary scalar 

### Creating tensors, converting to/from numpy

| torch        |  numpy equivalent | description |
|--------------|-------------------|-------------|
| `torch.tensor( obj )` |  | create a tensor from a Python object that is a list of lists (or a single Python number)  |
| `torch.tensor( obj, requires_grad=True )` |  | when we want to compute derivatives of some scalar function with respect to this tensor |
| `t.numpy()`  |                   | convert to numpy array |
| `torch.from_numpy(a)` <br /> `torch.from_numpy( df.values )` |          | numpy array converted to tensor | 
| `t.detach().numpy()` |  |  necessary when tensor is included on a computation graph, i.e `t.requires_grad == True` | 


### Basic tensor characteristics
| torch        |  numpy equivalent | description |
|--------------|-------------------|-------------|
| `t.shape`    | `a.shape`         |  tensor dimensions |
| `t.size()`   | `a.shape`         | same as `t.shape` |
| `t.numel()`  | `a.size`          | number of elements in the tensor| 
| `t.ndimensions` | `len(a.shape)` | tensor rank |


### Indexing slicing and extracting values
| torch        |  numpy equivalent | description |
|--------------|-------------------|-------------|
| `t.item()`   | `a.item()`        | only for tensors that have one element, <br /> the single element of the tensor as Python float or int  |
| `t[i]`   | `a[i]` | (zero based) indexing into first dimension; evaluates to a tensor that is 1 less in rank | 
| `t[i][j]` | `a[i][j]` | index into first, then second dimension; evals. to tensor that is 2 less in rank | 
| `t[i, j]` | `a[i, j]` | indexing directly first and second dimensions; same as `a[i][j]` but presumably faster as it is a single python function call (?) |
| `t[i1:i2, j1:j2 ] ` | `a[i1:i2, j1:j2]` | slicing directly into first and second dimensions | 

### Operations on tensors

| torch        |  numpy equivalent | description |
|--------------|-------------------|-------------|
| `torch.sum(t)` | `np.sum(a)` |  sum of all elements in tensor | 
| `t1 + t2` | `a1 + a2` | component wise sum of tensors |
| `t1 * t2` | `a1 * a2` | component wise product of tensors, also known as Hadamard product, NOT to be confused with dot product or matrix multiplication! |
| `17 * t`, `t * 17` | `17 * a`, `a * 17` | multiplication (of each element) by a scalar | 
| `torch.mm( t1, t2 )` | `np.matmul( a1, a2)` | matrix multiplication | 
| `torch.relu(t)` | `a * (a >= 0)`  | component wise result of `max(x , 0)`  |

## Datasets 

Datasets are objects of classes inheriting from `torch.util.Dataset`. They should implement `__getitem__` and `__len__` functions.




