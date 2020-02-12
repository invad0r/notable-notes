---
tags: [Notebooks]
title: big o notation
created: '2019-07-30T06:19:49.029Z'
modified: '2020-02-04T12:32:22.140Z'
---

# big o notation

## usage
```javascript
var calcVariance(data) {

  var sum = 0.0;
  var squareSum = 0.0;
  var n = data.length;

  for ( var i = 0; i < n; i++) {

    sum += data[i];
    squareSum += data[i] * data [i];
  }

  var variance = ( squareSum - ( sum * sum ) / n ) / n ;
  var average =
}
```

## recursion

### factoral recursion with bash
```sh
#!/usr/local/bin/bash
fact() {
  local -i n=${1:0}
  (( n == 0 )) && echo 1 && return
  (( nm1 = n - 1 ))
  (( result = n * $(fact $nm1) ))
  echo $result
}

for i in {1..25}; do
  echo fact ${i} is: $(fact ${i})
done
```

## see also
- [Big-O Algorithm Complexity Cheat Sheet (Know Thy Complexities!) @ericdrowell](http://bigocheatsheet.com/)
- [Big-O notation explained by a self-taught programmer](https://justin.abrah.ms/computer-science/big-o-notation-explained.html)
- [Big-O notation (article) | Algorithms | Khan Academy](https://www.khanacademy.org/computing/computer-science/algorithms/asymptotic-notation/a/big-o-notation)
- [A beginner's guide to Big O notation - Rob Bell](https://rob-bell.net/2009/06/a-beginners-guide-to-big-o-notation/)
