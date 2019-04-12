[**REACT**](react.md)


## Handling Events


* React events are named using camelCase, rather than lowercase.
* With JSX you pass a function as the event handler, rather than a string.

In Html you would handle events like that:

      <button onclick="activateLasers()">
      Activate Lasers
    </button>
    
In React:

    <button onClick={activateLasers}>
      Activate Lasers
    </button>
