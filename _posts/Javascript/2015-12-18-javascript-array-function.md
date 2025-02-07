---
layout:     post
title:      "Javascript各种数组方法"
subtitle:   "Javascript各种数组方法"
date:       2015-02-18
author:     "YingxueLiu"
category:  技术
tags:
    - 技术
    - Javascript
    - Array
---

##数组的基本方法如下

####1. concat()

该方法用于连接2个或者多个数组。该方法不会改变现有的数组，而仅仅会返回被连接数组的一个副本。

语法：`arrayObject.concat(array1,array2,....arrayx)`;

连接多个数组，使用逗号隔开；

比如如下代码演示：


    var arr1 = [1,2,3],
        arr2 = [4,5,6],
        arr3 = [7,8,9,1,2,3];
    console.log(arr1.concat(arr2,arr3)); // [1, 2, 3, 4, 5, 6, 7, 8, 9, 1, 2, 3]
    console.log(arr1); // [1,2,3]
    console.log(arr2); // [4,5,6]
    console.log(arr3); // [7,8,9,1,2,3]

<!-- more -->

####2. join()

该方法是把数组中的所有元素放入一个字符串中，元素通过指定的分隔符进行分割的。

语法如下：`arrayObject.join(separator)`;

separator: 指定分隔符对数组中的元素进行分割，如果省略该参数，则会使用逗号作为分隔符。如下代码演示：


    var arrs = [];
    arrs[0] = "aa";
    arrs[1] = "bb";
    arrs[2] = "cc";
    console.log(arrs.join()); // aa,bb,cc
    console.log(arrs.join("/")); // aa/bb/cc
    console.log(arrs.join("-")); // aa-bb-cc



####3.pop()

该方法删除数组的最后一个元素，把数组的长度减1，并且返回它被删除元素的值，如果数组变为空，则该方法不改变数组，返回undefine值。如下代码演示：

    var arrs = [1,2,3,4];
    console.log(arrs.pop()); // 4
    console.log(arrs);  // [1,2,3]

####4.push()

该方法是向数组末尾添加一个或者多个元素，并返回新的长度。

基本语法：`arrayObject.push(newElem1,newElem2,.....newElemX)`; 演示代码如下：

    var arrs = [1,2,3];
    arrs.push(4); 
    console.log(arrs);  // [1,2,3,4]
    arrs.push(5,6); 
    console.log(arrs);  // [1,2,3,4,5,6]

####5.reverse()

该方法用于颠倒数组中元素的顺序；

语法如下：`arrayObject.reverse()`;

如下代码演示：

    var arrs = [1,2,3,4];
    console.log(arrs.reverse()); //[4,3,2,1]

####6.shift()

该方法用于把数组的第一个元素从其中删除，并返回被删除的值。如果数组是空的，shift方法将不进行任何操作，返回undefined的值。

如下代码演示：


    var arrs = [1,2,3,4];
    console.log(arrs.shift());// 1
    console.log(arrs); // [2,3,4]

    var arrs2 = [];
    console.log(arrs2.shift()); // undefined
    console.log(arrs2); // []



####7.sort()

1. 该方法是对数组的元素进行排序；sortby参数规定排序顺序，且必须是函数。

如果该方法没有使用参数，则是按字母的字符编码的顺序进行排序。

2. 如果想按其他标准进行排序，就需要提供比较函数，该函数比较2个值，然后返回一个用于说明这2个值的相对顺序的数字，比如比较a与b，返回值如下：

  若a小于b，在排序后的数组中a应该出现在b之前，则返回一个小于0的值。

  若a等于b，在排序后的数组中 a等于b 则返回0；

  若a大于b，则返回一个大于0的值；

比如如下代码演示：


    var arrs = ["tugenhua","longen","alibaba"];
    console.log(arrs.sort());   // ["alibaba", "longen", "tugenhua"]

    var arrs2 = ["15","5","8","12"];
    console.log(arrs2.sort(function(a,b){
        return a - b;  // ["5", "8", "12", "15"]
    }));



####8.splice()

该方法用于插入，删除和替换数组的元素；

基本语法如下：

`Array.splice(index,howmany,element1,.....elementX)`;

Index参数：【必填】是从何处添加/删除元素，该参数是开始插入或删除数组元素的下标，必须是数字；

Howmany: 【必须】应该删除多少个元素，必须是数字，也可以是0，如果未设定该参数，则删除从index开始到原数组结尾的所有元素；

Element1: 【可选】规定要添加到数组的新元素，从index所指的下标处开始插入；

ElementX: 【可选】 可向数组中添加若干个元素；

如下代码演示：


    // 假如原数组如下
    var arrs = [1,2,3,4,5,6];
    // 先向数组的第二个位置中添加一个元素8；
    arrs.splice(1,0,8);
    console.log(arrs); // [1, 8, 2, 3, 4, 5, 6]

    // 接着从arrs数组中删除一个元素2
    arrs.splice(2,1);
    console.log(arrs); // [1, 8, 3, 4, 5, 6]

    // 再接着从arrs数组中替换一个元素8 使他变为10;如下代码：
    arrs.splice(1,1,10);
    console.log(arrs); // [1, 10, 3, 4, 5, 6]



####9.toString()

将数组转换为一个字符串，并且返回这个字符串；如下代码演示：

    var arrs = [1,2];
    console.log(arrs.toString()); // 1,2

####10.unshift()

该方法是向数组的开头添加一个或者更多元素，并返回新的长度。

如下代码演示：

    var arrs = [1,2];
    arrs.unshift(3); 
    console.log(arrs); //[3, 1, 2]

####11.slice()

该方法是从已有的数组中返回指定的元素。

基本语法：arrs.slice(start,end);

start参数【必须】从何处开始选取(包括start)，如果是负数，那么会从尾部选取，比如-1代表最后一个元素，-2代表倒数第二个元素，以此类推。

End参数【可选】规定是从何处结束选取(不包括end)，如果没有指定该参数，那么数组会包含从start开始到数组结束的所有元素，如果该参数是负数的话，那么它规定的是从数组尾部开始算起的元素。

如下演示：


    var arrs2 = [1,2,3];
    console.log(arrs2.slice(1)); // [2,3]
    console.log(arrs2.slice(0,1));// [1]
    console.log(arrs2.slice(1,-1)); // [2]
    console.log(arrs2.slice(2,-1)); // []
    console.log(arrs2.slice(0));  // [1,2,3]




##判断一个数组中是否有相同的元素


    /*
     * 判断数组中是否有相同的元素的代码
     */
     // 方案一
     function isRepeat1(arrs) {
        if(arrs.length > 0) {
            var s = arrs.join(","); 
            for(var i = 0,ilen = arrs.length; i < ilen; i+=1) {
                if(s.replace(arrs[i],"").indexOf(arrs[i])>-1) {
                    return true;
                }
            }
        }
        return false;
     }
     
     // 方案二
     function isRepeat2(arrs) {
        var hash = {};
        if(arrs.length > 0){
            for(var i = 0,ilen = arrs.length; i < ilen; i+=1) {
                if(hash[arrs[i]]) {
                    return true;
                }
                hash[arrs[i]] = true;
            }
        }
        return false;
     }
     var arrs = [1,4,3,2,5];
     console.log(isRepeat1(arrs)); // false

     var arrs2 = [1,2,3,1];
     console.log(isRepeat1(arrs2)); // true


     var arrs = [1,4,3,2,5];
     console.log(isRepeat2(arrs)); // false

     var arrs2 = [1,2,3,1];
     console.log(isRepeat2(arrs2)); // true




##计算一个数组中每个元素在数组中出现的次数；

代码如下：


    /*
     * 计算数组中每个元素在数组中出现的个数
     * @param {arrs} 数组
     * @method 定义一个新数组，循环当前的数组，使用一个临时的变量temp保存当前的值，外层for循环定义一次变量count=0，当做计数器，内部再一次循环数组判断当前的数组与外层的数组某一项是否相等，如是count++; 然后把当前的一项值置为-1，下一次就不会再继续循环了
     * @return {newArrs} 返回一个新数组
     */
    function arrayElemCount(arrs){
        var newArrs = [];
         if(arrs.length > 0) {
            for(var i = 0,ilen = arrs.length; i < ilen; i+=1) {
                var temp = arrs[i];
                var count = 0;
                for(var j = 0,jlen = arrs.length; j < jlen; j+=1) {
                    if(arrs[j] == temp) {
                        count++;
                        arrs[j] = -1;
                     }
                }
                newArrs.push(temp + ":" +count);
            }
         }
         return newArrs;
    }
    var arrs = [1,2,1,2,3,4,5,6,7,1,2,3];
    console.log(arrayElemCount(arrs)); 
    // 打印如下：["1:3", "2:3", "-1:6", "-1:6", "3:2", "4:1", "5:1", "6:1", "7:1", "-1:12", "-1:12", "-1:12"]
    // 键值为-1的，都可以去掉




##Javascript删除数组重复元素的操作

####1. 方案一

遍历数组使用indexOf方法，代码如下：


    /*
     * javascript数组去重方案一
     * @param {arrs} 原数组
     * @method 新建一个新数组，遍历原数组，在新数组内使用indexOf查找原数组内的每一项，如果没有找到，就把当前的项存入新数组里面去，这样就过滤掉
     * 重复项 indexOf方法在IE8及IE8以下不支持，因此有必要封装一个
     * @return {newArrays} 返回新数组
     */
    function arrayUnique(arrs) {
        var newArrays = [];
        for(var i = 0,ilen = arrs.length; i < ilen; i++) {
            if(newArrays.indexOf) {
                if(newArrays.indexOf(arrs[i]) == -1) {
                    newArrays.push(arrs[i]);
                }
            }else {
                if(indexOf(arrs[i],newArrays) == -1) {
                    newArrays.push(arrs[i]);
                }
            }
            
        }
        return newArrays;
    }
    /*
     * 为了支持IE8及以下浏览器需要封装一个indexOf方法
     * @param {arr,arrs} 某一项 原数组
     * @return 返回数组某一项
     */
     function indexOf(arr,arrs){
        if(arrs.length > 0) {
            for(var i = 0,ilen = arrs.length; i < ilen; i+=1) {
                if(arrs[i] == arr) {
                    return i;
                }
            }
        }
        return -1;
     }
    var arrs = [1,2,3,1,2,3];
    console.log(arrayUnique(arrs)); // [1,2,3]



####2. 方案二：

数组下标判断法；


    /*
     * 数组下标判断法
     * 思路：先定义一个新数组，循环当前数组，使用indexOf方法，如果在当前的数组的第i项在当前数组中的位置是i项的话，说明该项在数组中并未出现过，存入新数组，否则的话，在原数组中出现过，因此需要过滤掉。性能和第一种方案差不多。
     * @return {newArrars} 返回新数组
     */
    function arrayUnique(arrs) {
        var newArrays = [];
        if(arrs.length > 0) {
            for(var i = 0,ilen = arrs.length; i < ilen; i+=1) {
                if(arrs.indexOf) {
                    if(arrs.indexOf(arrs[i]) == i) {
                        newArrays.push(arrs[i]);
                    }
                }else {
                    if(indexOf(arrs[i],arrs) == i) {
                        newArrays.push(arrs[i]);
                    }
                }
                
            }
        }
        return newArrays;
    }
    /*
     * 为了支持IE8及以下浏览器需要封装一个indexOf方法
     * @param {arr,arrs} 某一项 原数组
     * @return 返回数组某一项
     */
     function indexOf(arr,arrs){
        if(arrs.length > 0) {
            for(var i = 0,ilen = arrs.length; i < ilen; i+=1) {
                if(arrs[i] == arr) {
                    return i;
                }
            }
        }
        return -1;
     }
    var arrs = [1,2,1,3,1];
    console.log(arrayUnique(arrs)); // [1,2,3]



####3. 方案三：

排序后相邻去除法


    /*
     * 排序后相邻去除法
     * @method 新建一个新数组，遍历当前的数组，如果当前的数组某一项不等于新数组的最后一项的话，就把当前的项存入新数组中，最后返回新数组
     */
    function arrayUnique(arrs) {
        var newArrays = [];
        if(arrs.length > 0) {
            arrs.sort();
            for(var i = 0,ilen = arrs.length; i < ilen; i+=1) {
                if(arrs[i] !== newArrays[newArrays.length - 1]) {
                    newArrays.push(arrs[i]);
                }
            }
        }
        return newArrays;
    }
    var arrs = [1,2,1,3,1];
    console.log(arrayUnique(arrs)); // [1,2,3]



####4. 方案四：

对象键值对法

代码如下：


    /*
     * 对象键值法(该方法性能最优)
     * @method 定义一个空对象和空新数组，遍历当前的数组，判断该对象是否存在数组的某一项，如果不存在
     * 就当当前的某一项存入新数组去，且当前的项置为-1 目的过滤掉重复的项
     */
    function arrayUnique(arrs) {
        var newArrays = [];
        var hash = {};
        if(arrs.length > 0) {
            for(var i = 0,ilen = arrs.length; i < ilen; i+=1) {
                if(!hash[arrs[i]]) {
                    hash[arrs[i]] = 1;
                    newArrays.push(arrs[i]);
                }
            }
        }
        return newArrays;
    }
    var arrs = [4,5,2,1,2,1,3,1];
    console.log(arrayUnique(arrs)); // [4,5,2,1,3]




##Javascript删除数组里面的某个元素。

####方案一：

使用indexOf和splice()方法删除某个元素；

代码如下：


    /*
     * 为了支持IE8及以下浏览器需要封装一个indexOf方法
     * @param {arr,arrs} 某一项 原数组
     * @return 返回数组某一项
     */
     function indexOf(arr,arrs){
        if(arrs.length > 0) {
            for(var i = 0,ilen = arrs.length; i < ilen; i+=1) {
                if(arrs[i] == arr) {
                    return i;
                }
            }
        }
        return -1;
     }
     /*
      * 删除数组里面的某个元素
      * @param {elem,arrs} 要删除的元素 原数组
      * 思路：先使用indexOf方法在数组里面找到该元素的位置，然后使用splice()方法删除一个元素
      * @return {elem,arrs} 返回一个对象，对象有2个元素，第一个是被删除的元素elem键，另一个是被删除元素
      后的数组，也就是新数组 [2,3]
      */
     function removeAttrsElem(elem,arrs){
        var newElem;
        if(arrs.length > 0) {
            var index = indexOf(elem,arrs);
            if(index > -1) {
                newElem = arrs.splice(index,1);
            }
        }
        return {
            elem: newElem,
            arrs: arrs
        }
     }
     var arrs = [1,2,3];
     var elem = 1;
     console.log(removeAttrsElem(elem,arrs)); 
     // 返回一个对象 {elem:1,arrs:[2,3]}



####方案二：

直接遍历数组 取其中某一项 如果某一项与该元素相同的话，直接截取，和第一种方案类似，比第一种方案简单


    /*
      * 删除数组里面的某个元素
      * @param {elem,arrs} 要删除的元素 原数组
      * 思路：直接遍历数组 取其中某一项 如果某一项与该元素相同的话，直接截取，和第一种方案类似，比第一种方案简单
      * @return {elem,arrs} 返回一个对象，对象有2个元素，第一个是被删除的元素elem键，另一个是被删除元素
      后的数组，也就是新数组 [2,3]
      */
     function removeAttrsElem(elem,arrs){
        var newElem;
        if(arrs.length > 0) {
            for(var i =0,ilen = arrs.length; i < ilen; i+=1) {
                if(arrs[i] == elem) {
                    newElem = arrs.splice(i,1);
                }
            }
        }
        return {
            elem: newElem,
            arrs: arrs
        }
     }
     var arrs = [1,2,3];
     var elem = 1;
     console.log(removeAttrsElem(elem,arrs)); 
     // 返回一个对象 {elem:1,arrs:[2,3]}




##在javascript中求出2个数组的相同的元素及不同的元素

思路：先定义一个对象，把A数组转换成对象，然后遍历B数组，判断B数组中某一项是否在A数组那个对象里面 如果在的话，说明B数组与A数组有相同的元素，否则B数组和A数组有不同的元素有哪些；

代码如下：


    /* 
      * 求出2个数组的相同的元素和不同的元素
      * 思路：先定义一个对象，把A数组转换成对象，然后遍历B数组，判断B数组中某一项是否在
      * A数组那个对象里面 如果在的话，说明有相同的元素，否则为不同的元素
      */
    function getArrsSameAndDiffElem(arrs1,arrs2){
        var hash = {},
            sameElemArrs = [],
            diffElemArrs = [];
        if(arrs1.length > 0) {
            for(var i = 0,ilen = arrs1.length; i < ilen;i+=1) {
                hash[arrs1[i]] = 1;
            }
        }
        if(arrs2.length > 0) {
            for(var j = 0,jlen = arrs2.length; j < jlen; j+=1) {
                if(hash[arrs2[j]]) {
                // 说明有相同的元素，把相同的元素存入sameElemArrs数组里面去
                    sameElemArrs.push(arrs2[j]);
                }else {
                // 说明是不同的元素，把不同的元素存入diffElemArrs数组里面去
                    diffElemArrs.push(arrs2[j]);
                }
            }
        }
        return {
            sameElemArrs: sameElemArrs,
            diffElemArrs: diffElemArrs
        }
    }
     var arrs1 = ["aac","aab","cfg",'longen','tugenhua','single'];
     var arrs2 = ["aac","mnc","nba","cba","anta",'tugenhua','single'];
     console.log(getArrsSameAndDiffElem(arrs1,arrs2));
     // 打印出 diffElemArrs = ["mnc","nba","cba","anta"]
     // 相同的元素 sameElemArrs = ["aac",'tugenhua','single']



如上可以看到 arrs2中与arr1中数组有相同的元素如上，不同的元素也如上；

如果需要判断arr1中与arr2中数组相同元素及不同的元素，传递参数调换位置即可！


##Javascript检测2个数组是否相似

判断2个数组是否相似的条件：

* 先判断这两个对象是否为Array的实例。
* 接着判断该数组的长度是否一致。

判断该2个对象的类型是否一样，先对这2个数组先转换为字符串后，再进行排序比较，如果该2个对象类型的个数一致，长度一致，且都是数组，说明该2个数组是相似的；比如如下：  

    var arr11 = [11,true];
    var arr22 = [false,22];

如上2个数组是相似的，但是如果2个数组如下这样的话

    var arr11 = [11,true];
    var arr22 = [false,true];

说明2个数组不相似了~ 代码如下：


    function arraysSimilar(arr1,arr2) {
        if(!(arr1 instanceof Array) || !(arr2 instanceof Array)) {
            return false;
        }
        if(arr1.length !== arr2.length) {
            return false;
        }
        var arrsLen = arr1.length;
        var tempArrs1 = [],
            tempArrs2 = [];
        for(var i = 0; i < arrsLen; i+=1) {
            var t1 = Object.prototype.toString.apply(arr1[i]);
            tempArrs1.push(t1);
            var t2 = Object.prototype.toString.apply(arr2[i]);
            tempArrs2.push(t2);
        }
        return tempArrs1.sort().join() === tempArrs2.sort().join() ? true : false;
     }
     var arr1 = ["aa","cc",false,"bb"];
     var arr2 = ["11","cc","11",false];
     console.log(arraysSimilar(arr1,arr2)); // true

     var arr11 = [11,true];
     var arr22 = [false,22];
     console.log(arraysSimilar(arr11,arr22)); // true




##如何判断该对象是否为数组。

####1. typeof

  首先我们会想到的是使用typeof来检测数据类型，但是对于Function, String, Number, Undefined等这几种基本类型来说，使用typeof来检测都可以检测到，比如代码如下：

    function test(){}
    console.log(typeof 1); // number
    console.log(typeof test); // function 
    console.log(typeof "yunxi"); // string
    console.log(typeof undefined); // undefined

但是对于数组或者正则来说，使用typeof来检测的话，那就满足不了，因为当我们检测数组或者正则的话，那么返回的类型将会是一个对象object，如下代码所示：

    console.log(typeof []);  // object
    console.log(typeof /\d+/g); // object

####2. Instanceof

由此我们很容易会想到使用instanceof来检测某个对象是否是数组的实例，该检测会返回一个布尔型(boolean),如果是数组的话，返回true，否则的话返回false；我们再来看下上面的检测是否为数组的代码如下：

    console.log([] instanceof Array);  // true
    console.log(/\d+/g instanceof Array); // false

如上可以看到使用instanceof确实可以判断是否为数组的列子;

####3. constructor属性

在javascript中，每个对象都有一个constructor属性，它引用了初始化该对象的构造函数，比如判断未知对象的类型，因此我们可以如下写一个方法：代码如下：


    function isArray(obj) {
        return typeof obj == 'object' && obj.constructor == Array
    }
    // 测试demo
    console.log(isArray([])); // true
    var a = {"a":1};
    console.log(isArray(a)); // false

    var b = [1,2,3];
    console.log(isArray(b)); // true
    console.log(isArray(/\d+/g));// false



如上可以看到，通过调用isArray 方法也可以判断是否为数组的列子。

我们现在可以看到，对于第二点和第三点分别使用instanceof方法和constructor属性貌似都可以来判断是否为数组了，但是也有列外情况，比如在跨框架iframe的时候使用页面中的数组时，会失败，因为在不同的框架iframe中，创建的数组是不会相互共享其prototype属性的；如下代码测试即可得到验证~


    var iframe = document.createElement('iframe');
    document.body.appendChild(iframe);
    xArray = window.frames[window.frames.length-1].Array;       
    var arr = new xArray("1","2","3","4","5");
    //这个写法IE下是不支持的，标准浏览器firefox，chrome下有

    console.log(arr);  // 打印出 ["1", "2", "3", "4", "5"]
    console.log(arr instanceof Array); // false 
    console.log(arr.constructor === Array); // false



如上的方法我们都不能来判断一个对象是否为数组的方式; 但是我们在看ECMA262中可以看到，可以使用 Object.prototype.toString.call()方法来判断一个对象是否为数组；如下代码：


    function isArray(obj) {
        return Object.prototype.toString.call(obj) == '[object Array]';
    }
    // 代码调用
    console.log(isArray([]));  // true
    console.log(isArray([1,2,3])); // true

    var iframe = document.createElement('iframe');
    document.body.appendChild(iframe);
    xArray = window.frames[window.frames.length-1].Array;       
    var arr = new xArray("1","2","3","4","5");

    console.log(arr); // ["1","2","3","4","5"]
    console.log(isArray(arr));  // true




##js将类数组对象转换成数组对象

首先我们来看一下类数组，什么是类数组，类数组有什么特征呢？

具有：有指向对象的数字索引 及 length属性值；

不具有：它不具有数组的方法，比如push，slice，pop等方法；

Javascript中常见的类数组有arguments, HTMLCollection的集合(比如document.getElementsByClassName,document.getElementsByTagName)等方法，常见的类数组对象有如下：

document.getElementsByClassName, document.getElementsByTagName,document.getElementsByName,arguments等等；比如如下测试代码：类数组可以有length属性，可以遍历，但是它并不是数组的实例，如下代码：


    function elems(){
        for(var i = 0, ilen = arguments.length; i < ilen; i+=1) {
            console.log(arguments[i]); // 循环2次 打印出 1,2
            
        }
        console.log(arguments instanceof Array);// false
    }
    elems(1,2);



我们再来测试下arguments是否和数组一样有push方法；测试代码如下：

    function test(){
        console.log(arguments.push(1)); //arguments.push is not a function
    }
    test();

在控制台中打印出 `arguments.push is not a function` 报错，说明类数组并不是一个真正的数组，因为它没有数组的方法；

但是我们可以将类数组转换为数组，我们可以使用slice()方法call对象；slice()方法可以将一个类数组对象/集合转换成一个数组，只需要使用数组原型上的slice方法call这个对象，即Array.prototype.slice.call(arguments);即可将类数组转换为数组，或者我们也可以使用[].slice.call(arguments);来转换数组；

如下代码：


    function test(){
        //var args = [].slice.call(arguments);
        var args = Array.prototype.slice.call(arguments);
        console.log(args.push(1)); //1
    }
    test();



使用上面的 `[].slice.call()`方法和 `Array.prototype.slice.call()`方法都可以将类数组转换为数组的，比如上面的`args`就是转换后的数组，其后就拥有push()方法；

当然如果我们不嫌麻烦的话，我们可以先在函数内部定义一个新数组，然后使用`arguments.length`的属性遍历每一项，把每一项存入到新数组里面去也是可以的，但是这样做并没有上面的好；如下代码：


    function elems(){
        var newArrs = [];
        for(var i = 0, ilen = arguments.length; i < ilen; i+=1) {
            newArrs[i] = arguments[i];
        }
        console.log(newArrs); // [1,2]
    }
    elems(1,2);




##查找数组中最大值与最小值

最小值算法如下：

* 将数组中第一个元素赋值给一个变量，把这个变量作为最小值；
* 开始遍历数组，从第二个元素开始依次和第一个元素进行比较。
* 如果当前的元素小于当前的最小值的话，就把当前的元素值赋值给最小值；
* 移动到下一个元素，继续对第三步操作；
* 当数组元素遍历结束时，这个变量存储的就是最小值；

代码如下：


    // 查找数组中最小值
    function arrayMin(arrs){
        var min = arrs[0];
        for(var i = 1, ilen = arrs.length; i < ilen; i+=1) {
            if(arrs[i] < min) {
                min = arrs[i];
            }
        }
        return min;
    }
    // 代码测试
    var rets = [2,4,5,6,7,9,10,15];
    console.log(arrayMin(rets));//2



上面是对数组中的数值进行比较的，如果数组中的数字是字符串的话，先要把字符串转换成数字再进行比较即可，因为字符串比较的不是值，而是ASCII编码，比如2的ASCLL编码会大于15的ASCII编码，因为15的编码第一个数字是1,2的ASCII编码肯定大于1的；

求最大值的算法和上面类似：

* 将数组中第一个元素赋值给一个变量，把这个变量作为最大值；
* 开始遍历数组，从第二个元素开始依次和第一个元素进行比较。
* 如果当前的元素大于当前的最大值的话，就把当前的元素值赋值给最大值；
* 移动到下一个元素，继续对第三步操作；
* 当数组元素遍历结束时，这个变量存储的就是最小值；

代码如下：

    // 在数组中查找最大值
    function arrayMax(arrs) {
        var max = arrs[0];
        for(var i = 1,ilen = arrs.length; i < ilen; i++) {
            if(arrs[i] > max) {
                max = arrs[i];
            }
        }
        return max;
    }
    // 代码测试
    var rets = [2,4,5,6,7,9,10,15];
    console.log(arrayMax(rets));//15

> 原文作者：[涂根华](http://www.cnblogs.com/tugenhua0707/p/5052808.html)

> 原文地址：[javascript数组的知识点讲解](http://www.cnblogs.com/tugenhua0707/p/5052808.html)