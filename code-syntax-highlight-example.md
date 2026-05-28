---
---
<!-- bundle exec jekyll serve -->
# Syntax highlighting
This theme supports syntax respectively code highlighting. Below you find some examples of different programming languages.

go
{% highlight go%}
package main

import (
	"fmt"
	"math"
)

// 1. Define the interface (the "contract")
type Shape interface {
	Area() float64
}

// 2. Define a struct
type Rectangle struct {
	Width, Height float64
}

// 3. Implement the interface method for Rectangle
func (r Rectangle) Area() float64 {
	return r.Width * r.Height
}

// 4. Define another struct
type Circle struct {
	Radius float64
}

// 5. Implement the same interface method for Circle
func (c Circle) Area() float64 {
	return math.Pi * c.Radius * c.Radius
}

// A function that accepts any type that satisfies the Shape interface
func printArea(s Shape) {
	fmt.Printf("Area: %.2f\n", s.Area())
}

func main() {
	r := Rectangle{Width: 10, Height: 5}
	c := Circle{Radius: 7}

	// Both structs can be passed to the same function
	printArea(r)
	printArea(c)
}

{% endhighlight %}

<br />ruby:
{% highlight ruby %}
def foo
  puts 'foo'
end

def bubble_sort(list)
  return list if list.size <= 1 # already sorted
  swapped = true
  while swapped do
    swapped = false
    0.upto(list.size-2) do |i|
      if list[i] > list[i+1]
        list[i], list[i+1] = list[i+1], list[i] # swap values
        swapped = true
      end
    end
  end

  list
end
{% endhighlight %}


<br /><br />python:
{% highlight python %}
def func():
     # function body
     print("hello world!")

     def setup(app):
         # enable Pygments json lexer
         try:
             import pygments
             if pygments.__version__ >= '1.5':
                 # use JSON lexer included in recent versions of Pygments
                 from pygments.lexers import JsonLexer
             else:
                 # use JSON lexer from pygments-json if installed
                 from pygson.json_lexer import JSONLexer as JsonLexer
         except ImportError:
             pass  # not fatal if we have old (or no) Pygments and no pygments-json
         else:
             app.add_lexer('json', JsonLexer())

         return {"parallel_read_safe": True}

words = ['cat', 'window', 'defenestrate']
for w in words:
   print w, len(w)
{% endhighlight %}


<br /><br />php:
{% highlight php %}
<?php function add($x, $y) {
    $total = $x + $y;
    return $total;
}
echo "1 + 16 = " . add(1, 16);
?>
{% endhighlight %}


<br /><br />js:
{% highlight javascript %}
function sayHello(name) {
  if (!name) {
    console.log('Hello World');
  } else {
    console.log(`Hello ${name}`);
  }  
}  

function myFunc(a, b) {
    return a * b;
}
document.getElementById('demo').innerHTML = myFunc(4, 3);
{% endhighlight %}


<br /><br />java:
{% highlight java %}
class HelloWorldApp {
    public static void main(String[] args) {
        System.out.println("Hello World!");
    }
}
{% endhighlight %}


<br />objective c:
{% highlight objective_c %}
- (int)method:(int)i {
    return [self square_root:i];
}
{% endhighlight %}


<br /><br />perl:
{% highlight perl %}
while (<>) {
    chomp;
    if (s/$//) {
        $_ .= <>;
        redo unless eof();
    }
}
{% endhighlight %}


<br /><br />sql:
{% highlight sql %}
SELECT Country FROM Customers WHERE Country <> 'USA'
{% endhighlight %}


<br /><br />c++:
{% highlight c++ %}
#include
using namespace std;
int main () {
  cout << "Hello World!";
  return 0;
}
{% endhighlight %}


<br /><br />c sharp:
{% highlight c# %}
class Foo {
    public int Value;
    public static explicit operator Foo(int value) {
        return new Foo(value);
    }
}
Foo foo = (Foo)2;
{% endhighlight %}


<br /><br />vb:
{% highlight vb linenos %}
Private Sub Form_Load()
    MsgBox "Hello, World!"
End Sub
{% endhighlight %}