--- 
date: 2021-01-19
title: "Web Component Navigation"
description: ""
tags: [ui-development,programming]
---

On my last consulting project, we used Web Components to stitch large pieces of the UI together.

Kinda like non-awful inverse iframes.

Each application provided its own UI, which would include/import a big navigation web component that had its own lifecycle.
The boundary was kept relatively clean since a web component can only communicate with its parent via element attributes.

Basically, we designed it where the parent controlled the state of the navigation by putting a couple of JSON blobs on specific attributes.
Then, the navigation would just redraw itself based on what was in there.
That way, each application could have whatever it wanted in the navigation tree.

I had plans to further subdivide that a bit or just have a few more common pieces (e.g. SSO logic) encapsulated in web components.

The cool thing was that the navigation piece was agnostic to what the surrouding application was built in.
It didn't matter if the application was static, Angular, React, or anything else, theoretically.

The web component itself was built with Angular using Angular Elements.
It was definitely not the most lightweight navigation in the world, but that's part of the cost of that sort of flexibility.

If you want to bootstrap your own WC, it's basically as simple as creating a class for the component and registering it with the browser with:

```
CustomElementRegistry.define()
```

For my tastes, it kinda sucks that it has to be in a class, but that's just a requirement for the bootstrapping piece.
You could initialize a whole different framework in there if you wanted (and that's basically what Angular Elements does).

## Would you do it again?

Were I to do it again, I'd definitely do it differently.
Mostly, I'd avoid Angular like the plague, frankly.
The most dynamic I'd get for navigation components in particular would be React.
Possibly even something a bit smaller like Preact or Inferno.

I'd definitely look at using WCs for stupidly flexible common navigation pieces again, though.
Like i said, you can really think of it like what iframes wanted to be or, really, how everybody wanted iframes to work.

More info:
https://developer.mozilla.org/en-US/docs/Web/Web_Components/Using_custom_elements
