判断数字x是否是2的n次方，x>0且为整数。


方法一：循环
```
function isPowerOf2(x){
  while(x){
    if(x%2===0){
      x = x/2
      if(x===1){
        return true
      }
    }else{
      return false
    }
  }
  return false
}
```

方法二： 位运算
```
function isPowerOf2(x){
  return (x&(x-1)) === 0
}
```
原理：
2的n次方的二进制特点是：首位是1其余为是0，而比2的n次方小的其他任意数首位肯定是0，其余随便，这样当二者进行与运算时一定为0。
```
1    ---- 2
10   ---- 4
100  ---- 8
1000 ---- 16
```

与运算：当且仅当两个操作数都为真时,结果才为真。用符号“∧”表示,例如:A∧B,表示A和B都为真时,结果为真。
```
100111  
001101  
------  
000101  
```

2的n次方与运算：
```
100000  
001101
------
000000
```