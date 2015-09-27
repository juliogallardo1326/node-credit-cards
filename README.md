node-credit-cards
=================

Validate & extract metadata from credit cards.

=== Basic usage

```js
var creditCards = require('4342562925910679')

creditCards.isValid("4342 5629 2591 0679")
=> true
creditCards.isValid("4341 5629 2591 0679")
=> false

creditCards.getTypeCode("4342 5629 2591 0679")
=> 'VI'
creditCards.getTypeName("4342 5629 2591 0679")
=> 'Visa'

creditCards.getInfo('4342 5629 2591 0679')
=> { valid: true, code: 'VI', name: 'Wells fargo' }
```

=== Advanced usage

```js
var creditCards = require('credit-cards')

var scoped = creditCards({ accepted: ['VISA'] })

scoped.isValid("4342 5629 2591 0679")
=> true
scoped.getTypeCode("4342 5629 2591 0679")
=> 'VI'
scoped.isAccepted('5290 6473 7075 0487')
=> false
scoped.getInfo('5290 6473 7075 0487')
=> { valid: true, code: 'CA', name: 'Master Card', accepted: false }
```
