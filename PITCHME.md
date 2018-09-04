---?image=elm-logo.svg&size=auto 32%&position=top&padding=20px
# Try Elm
No runtime errors. Safe and fun refactors!

---?image=neontribe-logo.png&size=auto 32%&position=top&padding=20px
## Katja Mordaunt

Note:

- Senior developer at Neontribe. Been working with web technologies for 10 years - but less computer scientist - more a person who just likes making stuff - and using code to do that.  
- These days a lot of us cover many parts of the stack. I've never thought of myself as a frontend dev - because I can't do visual design - and the bulk of my coding experience is in writing backends and APIs in php.


+++

## I like making stuff that helps

IMAGE - piles of help

Note:

- Generally optimistic
- I don't mind who or what it helps as long as the help goes towards lessening the overall help needed in the universe - giving help to bad or giving bad help creates the need for more and more help to be given.

- Learn by doing
- In practice that means - I like to jump right in try first and fail later... then try again

- I @fa[heart] javascript
- It would surprise my colleagues to hear that - So explain The runnnig of javascript - xxx the equality, freedom it creates by a core of universally supported standard on majority of our devices xxx... I do not like reading or writing javascript.

- Believe in open source, open minded
- Collaboration and sharing for progress and inclusion

---

## Assumptions I'm making about you

@ul
- Don't mind having fun
- Value safety & efficiency
- You want your clients' to trust to be well earned
- Might think new tech is fun - but old tech is safer
@ulend


Note:

- You might not share the same approah to coding as me.
- Maybe you like to plan a whole structure instead of jumping in.
- But - you probably share some of the same goals...
- START LIST end

---

## This talk will not

@ul
- Teach you functional programming concepts
- Compare Elm vs React, Vue and Angular
- Discuss the newly released Elm 0.19
@ulend

Note:
- Loads of people can do that much better than I can - and one of the awesome things about elm is that you can forget that it's functional. Do first - understand later.
- I won't make excuses or justifications about the size of the Elm community
- Note about 0.19 - some things have changed - but my examples will use 0.18 e.g. elm-lang packages now elm and elm-package.json is now elm.json
- If you are interested in any of those, come and see me later - I can point you towards some resources.


+++

## This talk will

- Shine a little light on Elm and why I enjoy using it

---

## Our (fun) problem

IMAGE logos for all the gone by the wayside. Any of these look familiar?

![alt-text-1](bower-grunt-yeoman.png "Bower Grunt Yeoman") ![alt-text-2](handlebars_logo.png "Handlebars")
![](mustache-js.png) ![](coffeescript.png) !![](gulp.png)

angular 1.0, backbone, polymer, ember, postcss, css modules

Note:
- Building user interfaces for amazing APIs
- Our tools = code - languages, libraries, frameworks, transpilers, editors/ ides (sadly not lego)

- We're lucky enough to be in a rapidly evolving industry.
- A few years ago we'd have written html, css and a bit of jquery
- Maybe used some templating
- As we asked our browsers to handle interpreting more and more complex code - our code turned to unpredictable, unmaintainable, magic, held together by sticky tape...
- Frameworks started popping up, and build tools and new syntaxes that would make the code easier to use in the way we wanted to - and transpilers.

---?image=elm-lang-home.png&size=auto 32%&position=top

Note:

- Describes itself as: A delightful language for reliable webapps.
- And claims to "Generate JavaScript with great performance and no runtime exceptions." It sounds too good to be true.... but I am going to demonstrate that you can write type safe & functional without a phd in category theory or a lisp in sight.

+++

### A couple of things you know before we get started.. so things don't seem scary.

@ul
- Uses ML style syntax
- Based on functional programming principles
- Statically typed
- Compiles to Javascript
- More than a language, it defines an architecture that helps us write good code
@ulend

Note:
- Elm is a language based on functional programming principles that compiles to Javascript and defines an architecture that makes rapid prototyping, evolving and scaling web apps and maintaining a single source of truth easy.
- Instead of listing the benefits - let's see how it works.

---
IMAGE or flow
# Anatomy of an Elm app

CODE - beginner programme highlight model then update then view

Note:
- model - your 'state'
- update function like a react redux reducer - unidirectional dataflow 
- view - display
- subscriptions for outside events like time but not this example

+++
# Syntax

```elm
"Hello " ++ "Exeter!"
> Hello Exeter!

5 / 2
> 2.5

5 // 2
> 2

addTwo : Int -> Int -> String
addTwo a b =
  toString a ++ "+" ++ toString b ++ "=" ++ toString (a + b)

addTwo 2 3
> 2+3=5
```

@[1-2](Concatenate strings with `++`)
@[4-8](Division can be floating point / or integer //)
@[10-12](Define a function that takes 2 integers and returns a string)
@[10](The type annotation)
@[11-12](The function definition)
@[14](Call the function)
@[15](The result is a string)

Note:
- Double quotes for strings single for characters

+++
# Format

CODE: some html - formated like traditional html 
CODE: snap to  elm-format 

CODE - with these as capitons?
@ul
- elm-format standard defined by elm
- machine can parse with confidence
- no one forgets the commas
- don't need trailing commas to eliminate bad diffs
@ulend

- html nodes - e.g. button [] []

Note:
- Elm primarily designed for making UIs so not surprising that there is good support for what ew traditionally think of as html elements - in elm they are nodes.
- Show the code looking like js then - Show how elm-format snaps into shape... so if it takes your muscle memory a while to retrain - don't worry. Like prettier but without the arguments over spaces, tabs and semicolons.

---
## Quick scenaro

IMAGE - client with button presser.
ELM coder no problem. JS getting - which framework to choose?

Note: We'll follow the elm project. leave js up to your imagination.

+++
# Awesome brick counter!

```elm
import Html exposing (..)
import Html.Attributes exposing (style)
import Html.events exposing (onClick)

-- MODEL

type alias Model =
    { bricks: Int }

model: Model
model =
    { bricks = 9 }

-- UPDATE

type Msg
    = Reset

update : Msg -> Model -> Model
update msg model =
    case msg of
        Reset ->
          { model | bricks = 0 }

-- VIEW

view : Model -> Html Msg
view model =
    div [ style [("padding-left", "2em")] ]
        [ h1 [] [ text "Hello Exeter!" ]
        , h2 [] [ text "Let's count some bricks" ]
        , div [] [ text (toString model.bricks) ]
        , button [ onClick Reset ] [ text "reset" ]
        ]

main =
  Html.beginnerProgram { model = model, view = view, update = update }

```

@[1-4](Import from libraries and expose only the bits you need)
@[5-11](Our Model)
@[12-19](Our Update functions)
@[20-32](Our View)
@[33-35](The magic!)

+++
# Confident refactor
+++
# Impossible states impossible 
# 0 runtime error
- Show minor typo example as js runtime error colour vs color! organisation vs. organization.
+++
# Compiler lead development
- Start by adding new feature - follow compiler messages
+++
# Using union types
Note:
- Slug = Slug not Slug = string
- So later when slug changes to string + referrer string... compiler will tell us in all the places we used it.
-
+++
# Easy to expose good API
+++


---
# Get started
- Tooling elm make and elm reactor
- Create Elm App - webpack
- debugger import/ export

Note:
- Export history with bug and import into another browser (QA team)


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
