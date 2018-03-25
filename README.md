
# Awesome web frameworks solving the Javascript problem

Because writing a web project with two languages is frustrating,
specially with Javascript.


We'll list here isomorphic web frameworks, that allow to write an
interactive web app without resorting to Javascript. Bonus point to
the ones not using JS libraries and not separating back and front
code.

Inspired by [https://wiki.haskell.org/The_JavaScript_Problem](https://wiki.haskell.org/The_JavaScript_Problem).

<!-- markdown-toc start - Don't edit this section. Run M-x markdown-toc-generate-toc again -->
**Table of Contents**

- [Awesome web frameworks solving the Javascript problem](#awesome-web-frameworks-solving-the-javascript-problem)
    - [Clojure & ClojureScript](#clojure--clojurescript)
    - [Common Lisp](#common-lisp)
        - [Weblocks](#weblocks)
    - [Haskell](#haskell)
    - [Nim](#nim)
        - [Karax](#karax)
    - [Ocaml](#ocaml)
        - [Eliom](#eliom)
    - [Python](#python)
        - [Nagare](#nagare)
    - [Ruby](#ruby)
        - [Inesita](#inesita)
        - [Volt [staling]](#volt-staling)
    - [Smalltalk](#smalltalk)
        - [Seaside](#seaside)
- [Contributing](#contributing)

<!-- markdown-toc end -->


## Clojure & ClojureScript

! heavily uses the JS ecosystem (specially React).


! Clojure and ClojureScript are two different things.

- [Reagent](https://reagent-project.github.io/), ...


## Common Lisp

### Weblocks

- being updated at [https://github.com/40ants/weblocks/blob/reblocks/docs/source/quickstart.rst](https://github.com/40ants/weblocks/blob/reblocks/docs/source/quickstart.rst)
- allows continuations based web programming
- can fallback to full html
- community links: [CL Cookbook](https://lispcookbook.github.io/cl-cookbook/), [Awesome CL](https://github.com/CodyReichert/awesome-cl), [lisp-lang.org](http://lisp-lang.org/)

> With Weblocks, you can handle all the business logic server-side,
> because an action can be any lisp function, even an anonymous
> lambda, closuring all necessary variables.

Similar to React but server based.

**Editor's note**: allows to keep the same CL development experience
all the way. Very lightweight.

## Haskell

https://wiki.haskell.org/The_JavaScript_Problem

## Nim

### Karax

>  Single page applications for Nim.

- https://github.com/pragmagic/karax

## Ocaml

### Eliom

- http://ocsigen.org/eliom/
- allows continuations based web programming
- targets web browsers and mobile devices (iOs, Android)
- production example: https://www.besport.com/

> Eliom is a multi-tier framework for developing multi-platform Web and mobile apps. It transforms OCaml into a multi-tier language: It makes it possible to write modern distributed applications fully in OCaml, for both the server and client parts, which simplifies a lot the communication between server and client. Applications are written as single programs that can run on any Web browser or mobile device (iOS, Android), saving from the need to develop one version for each platform.
>
> Eliom has support for reactive pages (generated on server or client), advanced session mechanism, server to client communication, continuation based Web programming, etc.
>
> It can also be used for more traditional Web or mobile apps: server only, single page applications, REST API, etc.

**Editor's note**: quite some work to install, compile and deploy.

## Python

### Nagare

- http://www.nagare.org/
- based on Stackless Python
- allows continuations based web programming
- [production examples](http://www.nagare.org/trac/wiki/WhoUsesNagare),
  [Kansha](http://www.kansha.org/), open-source Trello clone.

## Ruby

### Inesita

- https://github.com/inesita-rb/inesita
- based on [Opal](https://github.com/opal/opal), a Ruby to JavaScript
  source-to-source compiler.

> Inesita is a simple, light, Ruby front-end framework. Yes, Ruby, it’s all about Ruby, and its ecosystem.

### Volt [staling]

- https://github.com/voltrb/volt/
- based on Opal

> A Ruby web framework where your Ruby runs on both server and client


## Smalltalk

### Seaside

- http://seaside.st/
- continuations based


# Contributing

Thanks for doing so ! We didn't try everything let alone have we a
good experience with all of them, so we'll appreciate your light.

On this readme, we'd have quick links and highlights. We can have
discussions in issues and more in-depth resources and explanations in
a new file.
