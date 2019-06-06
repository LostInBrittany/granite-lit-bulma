## granite-lit-bulma

*granite-lit-bulma* is a wrapping of [Bulma CSS](https://picturepan2.github.io/bulma/) CSS as [LitElement](https://lit-element.polymer-project.org/) [lit-html CSS TemplateResult](https://lit-element.polymer-project.org/guide/styles) to be used in LitElement web components.



## Doc & demo

[https://lostinbrittany.github.io/granite-lit-bulma](https://lostinbrittany.github.io/granite-lit-bulma)



### Using `granite-lit-bulma`

To use *granite-lit-bulma* in an element:


#### 1. Install `granite-lit-bulma`


Install the component using [npm](https://www.npmjs.com/):

```sh
$ npm i @granite-elements/granite-lit-bulma --save
```


#### 2. Import *granite-lit-bulma* in the element where you want to use it


Once installed, import it in your application. Usually you will simply want to import `granite-lit-bulma.js` (wrap around `bulma.css`) or `granite-lit-bulma-min.js` (wrap around `bulma.min.css`).

Supossing you want to import `granite-lit-bulma.js`:
 
```
import bulmaStyle from '@granite-elements/granite-lit-bulma/granite-lit-bulma.js';
``` 

#### 3. Inside your component, use *granite-lit-bulma* in the static `styles` property


```js

class GraniteBulmaExample extends LitElement {
  static get styles() {
    return bulmaStyle;
  }
  render() {
    return html`
      <div class="label label-rounded label-primary">Styled text</div>
    `;
  }
```


#### A complete example

```js
import { html, LitElement } from 'lit-element';
import bulmaStyle from '../granite-lit-bulma.js';

class GraniteBulmaExample extends LitElement {
  static get styles() {
    return bulmaStyle;
  }
  render() {
    return html`
      <table class="table  table-hover">
          <tr><th>Surname</th><th>Name</th></tr>
          ${this.people.map( (person) => {
            return html`
            <tr>
              <td>${person.lastname}</td>
              <td>${person.firstname}</td>
            </tr>
            `;
          })}
      </table>
    `;
  }

  static get properties() {
    return {
      people: { type: Array },
    };
  }

  constructor() {
    super();
    this.people = [
      { firstname: 'Jack', lastname: 'Aubrey' },
      { firstname: 'Anne', lastname: 'Elliot' },
      { firstname: 'Stephen', lastname: 'Maturin' },
      { firstname: 'Emma', lastname: 'Woodhouse' },
    ];
  }
}
customElements.define('granite-bulma-example', GraniteBulmaExample);

```

## Contributing

1. Fork it!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -m 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request :D

## Install dependencies and run the demo

+   Run npm install from the repo directory:

    ```
     npm install
    ```
+   Run the Polymer development server from the root project directory:

    ```
    polymer serve --npm
    ```


## Note on semver versioning

I'm aligning the versions of this element with Bootstrap version, in order to make easier to choose the right version
 
## License

[Apache 2.0](http://www.apache.org/licenses/LICENSE-2.0)
