node-jvm
========

## Overview

node-jvm - jvm in pure node.js


## Example

### java
```java
public class Main {
    public static long fib(int n) {
        if (n <= 1) return n;
        return fib(n-1) + fib(n-2);
    }
    
    public static void main(String[] args) {
        if (args.length == 0) {
                System.out.print("help: java Main.class {Number}");
                return;
        }
        
        int N = Integer.parseInt(args[0]);
        long start = System.currentTimeMillis();            
        System.out.format("Fibonacci from 1 to %s:\n", N);
        for (int i = 1; i <= N; i++) {
            System.out.println(i + ": " + fib(i));
        }
        long stop = System.currentTimeMillis();
        System.out.println("time: " + (stop - start) + "ms");
        
        System.out.println("done.");
    }
}
```

### node.js
```javascript
var JVM = require("../../index");
var jvm = new JVM();
jvm.loadClassFile("./Main.class");
jvm.run([10]);
```

### build java files
`cd examples fibonacci; make`

### run jvm
`./fibonacci.js`

### clean
`make clean`

### output
```
Fibonacci from 1 to 10:
1: 1
2: 1
3: 2
4: 3
5: 5
6: 8
7: 13
8: 21
9: 34
10: 55
time: 18ms
done.
```

### other examples
`cd examples/`

```
cast
dogs
fibonacci
idogs
static
switcher
```


## Developer

Yaroslav Gaponov (yaroslav.gaponov -at - gmail.com)

## License

The MIT License (MIT)

Copyright (c) 2013 Yaroslav Gaponov

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
