# JavaScript

## 複数の配列の組み合わせを求める
```javascript
const makeComb = function(...array) {
  const make = (arr1, arr2) => {
      if (arr1.length === 0) {
        return arr2;
      }
      return arr1.reduce((arr, v1) => {
        arr2.forEach(v2 => {
          const group = [].concat(v1, v2);
          arr.push(group);
        });
        return arr;
      }, []);
    };

  return array.reduce(make, []);
};

var arr1 = [1, 2, 3];
var arr2 = [4, 5, 6];
var arr3 = [7, 8, 9];

var allCombination = makeComb(arr1, arr2, arr3);
```

結果
```
[
  [ 1, 4, 7 ], [ 1, 4, 8 ], [ 1, 4, 9 ],
  [ 1, 5, 7 ], [ 1, 5, 8 ], [ 1, 5, 9 ],
  [ 1, 6, 7 ], [ 1, 6, 8 ], [ 1, 6, 9 ],
  [ 2, 4, 7 ], [ 2, 4, 8 ], [ 2, 4, 9 ],
  [ 2, 5, 7 ], [ 2, 5, 8 ], [ 2, 5, 9 ],
  [ 2, 6, 7 ], [ 2, 6, 8 ], [ 2, 6, 9 ],
  [ 3, 4, 7 ], [ 3, 4, 8 ], [ 3, 4, 9 ],
  [ 3, 5, 7 ], [ 3, 5, 8 ], [ 3, 5, 9 ],
  [ 3, 6, 7 ], [ 3, 6, 8 ], [ 3, 6, 9 ]
]
```

## head要素内で外部javascriptを読み込むのは良くない
外部JSファイルを読み込み・実行されるまでの間はそれ以降のHTMLの解析がストップさせられるため、head要素内にそのような外部ファイルがあると結果的にページが表示されるのがそのぶん遅くなります。  
外部JavaScriptファイルはbody要素の最下部から読み込むほうがベター。

