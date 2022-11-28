#architecture #pattern #web #web 

- developers can create their own complex [[HTML]] elements, called custom elements
- these can inherit behavior from an existing [[HTML]] element, or define their own behavior completely

```html
Class SampleElement extends HTMLParagraphElement {
	constructor() {
		super();
	}
}
...
CustomElementRegistry.define('sample-element',
														 SampleElement,
								 						 { extends: 'p' });
...
<sample-element> example </sample-element>
```