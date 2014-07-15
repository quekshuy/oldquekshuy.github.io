---
published: true
title: RSpec custom matchers with multiple arguments
layout: post
---
I have to admit, I don't know how to write them,

```
RSpec::Matchers.define :some_multiple_of do |a,b|
   match { |actual| 
     #do some kind of equivalence(comparison), boolean expression here
   }
end

#Usage

describe 10 do
   it { expect(10).to some_multiple_of(2,5) }
end

```
That's as far as I can go. I'm not even sure if that's valid RSpec code.

The trouble is the `actual` argument -- it's dependent on the enclosing describe (group).


And when pressed for time, I just cook weird shit up. Like this (and this is valid; I've tested)

```

# The block at the end of the receive expects 2 arguments, 
# coinciding with the signature of some_method

expect(worker).to receive(:some_method) { |e1, e2| 
    expect(e1).to(eq(1)) && expect(e2).to(eq(2))
}

```