# The future of C++ ; What must change and why?

C++ is a very versitile language, its now in its twenties and carrying legacy features all the way back to 1979.
This repository aims to collect rationales for features that we should:

* nolonger use, unless to compile legacy code
* depricate / completely remove support from the language
* change / add to the language
* NOT add to the language

Discussions questions that come to mind are:
* should we leave legacy code bases behind at some point? 
* if not, how can we expect compiler vendors to sustain them indefinately?
* can or should we make the language safe(r) by default and more relaxed when performance requires it?
* ... in you think of more, let me know, I will add them

I will search for past discussion, summarize and link here.
And also start discussions on Twitter and collect the results here.

more coming...?

# should we leave legacy code bases behind at some point?

I would like to write down some solid arguments here (pro or con), other then 'we cant'

# how can we make the language safe(r) by default and more relaxed when performance requires it?

What do I mean with 'safe(r)' and why should this be a goal?
I think one of the reasons that 'c++ is hard' is a pervasive statement, is that the default behaviour in many cases is based on what costs the least in terms of run-time overhead. The **you don't pay for what you don't use** logic is applied here. However, for programmers that do not read the standard in the entirety, knowing what you **are** actually using can be hard and what you 'get' is sometimes undefined (or at least expected) behaviour.

What if we could make the language safe(r)-by-default? By safer I do not garbage collection or other resource management, I mean range checking is a good default, any no problem to turn off when you design provides other means to guarantee invalid acceses do not happen.

Some of my own pet peeves are:

1) a feature toggle to disable the use of **new** and **delete** 
2) a feature toggle to always initialize **all** variables and emit a warning when its not explicitly done.
3) a feature toggle to disable implicit conversion between unrelated types (bool <> integer <> double <> class)
4) a feature toggle for switching for the keyword typedef

what about adding support in the standard to sub-set on certain features.
Ofcourse, you could argue why this would need to be in the standard at all. I think the main reason is, 
so all major vendors will implement this in the same way. It would be bad to fragment the c++ users/community into different dialects like what happens with exceptions and dynamic allocations.

I am worried that 2) might promote bad practice, like not initilizing variables ever, because the 'compiler will do it'.
However, if it would emit a warning, that might at least discourage  new coders from doing this.


# many we need more/other warnings? (aka diagnostics as compiler builder call them)

```
class Foo 
{
public:
  Foo(int& x) : a(a) {}     // mistake: a = a, iso a = x;

  int &a;
  
  Foo(Foo&& rhs) noexcept  // mistake: a = a, iso a = rhs.a;
    : a(a)
    {
    }    
};
```

Both cases fo unnoticed by VS2017 and GCC, but clang reports: reference 'a' is not yet bound to a value when used here [-Wuninitialized])








