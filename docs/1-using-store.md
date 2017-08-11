# Get start with Vuex

To use Vuex, we first need to import and register then in Vue, with **Vue.use()** method.

> Exemple:

```javascript
// store.js

import Vue from 'vue';
import Vuex from 'vuex';

Vue.use(Vuex);
```

````

After we register Vuex, we create a instance of **Vuex.Store()** and export that to, after, import and pass to Vue created instance.

> Exemple

```javascript
// store.js
...

export const store = new Vuex.Store({
  state: {
    foo: 'bar'
  }
});
```

```javascript
// main.js

import Vue from 'vue'
import { store } from './store';

new Vue({
  el: '#app',
  store
});
```