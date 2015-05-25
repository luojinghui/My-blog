#解析Lodash中对Array数组的15个用法

Lodash是一个JavaScript库，也是Node JS的常用模块，Lodash侧重于基础类型的操作，比如数组，对象，字符串，函数。它可以提供一致性，可以模块化，可以更高效。在学习了一天多之后，大概可以理解它这句话的意思。现在，通过此博客，解析几个对于数组的操作：

1、_.chunk(array, [size=1])

实现思路：将一个数组元素按照指定的长度进行分割元素，类似对数组进行排队，最后return返回一个排好队的数组元素的集和。

array：要处理的数组元素；

[size=1]：要指定分割的长度；

例如：

? 1 2 3 4 5_.chunk(['a', 'b', 'c', 'd'], 2);

// → \[['a', 'b'], ['c', 'd']]

_.chunk(['a', 'b', 'c', 'd'], 3);

// → \[['a', 'b', 'c'], ['d']]

2、_.compact(array)

实现思路：将一个数组元素中包含有false, null, 0, " ", undefined（为定义）, and NaN（不是数字）的元素进行移除，并return返回一个过滤后的新数组。

array：要处理的数组元素；

例如：

? 1 2_.compact([0, 1, false, 2, '', 3]);

// → [1, 2, 3]

3、_.difference(array, [values])

实现思路：给定一组判定元素，若是原数组中出现相同的元素，将原数组中的元素移除，所有元素判断完毕后，return返回一个过滤后的新数组。

array：要处理的原数组集和；

[values]：判定将要移除元素的集和；

例如：

? 1 2_.difference([1, 2, 3], [4, 2]);

// → [1, 3]

4、 _.drop(array, [n=1])

实现思路：给定一个数组位置，将其从开始位置进行删除直到给定的位置，若是指定位置为0，则不会删除任何元素，若之未指定位置，则默认值是1，若是指定位置数字大于数组元素的长度，则会删除所有数组中的元素，最后return返回一个过滤后的新数组；

array：要处理的数组元素;

[n=1]：给出想要删除元素的位置；

例如：

? 1 2 3 4 5 6 7 8 9 10 11_.drop([1, 2, 3]);

// → [2, 3]

_.drop([1, 2, 3], 2);

// → [3]

_.drop([1, 2, 3], 5);

// → []

_.drop([1, 2, 3], 0);

// → [1, 2, 3]

5、_.dropRight(array, [n=1])

实现思路：同4方法，只是删除位置从右边开始。

例如：

? 1 2 3 4 5 6 7 8 9 10 11_.dropRight([1, 2, 3]);

// → [1, 2]

_.dropRight([1, 2, 3], 2);

// → [1]

_.dropRight([1, 2, 3], 5);

// → []

_.dropRight([1, 2, 3], 0);

// → [1, 2, 3]

6、_.fill(array, value, [start=0], [end=array.length])

实现思路：替换给定位置的元素，默认是0，从起始位置开始，到数组的长度结束，之后return返回一个新的数组。

array：要替换的数组集和；

value：必填选项，要替换的元素；

[start=0]：起始位置，默认从0开始。

[end=array.length]：结束位置，默认是数组的长度；

例如：

? 1 2 3 4 5 6 7 8 9 10 var array = [1, 2, 3];_.fill(array, 'a'); console.log(array);

// => ['a', 'a', 'a']

_.fill(Array(3), 2);

// => [2, 2, 2]

_.fill([4, 6, 8], '*', 1, 2);

// => [4, '*', 8]

7、_.flatten(array, [isDeep])

实现思路：将一个带有递归的数组元素放置于一个一层数组中，并return返回一个新的数组。

array：带有递归的数组元素；

[isDeep]：默认是false，当设置为true时，将所有元素进行消除递归；

例如：

? 1 2 3 4 5 6_.flatten([1, [2, 3, [4]]]);

// => [1, 2, 3, [4]]

// using `isDeep`_.flatten([1, [2, 3, [4]]], true);

// => [1, 2, 3, 4]

8、_.indexOf(array, value, [fromIndex=0])

实现思路：返回根据给定元素找到的第一个索引值，否则返回-1。

array：给定的数组；

value：要搜索的值；

[fromIndex=0](boolean|number)：通过二进制去进行搜索相应的值；

例如：

? 1 2 3 4 5 6 7 8 9 10_.indexOf([1, 2, 1, 2], 2);

// => 1

// using `fromIndex`_.indexOf([1, 2, 1, 2], 2, 2);

// => 3

// performing a binary search_.indexOf([1, 1, 2, 2], 2, true); // => 2

9、 _.initial(array)

实现思路：将数组最后一个元素忽略，然后重新返回该数组；

array：给定的数组；

例如：

? 1 2_.initial([1, 2, 3, 4 , 5, 7, 6, 8]);

// =>[1, 2, 3, 4, 5, 7, 6]

10、_.intersection([arrays])

实现思路:在一个含有多个数组的array中,返回数组中含有的相同元素.

arrays:需要检查的数组.

例如:

? 1 2_.intersection([1, 2], [4, 2], [2, 1]);

// => [2]

11、 _.pull(array, [values])

实现思路：移除给定元素的值，返回一个新的数组；

array：要移除的数组；

[values]：要移除的元素；

例如：

? 1 2 3 4 var array = [1, 2, 3, 1, 2, 3];_.pull(array, 2, 3); console.log(array);

// => [1, 1]

12、 _.pullAt(array, [indexes])

实现思路：给定数组中的一个或者多个元素的位置，返回一个此位置上的数据元素；

array：数组元素；

[indexes](...(number|number[])：要显示的元素的位置；

例如：

? 1 2 3 4 5 6 7 var array = [5, 10, 15, 20]; var evens = _.pullAt(array, 1, 3); console.log(array);

// => [5, 15]

console.log(evens);

// => [10, 20]

13、 *.remove(array, [predicate=*.identity], [thisArg])

实现思路：按照某种条件去除一个数组中不想要的元素；

array：要修改的元素数组；

[predicate=_.identity] (Function|Object|string）：条件可以是函数，对象，或者字符串；

例如：

? 1 2 3 4 5 6 7 8 9 var array = [1, 2, 3, 4]; var evens = _.remove(array, function(n) { return n % 2 == 0; }); console.log(array);

// => [1, 3]

console.log(evens);

// => [2, 4]

14、 _.take(array, [n=1])

实现思路：从指定的一个位置截取前面的数据元素；

array：数组；

[n=1](number)：默认是1，指定位置的数字元素；

例如：

? 1 2 3 4 5 6 7 8*.take([1, 2, 3]);

// => [1]*.take([1, 2, 3], 2);

// => [1, 2]*.take([1, 2, 3], 5);

// => [1, 2, 3]*.take([1, 2, 3], 0);

// => []

15、 _.slice(array, [start=0], [end=array.length])

实现思路：将一个数组按照起始位置和终止位置的前一位进行截取。

array：数组元素；

[start=0](number)：截取的起始位置；

[end=array.length](number)：截取的位置；

例如：

? 1 2_.slice([1,2,3,4,5],2,5)

// =>[3, 4, 5]
