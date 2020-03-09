---
layout: post
title:  "Sorting data structures in Python and C#"
date:   2020-02-19 12:01:43 +0800
categories: Arrays C# Python
---
In this post, we are going to discuss diferent ways of sorting arrays in C# and Python.
You'll find links to the examples to an online IDE container (repl.it)

# Python

The `sorted()` built-in method sorts any sequence (list, tuple, string, etc) and **always** returns a
`list` with the elements in sorted manner, without modifying the original sequence.

Example:

{% highlight python %}
# List
a = [5,2,3,1,4]
print(sorted(a))
# Output: [1,2,3,4,5]

# Tuple
a = (5,2,3,1,4)
print(sorted(a))
# Output: [1,2,3,4,5]

# Dictionary
a = {5:1, 2:2, 3:3, 1:4, 4:5}
print(sorted(a))
# Output: [1,2,3,4,5]

# String
a = '52314'
print(sorted(a))
# Output: [1,2,3,4,5]

{% endhighlight %}

Another way to sort a list of elements is using the `sort()` method. This mehtod only works for
list data structures and it modifies the original list.

Example: 

{% highlight python %}
# List
a = [5,2,3,1,4]
a.sort()
print(a)
#Output: [1,2,3,4,5]

{% endhighlight %}


The NumPy library provides you with an array data structure that holds some benefits over
Python lists, such as: being more compact, faster access in reading and writing items, being more convenient and more efficient.

The NumPy module has a `sort()` method.

Example:

{% highlight python %}
import numpy as np

a = np.array([5,2,3,1,4])
print(np.sort(a))

#Output: [1 2 3 4 5]
{% endhighlight %}



# C#

## Sort a list of integers
In this example, we will use the `List<T>.Sort` Method.

It sorts the elements or a portion of the elements in the `List<T>` using either the specified or default `IComparer<T>` implementation or a provided `Comparison<T>` delegate to compare list elements.

Example:

{% highlight C#  %}

using System;
using System.Collections.Generic;

namespace array_sorting
{
    class Program
    {
        static void Main(string[] args)
        {
            var unsorted_list = new List<int> { 5, 2, 3, 1, 4 };
            var sorted_list = new List<int>();

            sorted_list = new List<int>(unsorted_list); // make a copy first if you need to
            sorted_list.Sort();


            foreach (int i in unsorted_list)
            {
                Console.Write(i);
            }

            Console.Write("\n");


            foreach (int i in sorted_list)
            {
                Console.Write(i);
            }

        }
    }
}

// Output: 
// 52314
// 12345

{% endhighlight  %}

## Sorting an Array of integers
The `Sort(Array)` method sorts the elements in an entire one-dimensional `Array` using 
the `IComparable` implementation of each element of the `Array`.

In the following example, we are sorting the values in an `Array` using the default comparer.


{% highlight c#  %}

using System;

namespace array_sorting
{
    class Program
    {
        static void Main(string[] args)
        {

            int[] unsorted_array = {5, 2, 3, 1, 4};
            var sorted_array = new int[5];

            Array.Copy(unsorted_array, sorted_array, unsorted_array.Length);
            Array.Sort(sorted_array);

            foreach (int i in unsorted_array)
            {
                Console.Write(i);
            }

            Console.Write("\n");

            foreach (int i in sorted_array)
            {
                Console.Write(i);
            }

        }
    }
}

// Output:
// 52314
// 12345


{% endhighlight  %}
