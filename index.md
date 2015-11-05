---
layout: default
title: Home
---

Easy Search is a simple and flexible solution for adding Search Components to your Meteor App. Read the documentation to [get started](getting-started).

```javascript
// On Client and Server
let Players = new Mongo.Collection('players'),
  PlayersIndex = new EasySearch.Index({
    collection: Players,
    fields: ['name'],
    engine: new EasySearch.MongoDB()
  });
```

```javascript
// On Client
Template.searchBox.helpers({
  playersIndex: () => PlayersIndex
});
```

```html
{% raw %}
<template name="searchBox">
    {{> EasySearch.Input index=playersIndex }}
    <ul>
        {{#EasySearch.Each index=playersIndex }}
            <li>Name of the player: {{name}}</li>
        {{/EasySearch.Each}}
    </ul>
</template>
{% endraw %}
```

Check out the [searchable leaderboard example](https://github.com/matteodem/easy-search-leaderboard) for a project implemented with EasySearch.

## How to install

```sh
cd /path/to/project
meteor add easy:search
```