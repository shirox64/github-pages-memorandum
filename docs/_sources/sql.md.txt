# SQLスタイルガイド
QiitaにSQLスタイルガイドの良い記事があったので備忘録にまとめる。  
[SQLスタイルガイド](https://qiita.com/taise/items/18c14d9b01a5dfd6d35e)

## 予約語/関数は大文字にする
予約語と関数はそれ他と区別がつきやすいように大文字にする。  
ex) SELECE、FROM、WHERE
```SQL
SELECT
  COUNT(*) AS sushi_post_count
FROM
  microposts
WHERE
  content LIKE '%:sushi:%'
;
```

## インデントはスペース2で揃える
Pythonのようにインデントでブロックを示しているわけではないので推奨

## SQLの特定の予約の後は改行する
基本的には以下の予約語の後は改行する。
* SELECT
* FROM
* WHERE
* GROUP BY
* ORDER BY

SELECT句やWHERE句の中で利用される関数(COUNTやBETWEENなど)については、
同じ予約語でも改行の必要はない。  
改行が増えすぎて逆に読みづらくなります。
```SQL
SELECT
  DATE(created_at) AS created_date,
  COUNT(*) AS post_count
FROM
  posts
WHERE
  created_at BETWEEN '2015-12-01' AND '2015-12-10'
GROUP BY
  created_date
;
```

## 1カラム1行にする
SELECT、WHEREで指定するカラムや条件式は1行に1つまでとする。
```SQL
SELECT
  DATE(created_at) AS created_date,
  user_id,
  COUNT(*) AS post_count
FROM
  posts
WHERE
  created_at BETWEEN '2015-12-01' AND '2015-12-10'
GROUP BY
  created_date,
  user_id
;
```

## 条件のAND/ORは先頭に置く
AND/ORを先頭に置くと、その行がどちらに該当するのか分かりやすい。
```SQL
SELECT
  COUNT(*) AS user_count
FROM
  user
WHERE
  created_at >= '2015-12-01'
  AND status IN ('signup', 'available')
  AND admin IS NULL
;
```

## サブクエリは字下げする
サブクエリのインデントを下げることで、サブクエリの部分を判別しやすくする。
```SQL
SELECT
  post_count,
  COUNT(*) AS freq
FROM
  (
    SELECT
      user_id,
      COUNT(*) post_count
    FROM
      microposts
    GROUP BY
      user_id
  )
GROUP BY
  post_count
;
```

## CASE文は各予約語の前で字下げして改行する
字下げすることでどこまで条件式か分かりやすくなる。
```SQL
CASE
  WHEN hoge
    THEN 'hoge'
  WHEN piyo
    THEN 'piyo'
  ELSE 'other'
END 
```

## JOIN句は字下げして、ONはさらに字下げする
いろいろな流派があるらしい。。。
```SQL
SELECT
  COUNT(*) AS post_count
FROM
  microposts AS m
  INNER JOIN users AS u
    ON m.user_id = u.id
WHERE
  u.status IN ('signup', 'available')
;
```

## セミコロン(;)は最終行に置く
複数のSQLがあるときに、どこで終わっているか分かりやすくなる。
```SQL
SELECT
  COUNT(*) AS sushi_beer_post_count
FROM
  microposts
WHERE
  DATE(created_at) = DATE(UTC_TIMESTAMP())
  AND content REGEXP(':(sushi|beer):')
;
```
