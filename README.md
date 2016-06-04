# react-relay-redux

> Redux integration for Relay


## Overview

`react-relay-redux` lets you listen and respond to Relay
queries and mutations using Redux actions and reducers.

Eventually I want to look into how you can possibly dispatch queries/mutations directly using Redux actions, but that is a WIP.

## Install

```
$ npm install --save react-relay-redux
```


## Usage


#### `RegisterRelayDispatcher`

`react-relay-redux` exports a `RelayNetworkDispatch` function that
takes your Relay environment and a `dispatch` function for your
Redux store.

```js
import Relay from 'react-relay'
import {RegisterRelayDispatcher} from './react-relay-redux'
import store from 'your-redux-store'

/* register a network subscriber */
RegisterRelayDispatcher(Relay.Store, store.dispatch)

/* then pass it to your renderer or root container */
<Relay.Renderer
  environment={Relay.Store}
  ...

```

#### `RelayReduxActions`

You can import and use the following actions:

* `RELAY_QUERY` - when a Relay query is issued
* `RELAY_QUERY_SUCCESS` - when a Relay query is successful
* `RELAY_MUTATION` - when a Relay mutation is issued
* `RELAY_MUTATION_SUCCESS` - when a Relay mutation is successful


## Coming Soon

* `RELAY_{QUERY,MUTATION}_FAILURE` support
