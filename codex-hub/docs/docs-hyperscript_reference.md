///\_hyperscript
================

Features
--------

name

description

example

[behavior](https://hyperscript.org/features/behavior)

Define cross-cutting behaviors that are applied to many HTML elements

[def](https://hyperscript.org/features/def)

Defines a function

[see details...](https://hyperscript.org/features/def)

[eventsource](https://hyperscript.org/features/event-source)

Subscribe to Server Sent Events (SSE)

[js](https://hyperscript.org/features/js)

Embed JavaScript code at the top level

[see details...](https://hyperscript.org/features/js)

[set](https://hyperscript.org/features/set)

Defines a new [element-scoped](https://hyperscript.org/docs#names_and_scoping) variable

[init](https://hyperscript.org/features/init)

Initialization logic to be run when the code is first loaded

[on](https://hyperscript.org/features/on)

Creates an event listener

`on click log "clicked!"`

[socket](https://hyperscript.org/features/socket)

Create a Web Socket

[worker](https://hyperscript.org/features/worker)

Create a Web Worker for asynchronous work

Commands
--------

See also [pseudo-commands](https://hyperscript.org/commands/pseudo-commands/).

name

description

example

[add](https://hyperscript.org/commands/add)

Adds content to a given target

`add .myClass to me`

[append](https://hyperscript.org/commands/append)

Appends a value to a string, array or HTML Element

`append "value" to myString`

[async](https://hyperscript.org/commands/async)

Runs commands asynchronously

`async fetch /example`

[beep](https://hyperscript.org/commands/beep)

Debug printing

`beep! <.foo/>`

[break](https://hyperscript.org/commands/break)

Breaks out of the current loop

`repeat 3 times break end`

[call/get](https://hyperscript.org/commands/call)

Evaluates an expression (e.g. a Javascript Function)

`call alert('yep, you can call javascript!')`

`get prompt('Enter your name')`

[continue](https://hyperscript.org/commands/continue)

Skips the remainder of a loop and continues at the top of the next iteration.

`repeat 3 times continue end`

[decrement](https://hyperscript.org/commands/decrement)

Subtracts a value to a variable, property, or attribute

`decrement counter`

[fetch](https://hyperscript.org/commands/fetch)

Send a fetch request

`fetch /demo then put it into my.innerHTML`

[go](https://hyperscript.org/commands/go)

Navigate to a new page or within a page

`go to the top of the body smoothly`

[halt](https://hyperscript.org/commands/halt)

Halts the current event (stopping propagate, etc.)

`halt`

[hide](https://hyperscript.org/commands/hide)

Hide an element in the DOM

`hide me`

[if](https://hyperscript.org/commands/if)

A conditional control flow command

`if I match .selected then call alert('I\'m selected!')`

[increment](https://hyperscript.org/commands/increment)

Adds a value to a variable, property, or attribute

`increment counter`

[js](https://hyperscript.org/commands/js)

Embeds javascript

`js alert('this is javascript'); end`

[log](https://hyperscript.org/commands/log)

Logs a given expression to the console, if possible

`log me`

[make](https://hyperscript.org/commands/make)

Creates a class instance or DOM element

`make a Set from a, b. c`, `make a <p/> called para`

[measure](https://hyperscript.org/commands/measure)

Gets the measurements for a given element

`measure me then log it`

[pick](https://hyperscript.org/commands/pick)

Selects items from arrays, strings and regex match results

`pick match of "(\w+)" from str`

[put](https://hyperscript.org/commands/put)

Puts a value into a given variable or property

`put "cool!" into me`

[remove](https://hyperscript.org/commands/remove)

Removes content

`log "bye, bye" then remove me`

[repeat](https://hyperscript.org/commands/repeat)

Iterates

`repeat for x in [1, 2, 3] log x end`

[return](https://hyperscript.org/commands/return)

Returns a value

`return 42`

[send/trigger](https://hyperscript.org/commands/send)

Sends an event

`send customEvent to #a-div`

[set](https://hyperscript.org/commands/set)

Sets a variable or property to a given value

`set x to 0`

[settle](https://hyperscript.org/commands/settle)

Waits for a transition to end on an element, if any

`add .fade-out then settle`

[show](https://hyperscript.org/commands/show)

Show an element in the DOM

`show #anotherDiv`

[take](https://hyperscript.org/commands/take)

Takes a class from a set of elements

`take .active from .tabs`

[tell](https://hyperscript.org/commands/tell)

Temporarily sets a new implicit target value

`tell <p/> add .highlight`

[throw](https://hyperscript.org/commands/throw)

Throws an exception

`throw "Bad Value"`

[toggle](https://hyperscript.org/commands/toggle)

Toggles content on a target

`toggle .clicked on me`

[transition](https://hyperscript.org/commands/transition)

Transitions properties on an element

`transition opacity to 0`

[wait](https://hyperscript.org/commands/wait)

Waits for an event or a given amount of time before resuming the command list

`wait 2s then remove me`

Expressions
-----------

See [expressions](https://hyperscript.org/expressions) for an overview.

name

description

example

[as expressions](https://hyperscript.org/expressions/as)

Converts an expression to a new value

`"10" as Int`

[async expressions](https://hyperscript.org/expressions/async)

Evaluate an expression asynchronously

`set x to async getPromise()`

[attribute reference](https://hyperscript.org/expressions/attribute-ref)

An attribute reference

`[selected=true]`

[block literal](https://hyperscript.org/expressions/block-literal)

Anonymous functions with an expression body

`\ x -> x * x`

[class reference](https://hyperscript.org/expressions/class-reference)

A class reference

`.active`

[closest expression](https://hyperscript.org/expressions/closest)

Find closest element

`closest <div/>`

[comparison operator](https://hyperscript.org/expressions/comparison-operator)

Comparison operators

`x == "foo" I match <:active/>`

[id reference](https://hyperscript.org/expressions/id-reference)

An id reference

`#main-div`

[logical operator](https://hyperscript.org/expressions/logical-operator)

Logical operators

`x and y`  
`z or false`

[no operator](https://hyperscript.org/expressions/no)

No operator

`no element.children`

[of expression](https://hyperscript.org/expressions/of)

Get a property of an object

`the location of window`

[query reference](https://hyperscript.org/expressions/query-reference)

A query reference

`<button/> <:focused/>`

[relative positional expressions](https://hyperscript.org/expressions/relative-positional/)

Get a positional value out of an array-like object

`next <div/> from me`

[positional expressions](https://hyperscript.org/expressions/positional)

Get a positional value out of an array-like object

`first from <div/>`

[possessive expressions](https://hyperscript.org/expressions/possessive)

Get a property or attribute from an element

`the window's location`

[time expression](https://hyperscript.org/expressions/time-expression)

A time expression

`200ms`

[cookies symbol](https://hyperscript.org/expressions/cookies)

A symbol for accessing cookies

`cookies['My-Cookie']`

Magic Values
------------

name

description

example

[it](https://hyperscript.org/expressions/it)

The result of a previous command

`fetch /people as json then put it into people`

[me](https://hyperscript.org/expressions/me)

Reference to the current element

`put 'clicked' into me`

[you](https://hyperscript.org/expressions/you)

Reference to a target element

`tell <p/> remove yourself`

Literals
--------

Define other values just like you do in Javascript

name

description

example

arrays

Javascript-style array literals

`[1, 2, 3]`

booleans

Javascript-style booleans

`true false`

math operators

Javascript-style mathematical operators (`mod` is a keyword in place of `%`)

`1 + 2`

null

Javascript-style null

`null`

numbers

Javascript-style numbers

`1 3.14`

objects

Javascript-style object literals

`{foo:"bar", doh:42}`

[strings](https://hyperscript.org/expressions/string)

Javascript-style strings

`"a string", 'another string'`

See also [pseudo-commands](https://hyperscript.org/commands/pseudo-commands/).

name

description

example

[add](https://hyperscript.org/commands/add)

Adds content to a given target

`add .myClass to me`

[append](https://hyperscript.org/commands/append)

Appends a value to a string, array or HTML Element

`append "value" to myString`

[async](https://hyperscript.org/commands/async)

Runs commands asynchronously

`async fetch /example`

[beep](https://hyperscript.org/commands/beep)

Debug printing

`beep! <.foo/>`

[break](https://hyperscript.org/commands/break)

Breaks out of the current loop

`repeat 3 times break end`

[call/get](https://hyperscript.org/commands/call)

Evaluates an expression (e.g. a Javascript Function)

`call alert('yep, you can call javascript!')`

`get prompt('Enter your name')`

[continue](https://hyperscript.org/commands/continue)

Skips the remainder of a loop and continues at the top of the next iteration.

`repeat 3 times continue end`

[decrement](https://hyperscript.org/commands/decrement)

Subtracts a value to a variable, property, or attribute

`decrement counter`

[fetch](https://hyperscript.org/commands/fetch)

Send a fetch request

`fetch /demo then put it into my.innerHTML`

[go](https://hyperscript.org/commands/go)

Navigate to a new page or within a page

`go to the top of the body smoothly`

[halt](https://hyperscript.org/commands/halt)

Halts the current event (stopping propagate, etc.)

`halt`

[hide](https://hyperscript.org/commands/hide)

Hide an element in the DOM

`hide me`

[if](https://hyperscript.org/commands/if)

A conditional control flow command

`if I match .selected then call alert('I\'m selected!')`

[increment](https://hyperscript.org/commands/increment)

Adds a value to a variable, property, or attribute

`increment counter`

[js](https://hyperscript.org/commands/js)

Embeds javascript

`js alert('this is javascript'); end`

[log](https://hyperscript.org/commands/log)

Logs a given expression to the console, if possible

`log me`

[make](https://hyperscript.org/commands/make)

Creates a class instance or DOM element

`make a Set from a, b. c`, `make a <p/> called para`

[measure](https://hyperscript.org/commands/measure)

Gets the measurements for a given element

`measure me then log it`

[pick](https://hyperscript.org/commands/pick)

Selects items from arrays, strings and regex match results

`pick match of "(\w+)" from str`

[put](https://hyperscript.org/commands/put)

Puts a value into a given variable or property

`put "cool!" into me`

[remove](https://hyperscript.org/commands/remove)

Removes content

`log "bye, bye" then remove me`

[repeat](https://hyperscript.org/commands/repeat)

Iterates

`repeat for x in [1, 2, 3] log x end`

[return](https://hyperscript.org/commands/return)

Returns a value

`return 42`

[send/trigger](https://hyperscript.org/commands/send)

Sends an event

`send customEvent to #a-div`

[set](https://hyperscript.org/commands/set)

Sets a variable or property to a given value

`set x to 0`

[settle](https://hyperscript.org/commands/settle)

Waits for a transition to end on an element, if any

`add .fade-out then settle`

[show](https://hyperscript.org/commands/show)

Show an element in the DOM

`show #anotherDiv`

[take](https://hyperscript.org/commands/take)

Takes a class from a set of elements

`take .active from .tabs`

[tell](https://hyperscript.org/commands/tell)

Temporarily sets a new implicit target value

`tell <p/> add .highlight`

[throw](https://hyperscript.org/commands/throw)

Throws an exception

`throw "Bad Value"`

[toggle](https://hyperscript.org/commands/toggle)

Toggles content on a target

`toggle .clicked on me`

[transition](https://hyperscript.org/commands/transition)

Transitions properties on an element

`transition opacity to 0`

[wait](https://hyperscript.org/commands/wait)

Waits for an event or a given amount of time before resuming the command list

`wait 2s then remove me`

Events
------

name

description

`hyperscript:ready`

Triggered on the document after hyperscript has processed the page

`load`

Triggered on an element with hyperscript on it after it has loaded

`fetch:beforeRequest`

Triggered before a `fetch` command sends a request

`fetch:afterResponse`

Triggered after a `fetch` command recieves a response

`fetch:afterRequest`

Triggered after a `fetch` command handles a response

`fetch:error`

Triggered when a `fetch` command gets an error

`fetch:abort`

Triggered when a `fetch` command request is aborted

`hyperscript:beep`

Triggered when a `beep` command executes