[**REACT**](react.md)



## AXIOS.js

**Install Axios to your project**

    npm install axios

**Import Axios to your Componment**

    import Axios from "axios";

Axios is a Javascript library used to make http requests from node.js or XMLHttpRequests from the browser and it supports the Promise API that is native to JS ES6. Another feature that it has over .fetch() is that it performs automatic transforms of JSON data.

    const url = 'https://api.spotify.com/v1/artists/0OdUWJ0sBjDrqHygGUXeCF'
    axios.get(url).then(response => console.log(response));

**Error Handling**

    const url = 'https://api.spotify.com/v1/artists/0OdUWJ0sBjDrqHygGUXeCFcdsds';
    fetch(url).catch(error => console.log('BAD', error)).then(response => console.log('GOOD', response));
    
    
