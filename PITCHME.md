---?image=elm-logo.svg&size=auto 32%&position=top&padding=20px
# Try Elm
No runtime errors. Safe and fun refactors!

---?image=neontribe-logo.png&size=auto 32%&position=top&padding=20px
# About me
@ul
- Senior web "engineer" at Neontribe
- Not a frontend developer
@ulend

Note:

- I've been working with web technologies for 10 years - but really I'm less of a computer scientist - more a person who just likes making stuff that might make someone's life a little more enjoyable - and I'm using code to do that.  
- These days a lot of us cover many parts of the stack to lesser or greater extent. I've never thought of myself as a frontend dev - because I can't do visual design - and the bulk of my coding experience is in writing backends and APIs in php.
- But - the lines are blurring


+++


# I like making stuff that helps

@ul

- Generally optimistic
- Learn by doing
- I @fa[heart] javascript
- Believe in open source, open minded

@ulend

Note:

- I don't mind who or what it helps as long as the help goes towards lessening the overall help needed in the universe - giving help to bad or giving bad help creates the need for more and more help to be given.
- In practice that means - I like to jump right in try first and fail later... then try again
- It would surprise my colleagues to hear that - So explain The runnnig of javascript - xxx the equality, freedom it creates xxx... I do not like reading or writing javascript.
- Collaboration and sharing for progress and inclusion

---

# About you
## (Assumptions I'm making)
@ul

- Don't mind having fun
- Value safety & efficiency
- Want to deserve trust
- Might think new tech is fun - but old tech is safer

@ulend

Note:

- You might not share the same approah to codeing as me.
- Hopefully you are more responsible.
- Probably share some of the same goals...

---

# This talk will not

- Teach you functional programming concepts
- Compare Elm vs React, Vue and Angular
- Discuss the newly released Elm 0.19 (Big yay! to Evan)

Note:
- Loads of people can do that much better than I can - and one of the awesome things about elm is that you can forget that it's functional. Do first - understand later.
- I won't make excuses or justifications about the size of the Elm community
- If you are interested in any of those, come and see me later - I can point you towards some resources.


+++

# This talk will

- Shine a little light on Elm and why I enjoy using it

---

# First some background
## Building a user interface

Note:
- We're lucky enough to be in a rapidly evolving industry.
- A few years ago we'd have written html, css and a bit of jquery
- Maybe used some templating
- As we asked our browsers to handle interpreting more and more complex code - our code turned to unpredictable, unmaintainable, magic, held together by sticky tape...
- Frameworks started popping up, and build tools and new syntaxes that would make the code easier to use in the way we wanted to - and transpilers.

---?image=elm-lang-home.png&size=auto 32%&position=top
# So what is Elm?

Note:
- Elm is a language based on functional programming principles that compiles to Javascript and defines an architecture that makes rapid prototyping, evolving and scaling web apps and maintaining a single source of truth easy.
- Describes itself as: A delightful language for reliable webapps.
- And claims to "Generate JavaScript with great performance and no runtime exceptions." It sounds too good to be true.... but I am going to demonstrate that you can write type safe & functional without a phd in category theory or a lisp in sight.
- Instead of listing the benefits - let's see how it works.

+++



#
[Production code](https://github.co.uk/katjam/elm-pic-story-site)
