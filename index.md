<!--
bodyclass intro-background
class align-right border-right copyright-right
-->

# Why we built another framework
[@delvedor](https://twitter.com/delvedor)

---
<!--
class technical-debt boxed-em
-->

# Or you die as *innovator*,
# or you live long enough to become the *technical debt*.

---
<!--
class small nobreak
-->

Can we avoid that*?*

---
<!--
class small
-->

# Hey!

---
<!--
class small
-->

# I’ve built a *new framework!*

---
<!--
class small
-->

# Inside we are using *Express*.

---
<!--
class center center-image
-->

![astonished](images/astonished.gif)

---

# Two years ago*.*

---

# Express Hapi Restify Koa Micro Connect take-five total.js

---
<!--
class nobreak
-->

*`fast`*`-json-stringify`

---
<!--
class row json-faster
-->

```js
const FJS = require('fast-json-stringify')

const stringify = FJS({
  type: 'object',
  properties: {
    firstName: { type: 'string' },
    lastName: { type: 'string' },
    age: { type: 'integer' }
  }
})

console.log(stringify({
  firstName: 'Tomas',
  lastName: 'Della Vedova',
  age: 25
}))
```

# 2-3x *faster*

---
<!--
bodyclass fastify-background
-->
![fastify-logo](images/fastify-white-landscape.png)

---

# Design goals*.*

---

Design goals*.*
# Built for *speed*

---
<!--
class center-image small
-->

![benchmarks](images/benchmarks.png)

---

Design goals*.*
# Almost zero *overhead*

---
<!--
class small
-->

# Overhead:
# the *price* you are paying for a set of *features*.

---
<!--
class center center-image
-->

![flame-bare](images/flame-bare.png)

---
<!--
class center center-image
-->

![flame-fastify](images/flame-fastify.png)

---
<!--
class center center-image
-->

![flame-express](images/flame-express.png)

---

Design goals*.*
# As *light* as possible

---
<!--
class small
-->

Every feature we implement in core is something that *we must maintain*.

---
<!--
class small
-->

Change it in the future could lead to massive *breaking changes* for the community.

---
<!--
class small nobreak
-->

How can we fix this*?*

---

Design goals*.*
# Extensible via *plugins*

---

```js
fastify.register(
  require('my-plugin'),
  { options }
)
```

---
<!--
class row async-plugin
-->

```js
function myPlugin (fastify, opts, next) {
  // register other plugins
  fastify.register(...)

  // add hooks
  fastify.addHook(...)

  // add decorator
  fastify.decorate(...)

  // add routes
  fastify.route(...)

  next()
}

module.exports = myPlugin
```

## *async await* is supported as well!

---
<!--
class center small-image
-->

# Plugins: *Architecture*
![dag](images/dag.png)

---
<!--
class center small-image
-->

# Plugins: *Encapsulation*
![dag-decorate](images/dag-decorate.png)

---

### Exposing functionality to *parents*
```js
const fp = require('fastify-plugin')

async function myPlugin (fastify, options) {
  fastify.decorate('util', yourAwesomeUtility)
  // now you can use it with `fastify.util`
}

module.exports = fp(myPlugin)
```

---
<!--
class center small-image
-->

# Plugins: *Encapsulation*
![dag-fp-encapsulate](images/dag-fp-encapsulate.png)

---

### *Encapsulation* enables many great things
### such as custom `log-level` per plugin

<br/>

```js
const fastify = require('fastify')()

fastify.register(require('./api/v1'), {
  prefix: '/v1',
  logLevel: 'error'
})

fastify.register(require('./api/v2'), {
  prefix: '/v2',
  logLevel: 'debug'
})
```

---
<!--
class center small-image
-->

# Plugins: Real world
![plugin-real-world](images/plugin-real-world.png)

---
<!--
class boxed-em
-->

# *Everything* is a plugin

---

Design goals*.*
# Developer *experience*

---
<!--
class nobreak
-->

API that is *easy to use* and understand;

<br/>

*Painless* transition from monolith to microservices;

<br/>

Extensive and quality *documentation* & *tooling*;

<br/>

*Responsive* to issues and questions.

---

Design goals*.*
# *Long* Term Support

---
<!--
class nobreak
-->

Minimum *six months* of active development<br/>from the release date.

<br/>

Additional six months of *security updates*<br/>after a new Major.

---

Design goals*.*
# *Open* open source

---
<!--
class small
-->

Individuals making significant and valuable *contributions* are given commit-access to the project to contribute as they see fit*.*

<br/>

[openopensource.org](http://openopensource.org/)

---

# Two years after*.*

---

# *Fastify* `v2` is coming*.*

---

# Community impact*.*

---
<!--
class center-image
-->

![global-downloads](images/global-downloads.png)

---
<!--
class center-image
-->

![npm-keyword](images/npm-keyword.png)

---
<!--
class small
-->

# Currently, there are *78* officially recognized plugins

---
<!--
class small
-->

# *33* maintained by the core team

---
<!--
class boxed-em small
-->

# One plugin *every 10 days*

---
<!--
class small
-->

# *≥ 7900* stars

---
<!--
class small
-->

# *100* unique contributors

---
<!--
class small
-->

# *≥ 400* forks

---
<!--
class small
-->

# *≥ 90* releases

---
<!--
class small
-->

# *≥ 1700* commits

---
<!--
class small team
-->

# Core team: *nine awesome people*

<br/>

[allevo](https://github.com/allevo) [delvedor](https://github.com/delvedor) [evanshortiss](https://github.com/evanshortiss) [lmammino](https://github.com/lmammino) [jsumners](https://github.com/jsumners) [mcollina](https://github.com/mcollina) [nwoltman](https://github.com/nwoltman) [starptech](https://github.com/starptech) [trivikr](https://github.com/trivikr)

---
<!--
class very-small center
-->

Demo*!*

---
<!--
bodyclass fastify-background
-->
![fastify-logo](images/fastify-white-landscape.png)

---
<!--
class elastic-logo small
-->

![elastic-logo-light](images/elastic-logo-light.png)
![elastic-logo-dark](images/elastic-logo-dark.png)

---
<!--
bodyclass intro-background
class copyright-right
-->

# Thanks*!*
[@delvedor](https://twitter.com/delvedor)
