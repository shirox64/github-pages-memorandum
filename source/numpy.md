# NumPy

## NumPyとは
NumPyは科学技術計算に特化したサードパーティ製パッケージで配列や行列を効率よく扱える。

## インポート
```Python
# NumPyのインポート
import numpy as np
```

## 1次元配列
```Python
# 1次元配列作成
array_1d = np.array([1, 2, 3])

array_1d
# array([1, 2, 3])

print(array_1d)
# [1, 2, 3]

type(array_1d)
# numpy.ndarray

array_1d.shape
# (3,)
```

## 2次元配列
```Python
# 2次元配列作成
array_2d = np.array([[1, 2, 3], [4, 5, 6]])

array_2d
# array([[1, 2, 3],
#        [4, 5, 6]])

print(array_2d)
# [[1, 2, 3]
#  [4, 5, 6]]

array_2d.shape
# (2, 3)
```

## 変形
``` Python
array1 = np.array([1, 2, 3, 4, 5, 6])
array1
# array([1, 2, 3, 4, 5, 6])

# 1次元配列を2次元配列に変形
array2 = array1.reshape((2, 3))
array2
# array([[1, 2, 3],
#        [4, 5, 6]])

# 変形する要素数が合わない場合は、エラーになる
array3 = array1.reshape((3, 4))
# ValueError: cannot reshape array of size 6 into shape (3,4)

# 1次元配列に戻す *参照を渡す
array4 = array2.ravel()
array4
# array([1, 2, 3, 4, 5, 6])

# 1次元配列に戻す *コピーを返す
array5 = array2.flatten()
# array([1, 2, 3, 4, 5, 6])
```

## データ型
``` Python
# データ型を指定しない場合は、自動で設定される
array1 = np.array([1, 2, 3])
array1.dtype
# dtype('int32')

# データ型を指定
array2 = np.array([1, 2, 3], dtype=np.int16)
array2.dtype
# dtype('int16')

# 配列作成後にデータ型を変更
array2.astype(np.float16)
# array([1, 2, 3], dtype=float16)
```

## インデックスとスライス
``` Python
array1 = np.array([1, 2, 3])
array1[0]
# 1
array1[1:]
# array([2, 3])
array1[-1]
# 3

array2 = np.array([[1, 2, 3], [4, 5, 6]])
array2[0]
# array([1, 2, 3])
array2[1, 0]
# 4
array2[:, 2]
# array([3, 6])
array2[1, :]
# array([4, 5, 6])
array2[0, 1:]
# array([2, 3])
arary2[:, [0, 2]]
# array([[1, 3],
#        [4, 6]])
```

## データ再代入
``` Python
array1 = np.array([1, 2, 3])
array1[2] = 4
array1
# array([1, 2, 4])

array2 = np.array([[1, 2, 3], [4, 5, 6]])
array2[1, 2] = 7
array2
# array([[1, 2, 3],
#        [4, 5, 7]])

array2[:, 2] = 8
array2
# array([[1, 2, 8],
#        [4, 5, 8]])
```

## 深いコピー
Python標準のリストではスライスした結果はコピーが渡されるが、NumPyではスライスした結果は参照が渡されるので注意。
``` Python

```

## 数列を返す
後日更新予定

## 乱数
後日更新予定