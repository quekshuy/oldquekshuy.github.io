---
published: true
title: Ruby quirk
layout: post
---
Well I wouldn't call it a quirk. It might be more explicit than Python in this area.

```
x = 0
if x
  puts 'x is not false'
else
  puts 'x is false'
end
```
guess what get's printed?

`'x is not false'`.

That's right, `0` is not coerced to `false`.

Interesting huh.