# The future of C++ ; What must change and why?

C++ is a very versitile language, its now in its twenties and carrying legacy features all the way back to 1979.
This repository aims to collect rationales for features that we should:

* nolonger use unless to compile legacy code
* depricate / completely remove support from the language
* change / add to the language
* NOT add to the language

Discussions questions that come to mind are:
* should we leave legacy code bases behind at some point? 
* if not, how can we expect compiler vendors to sustain them indefinately?
* how can we make the language safe by default and unsafe when performance requires it?
* ... in you think of more, let me know, I will add them

I will search for past discussion, summarize and link here.
And also start discussions on Twitter and collect the results here.

* should we leave legacy code bases behind at some point? 
* if not, how can we expect compiler vendors to sustain them indefinately?
* how can we make the language safe by default and unsafe when performance requires it?
*

more coming...?

# should we leave legacy code bases behind at some point?

# how can we make the language safe by default and unsafe when performance requires it?

... and why should this be a goal?
I think one of the reasons that 'c++ is hard' is a pervasive statement, is that the default behaviour in many cases is based on what costs the least in terms of run-time overhead. The **you don't pay for what you don't use** logic is applied here. However, for programmers that do not read the standard in the entirety, knowing what you *are* actually using can be hard.

I think we could start by adding support in the standard to sub-set on certain features.

Ofcourse, you could argue why this would need to be in the standard at all. I think the main reason is, 
so all major vendors will implement this in the same way. It would be bad if 



My own two pet peeves are:

- a compiler switch to disable the use of **new** and **delete** 
- a compiler switch always initialize *all* variables



