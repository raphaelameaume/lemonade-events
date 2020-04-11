# lemonade-events

`lemonade-events` is a minimal event system. The implementation is based on [mitt](https://github.com/developit/mitt) with a few changes:
- It returns the unsuscribe function on subscribe
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

let event = '@example / EVENT_NAME';

// subscribe to an event
let eventListener = EventBus.on(event, (data) => {
    console.log(data); // { someData: true }
});

// emit an event
EventBus.emit(event, { someData: true });

// unsubscribe to event
eventListener();
// or
EventBus.off(event);
```

You can also create an instance of EventBus by yourself if you don't want to use the global one

```js
import { EventBus } from "lemonade-helpers";

let eventBus = EventBus();

// eventBus.on, eventBus.off, eventBus.on

```

## Credits
- [mitt](https://github.com/developit/mitt)

## License

MIT License, see [LICENSE](https://github.com/raphaelameaume/lemonade-events/tree/master/LICENSE) for details