# Collapsible Lists `RMWC Addon`

> Collapsible Lists present accordion style navigation elements to progressively reveal content.

- import from **'@rmwc/list'**;
- Import styles:
  - import **'@material/list/dist/mdc.list.css'**;
  - import **'@rmwc/list/collapsible-list.css'**;

Collapsible lists aren't part of the material spec, but they've been added to RMWC after continuing requests from the community. They present an accordion style navigation element to progressively reveal content. They've have been built to work with the `List` and `ListItem` components in regards to keyboard events and styling, but they technically be used with any kind of content.

```jsx render
import {
  List,
  SimpleListItem,
  CollapsibleList
} from '@rmwc/list';

<List>
  <CollapsibleList
    handle={
      <SimpleListItem
        text="Cookies"
        graphic="favorite"
        metaIcon="chevron_right"
      />
    }
    onOpen={() => console.log('open')}
    onClose={() => console.log('close')}
  >
    <SimpleListItem text="Chocolate Chip"/>
    <SimpleListItem text="Ginger Snap"/>
    <SimpleListItem text="Peanut Butter"/>
  </CollapsibleList>

  <CollapsibleList handle={
    <SimpleListItem text="Pizza" 
    graphic="local_pizza" metaIcon="chevron_right"/>
  }>
    <SimpleListItem text="Cheese"/>
    <SimpleListItem text="Pepperoni"/>
    <SimpleListItem text="Supreme"/>
  </CollapsibleList>

  <CollapsibleList handle={
    <SimpleListItem text="Icecream" 
    graphic="star" metaIcon="chevron_right"/>
  }>
    <SimpleListItem text="Vanilla"/>
    <SimpleListItem text="Chocolate"/>
    <CollapsibleList handle={
      <SimpleListItem text="Nested Collapsible" 
      graphic="touch_app" metaIcon="chevron_right"/>
    }>
      <SimpleListItem text="Orange"/>
      <SimpleListItem text="Strawberry"/>
      <SimpleListItem text="Blueberry"/>
    </CollapsibleList>
  </CollapsibleList>
  
  <CollapsibleList open handle={
    <SimpleListItem text="Custom Content, forced open" 
    graphic="help" metaIcon="chevron_right"/>
  }>
    
    <div style={{
      padding: '4rem',
      background: 'green',
      color: 'white'
    }}>Collapsibles can contain any content</div>
  </CollapsibleList>
</List>
```

## Usage as Non-List
`CollapsibleList` is optimized to work with the `List` component but there is nothing stopping you from using any other kind of content.

```jsx render
import { CollapsibleList } from '@rmwc/list';
import { IconButton } from '@rmwc/icon-button';
<CollapsibleList
  handle={<IconButton icon="favorite_outline" onIcon="favorite"/>}
  onOpen={() => console.log('open')}
  onClose={() => console.log('close')}
>
  <div style={{
    padding: '1rem',
    background: 'red',
    color: 'white',
    display: 'inline-block'
  }}>
    Favorited!
  </div>
</CollapsibleList>
```

```jsx renderOnly
import { Docs } from '@rmwc/base/utils/document-component';
import * as docs from './docgen.json';

<Docs src={docs} components={[
  'CollapsibleList'
]} />
```
