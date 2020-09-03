#  Pytorch sheet cheat

## Basics

_Notation_: `t` denotes a tensorflow tensor, `a` a numpy array

| torch        |  numpy equivalent | description |
|--------------|-------------------|-------------|
| `t.shape`    | `a.shape`         |  tensor dimensions |
| `t.size()`   | `a.shape`         | same as `t.shape` |
| `t.numel()`  | `a.size`          | number of elements in the tensor| 
| `t.ndimensions` | `len(a.shape)` | tensor rank |
| `t.item()`   | `a.item()`        | only for tensors that have one element, <br /> the single element of the tensor as Python float or int  |
| `t.numpy()`  |                   | convert to numpy array |
| `tensor.from_numpy(a)` |          | numpy array converted to tensor | 

