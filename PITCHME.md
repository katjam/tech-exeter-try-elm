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

@ul
- Teach you functional programming concepts
- Compare Elm vs React, Vue and Angular
- Discuss the newly released Elm 0.19 (Big yay! to Evan)
@ulend

Note:
- Loads of people can do that much better than I can - and one of the awesome things about elm is that you can forget that it's functional. Do first - understand later.
- I won't make excuses or justifications about the size of the Elm community
- Note about 0.19 - some things have changed - but my examples will use 0.18 e.g. elm-lang packages now elm and elm-package.json is now elm.json
- If you are interested in any of those, come and see me later - I can point you towards some resources.


+++

# This talk will

- Shine a little light on Elm and why I enjoy using it

---

# Our (fun) problem

- Building user interfaces for amazing APIs
- Our tools = code - languages, libraries, frameworks, transpilers, editors/ ides (sadly not lego)

Note:
- We're lucky enough to be in a rapidly evolving industry.
- A few years ago we'd have written html, css and a bit of jquery
- Maybe used some templating
- As we asked our browsers to handle interpreting more and more complex code - our code turned to unpredictable, unmaintainable, magic, held together by sticky tape...
- Frameworks started popping up, and build tools and new syntaxes that would make the code easier to use in the way we wanted to - and transpilers.

---?image=elm-lang-home.png&size=auto 32%&position=top
# So what is Elm?

@ul
- Uses ML style syntax.
- Based on functional programming principles
- Statically typed
- Compiles to Javascript
- More than a language, it defines an architecture that helps us write good code
@ulend

Note:
- Elm is a language based on functional programming principles that compiles to Javascript and defines an architecture that makes rapid prototyping, evolving and scaling web apps and maintaining a single source of truth easy.
- Describes itself as: A delightful language for reliable webapps.
- And claims to "Generate JavaScript with great performance and no runtime exceptions." It sounds too good to be true.... but I am going to demonstrate that you can write type safe & functional without a phd in category theory or a lisp in sight.
- Instead of listing the benefits - let's see how it works.

---
# Anatomy of an Elm app
Note:
- update function like a react reducer
- Tiny bit about pure functions - they return a typed value (total vs partial)

+++
# Elements

Note:
- html nodes - e.g. button [] []
-
+++
# Syntax and Format

Note:
- Show the code looking like js then - Show how elm-format snaps into shape... so if it takes your muscle memory a while to retrain - don't worry. Like prettier but without the arguments over spaces, tabs and semicolons. It also means the machine can parse with confidence.

---
# Get started
- Tooling elm make and elm reactor
- Create Elm App - webpack
- debugger import/ export

Note:
- Export history with bug and import into another browser (QA team)

---
# Example

```elm
import Html exposing (..)
import Html.events exposing (onClick)

-- MODEL

type alias Model = {rocks: Int}

model: Model
model = { rocks = 9 }

-- UPDATE

type Msg = Reset

update : Msg -> Model -> Model
update msg model =
  case msg of
    Reset -> { model | rocks = 0 }

-- VIEW

view : Model -> Html Msg
view model =
  div []
    [ h1 [] [ text "Hello Exeter!" ]
    , h2 [] [ text "Let's count some rocks" ]
    , button [ onClick Reset ] [ text "reset" ]
    ]

main =
  Html.beginnerProgram { model = model, view = view, update = update }

```

@[1-2](Import from libraries and expose only the bits you need)
@[3-9](Our Model)
@[10-12](Our Update functions)
@[13-15](Our View)

+++
# Confident refactor
+++
# Impossible states impossible 
# 0 runtime error
- Show minor typo example as js runtime error
+++
# Compiler lead development
- Start by adding new feature - follow compiler messages
+++
# Using union types
Note:
- Slug = Slug not Slug = string
+++
# Easy to expose good API
+++

---
Trade off between power & what we can know
Elm package (diff versions to show changes)
Start small - convert one part of your app to elm and keep building

---
# Elm community
- Elm town, meetups, slack, discourse, great docs, conferences
- Great for learning - in fact I'm working on a course for primary school children
- Easy for non-programmers - e.g. scientists needing visualisations


[Production code](https://github.co.uk/katjam/elm-pic-story-site)
