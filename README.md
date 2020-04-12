# lemonade-events

`lemonade-events` is a minimal event system. The implementation is based on [mitt](https://github.com/developit/mitt) with a few changes:
- It returns the unsuscribe function on subscribe to avoid keeping a reference of the listener function
- It has a log mode for development
- It exports an eventBus by default

## Installation

`npm install lemonade-events`

## Usage

```js
// import the full instance
import EventBus from "lemonade-events";
// or import only needed methods
import { on, emit } from "lemonade-events";

EventBus.log = true;

let e = '@example / EVENT_NAME';

// subscribe to an event
function listener(data) {
    console.log(data); // { someData: true }
}

let eventListener = EventBus.on(e, listener);

// add subscription
EventBus.emit(e, { someData: true });

// remove subscription
eventListener();
// or
EventBus.off(e, listener);
```

You can also create an instance of EventBus by yourself if you need.

```js
import { EventBus } from "lemonade-helpers";

let eventBus = EventBus();

// local instance
eventBus.on();
eventBus.emit();
```

## Credits
- [mitt](https://github.com/developit/mitt)

## License

MIT License, see [LICENSE](https://github.com/raphaelameaume/lemonade-events/tree/master/LICENSE) for details