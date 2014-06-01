---
published: true
title: Ruby Blocks, Lambdas and Procs
layout: post
---
This is going to be a continued series of posts on Ruby (and Rails). Coming from a Python background, Ruby is pretty neat. But imo, blocks lambdas and procs are possibly the neatest things in the language so far. They've taken functional programming a bit further with code blocks as objects. While interesting, I think it's kind of like Javascript's closures, except that they've made a bit more complex.

Here are the references: 

[Understanding Ruby Blocks, Procs and Lambdas](http://www.reactive.io/tips/2008/12/21/understanding-ruby-blocks-procs-and-lambdas/)

[The & operator in Ruby](http://ablogaboutcode.com/2012/01/04/the-ampersand-operator-in-ruby/)

===

* Blocks cannot be assigned to variables, procs and lambdas can

* Lambdas have explicit argument checking, procs do not.

Invoking a Proc does not check its argument list for the same number of arguments. 

```!ruby

x = Proc.new do |a,b,c|
puts a+b
end

x.call(1,2) # no error

```

For a lambda this will be an error, since it expects 3 arguments but is called with 2 instead.

* Lambdas are more like methods than Procs, so a `return` call in a lambda returns from itself. Using `return` in a Proc however will return from its containing method. It's not a subtle difference.

* Use the `method` method to assign methods to variables

Look at how I assign a method to another variable in a Python class.

```!python

class PAlpha(object):
  
  def s(a, b):
      print a, '+', b

  # assignment of s to another_s
  another_s = s

p = PAlpha()
p.s("1", "2")

```


Ruby's method calls do not require parentheses. So if I were to do the same thing in Ruby it would be assumed that `another_s` stores the value returned by `s` (which in this case would be `nil`)

```!ruby

class Alpha
  def s(a, b)
     puts "called #{a} + #{b}"
  end

  def another_s(a, b)
     s(a,b)
  end
end

a = Alpha.new
a.s "1", "2" # see! does not require parentheses


```
This is the only way I know so far to do the same thing.

Ruby doesn't allow the same kind of flexibility as Python in this case, but it definitely looks more explicit.

But if it were not instance methods but just functions in general, it would require use of the `method` function.

```!ruby

def s(a,b)
   puts "#{a} + #{b}"
end

another_s = method(:s)
another_s.call(1, 2)

```

It seems that it has to do with scoping. Only if `s(1,2)` is valid will `method(:s)` work and actually wrap up the method.
