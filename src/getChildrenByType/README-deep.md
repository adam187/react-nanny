

<h2>getChildrenByTypeDeep&lt;T=React.ReactNode, TC=unknown&gt;</h2>
<p>Gets all children by specified type (deep search)</p>
<p>Since v1.0.0 (modified v2.0.0)</p>
<table>
      <thead>
      <tr>
        <th>Param</th>
        <th>Type</th></tr>
      </thead>
      <tbody><tr><td><p><b>children</b></p>JSX children</td><td>T</td></tr><tr><td><p><b>types</b></p>Types of children to match</td><td>TC | TC[]</td></tr><tr><td><p><b>{ customTypeKey: '__TYPE' } <span>(optional)</span></b></p>The configuration params</td><td>GetChildrenByTypeConfig</td></tr></tbody>
    </table><p><b>Returns:</b> {T[]} - Array of matching children</p><blockquote><p>This function will check the prop <em>{customTypeKey}</em> first and then <em>component.type</em> to match core html (JSX intrinsic) elements or component functions. To find a React Fragment, search for <em>'react.fragment'</em>.</p></blockquote><h4>Supporting Types</h4>

```
// The configuration type for the util:
//   customTypeKey?: string = '__TYPE' - The custom component prop key to check the type

export type GetChildrenByTypeConfig = { customTypeKey?: string };
```
  <h4>Import</h4>

```
import { getChildrenByTypeDeep, GetChildrenByTypeConfig } from 'react-nanny';
```

  <blockquote><p><em>GetChildrenByTypeConfig</em> is a TypeScript type and is only for (optional) use with TypeScript projects</p></blockquote><h4>Examples</h4>





```    
// Finds all occurrences of ToDo (custom component), div, and React Fragment
getChildrenByTypeDeep(children, ['ToDo', 'div', 'react.fragment']);

// Finds all occurrences of MyComponent (custom component - full component passed in), a div, and React Fragment
import MyComponent from './MyComponent';
getChildrenByTypeDeep(children, [MyComponent, 'div', 'react.fragment']);

// Finds all occurrences of ToDo (custom component) with a customized {customTypeKey}
getChildrenByTypeDeep(children, ['ToDo'], { customTypeKey: 'myTypeKey' });
```

    