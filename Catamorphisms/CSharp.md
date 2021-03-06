**Catamorphisms in C#**

Catamorphisms apply a mapping function f to items in a list of data.  

1.  One method of emulating the map() function in C# uses generators

```
public List<int> map(List<int> list, Func<T, U> f)
for(var i=0; i<list.count; i++)
{
    yield f(list[i]);
}

```
This code probably does not work but its there if you need it.

2.  The best way to implement map() in C# is through LINQ using the select operator

```
Func<int, int> add = x => x + 1;

var list 2 = list.select(add) 

```

3. Mappable data in C# 

Instead of a loop with statements inside, map iterates over the data and applies its callback function to each item.


Sound familiar?  like perhaps...IEnumerable?


```
Let's start with a collection

List<int> mylist = new List<int>();
mylist.Add(1);
mylist.Add(2);
mylist.Add(3);

var mylist2 = mylist.select(add);

foreach(var item in mylist2)
{
    console.log(item);
}

```

The result is a new list, mylist2, with elements: 2, 3,4.  The map code is much more compact than a for loop.

4.  Replace the mylist.Add calls with insert

