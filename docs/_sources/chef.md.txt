# Chef

## yumが機能しないとき
```
Could not retrieve mirrorlist https://mirrors.iuscommunity.org/mirrorlist?repo=ius-centos7&arch=x86_64&protocol=http error was
14: curl#6 - "Could not resolve host: mirrors.iuscommunity.org; Name or service not known"
```

* IUSを追加すれば解決  
`sudo yum -y install https://centos7.iuscommunity.org/ius-release.rpm`
