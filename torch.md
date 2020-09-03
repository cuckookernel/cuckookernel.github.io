#  Pytorch sheet cheat

## Basics

_Notation_: `t` denotes a tensorflow tensor, `a` a numpy array

| torch        |  numpy equivalent | description |
|--------------|-------------------|-------------|
| `t.shape`    | `a.shape`       |  tensor dimensions |
| `t.size()`   | `a.shape`        | same as `t.shape` |
| `t.numel()`  | `np.product(a.shape)` | number of elements in the tensor| 
| `t.ndimensions` | `len(a.shape)` | tensor rank |
| `t.item()`   | `a.item()` | the single element of the tensor as Python float or int only for tensors that have one element |


