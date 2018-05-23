
# (Possibly awesome) Web frameworks solving the Javascript problem

Because writing a web project with two languages is frustrating,
specially with Javascript.


We'll list here isomorphic web frameworks, that allow to write an
interactive web app without resorting to Javascript. Bonus point to
the ones not using JS libraries and not separating back and front
code.

Directly inspired by [https://wiki.haskell.org/The_JavaScript_Problem](https://wiki.haskell.org/The_JavaScript_Problem).

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
        - [Anpylar](#anpylar)
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

[https://wiki.haskell.org/The_JavaScript_Problem](https://wiki.haskell.org/The_JavaScript_Problem)

### Haste

- https://haste-lang.org/docs/
- examples: https://github.com/valderman/haste-compiler/blob/master/examples/


## Nim

### Karax

>  Single page applications for Nim.

- https://github.com/pragmagic/karax
- production example: https://forum.nim-lang.org/. [github](https://github.com/nim-lang/nimforum).

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

Excerpt from the [tutorial](https://ocsigen.org/tuto/6.1/manual/tutowidgets):

The following code defines a client-server Web application with only one service, registered at URL / (the root of the website).

The code also defines a client-side application (section [%%client ... ] ) that appends a client-side generated widget to the page. Section [%%shared ... ] is compiled on both the server and the client-side programs. Inside such a section, you can write let%server or let%client to override [%%shared ... ] and define a server-only or client-only value (similarly for [%%server ... ] and [%%client ... ] ).

```ocaml
module Ex_app =
  Eliom_registration.App (struct
    let application_name = "ex"
    let global_data_path = None
  end)

let _ = Eliom_content.Html.D.(
  Ex_app.create
    ~path:(Eliom_service.Path [""])
    ~meth:(Eliom_service.Get Eliom_parameter.unit)
    (fun () () ->
       Lwt.return
         (Eliom_tools.D.html ~title:"tutowidgets" ~css:[["css"; "ex.css"]]
            (body [h2 [pcdata "Welcome to Ocsigen!"]])))
)

[%%client
let mywidget s1 s2 = Eliom_content.Html.D.(
  let button  = div ~a:[a_class ["button"]] [pcdata s1] in
  let content = div ~a:[a_class ["content"]] [pcdata s2] in
  div ~a:[a_class ["mywidget"]] [button; content]
)

let _ =
  let%lwt _ = Lwt_js_events.onload () in
  Dom.appendChild
    (Dom_html.document##.body)
    (Eliom_content.Html.To_dom.of_element (mywidget "Click me" "Hello!"));
  Lwt.return ()
]
```

The `##` is used to call a JS method from OCaml and `##.` to access a
JS object field.

`Lwt` is the concurrent library used to program threads on both client
and server sides. The syntax `let%lwt a = e1 in e2` allows waiting
(without blocking the rest of the program) for an Lwt thread to
terminate before continuing. `e2` must ben a Lwt thread
itself. `Lwt.return` enables creating an already-terminated Lwt thread.
`Lwt_js_events` defines a convenient way to program interface events
(mouse, keyboard, ...).

`Lwt_js_events.onload` is a Lwt thread that waits until the page is
loaded. There are similar functions to wait for other events, e.g.,
for a click on an element of the page, or for a key press.


**Editor's note**: quite some work to install, compile and deploy.

## Python

### Anpylar

- https://www.anpylar.com/
- uses [Brython](https://github.com/brython-dev/brython), an
  implementation of Python 3 running in the browser.

> [me] Reminds me of Nagare.
>
> [Anpylar team] AnPyLar has gone a step beyond by being client-side. One of the advantages is that the application is downloaded once, and can contain multiple pages and hierarchies, which are navigated without sending a single request to the server.
>
> The server can with it be a pure API server (and the server of the initial content download), with the advantage of no longer having to implement business logic in the server.


### Nagare

- http://www.nagare.org/
- based on Stackless Python
- allows continuations based web programming
- [production examples](http://www.nagare.org/trac/wiki/WhoUsesNagare),
  [Kansha](http://www.kansha.org/), open-source Trello clone.

**Editor's note**: looks like ASP .Net. Doesn't seem totally JavaScript free:

```python
@presentation.render_for(Board, 'switch')
def render_Board_item(self, h, comp, *args):
    reload_search = ajax.Update(component_to_update='show_results',
                                render=lambda renderer: comp.render(renderer, 'search_results'))
    h << h.script(u'''$(window).on('reload_search', function() { %s; })''' % reload_search.generate_action(41, h))

    with h.div(id='switch_zone'):
        if self.model == 'columns':
            search_cb = ajax.Update(
                action=self.search,
                component_to_update='show_results',
                render=lambda renderer: comp.render(renderer, 'search_results')
            ).generate_action(1, h).replace('this', 'elt')
            oninput = 'debounce(this, function(elt) { %s; }, 500)' % search_cb
            # etc
```

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
