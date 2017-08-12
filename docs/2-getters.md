# Vuex Getters

In big projects, is common to use a same method in multiple places. To avoid code repetiton, the vuex getter is a method avaible to be accessed from our store.

First, we add a ``getters`` object to our ``Vuex Store``. The ``getters`` is where we put our methods, so, in bellow, you see a exemple of how add a method to work as a getter and consoles *Hello world* when called.

>Exemple

```javascript
// store.js

... new Vuex.Store({
  state: {},
  getters: {
    getterExemple: () => {
      console.log('Hello world');
    }
  }
})

```

To call this in a component, you can do this:

```javascript
// compontent.vue

computed: {
  getterExemple () {
    return this.$store.getters.getterExemple
  }
}
```

But, wait a minute.... And if we use all the same getters at multiple components? To fix this boring task, you can use the ``mapGetters`` helper.
To this, you need to import the ``mapGetters`` from *Vuex*. See the exemple below:

> Exemple
```javascript
// component.vue

computed: {
  mapGetters([
    'getterExemple',
    'anotherExistentGetter'
  ])
}
```

To access the method with another name, you can do like this:

```javascript
// component.vue

{
mapGetters({
    exemple: 'getterExemple',
    another: 'anotherExistentGetter'
  })
}
```