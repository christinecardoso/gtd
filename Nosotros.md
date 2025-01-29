---
counter: 0
Count: 0
cigarettes: 19

---

- customer Brock was just told by his nutritionist that he needs to stop drinking scotch and wines and transition to tequilas. He was very impressed with the Nosotros. He liked the dark of varietal as it was closer in relation to what he’s used to it as a scotch drinker. He ended up going with his pick of Suavecito, but will try Nosotros next time. He was going with an Anejo.
- 3
- Make a button for counter for how many tasters and people



```dataviewjs 
const {update} = this.app.plugins.plugins["metaedit"].api;
const {createButton} = app.plugins.plugins["buttons"];

// Display the current count of cigarettes
dv.el("p", "Smoked today: `$= dv.current().cigarettes` cigarettes");
createButton({app, el: this.container, args: {name: "+1 🚬"}, 
 clickOverride: {click: update, params: ['cigarettes',
dv.current().cigarettes + 1, dv.current().file.path]},
}); 

```



