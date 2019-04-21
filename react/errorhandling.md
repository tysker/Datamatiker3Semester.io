[**REACT**](react.md)



## Error Handling In React


### Simple error function to catch errors.

That will return the status of the error and the error message body. If the Promise is given, the function will return the fetched data.

    function handleHttpErrors(result) {
      if (!result.ok) {
        return Promise.reject({ status: result.status, fullError: result.json() });
      }
      return result.json();
    }
  
Eksample 1:

    // Return a promise that resolves, when fetch and subsequent thens are completed.
      getLabels = () => {
        return fetch("http://localhost:3333/labels")
          .then(handleHttpErrors)
          .then(data => (this.labels = data));
        //  .then((data) => { console.log("data:", data); this.labels = data});
      };
    
Eksample 2:

It also possible to catch the error at the end of the fetch line. The idear is, if anything goes wrong in one of our promises, the error will be submitet to our catch line and will be handeld there accordingly.

      function deleteButtonClickHandler(event){
        const catId = e.target.data['cat-id']
        deleteCat(catId)
        then(() => removeItemElementFromPage(catId))
        .catch(err =>
          showMessageDialog(
            'item ' + getCatName(catId) + ' was not deleted'))
      }
    
Eksample 3:

It is also possible to use a try catch and throw an error with an string/message.

    <script>
            function myFunction() {
                var message, x;
                message = document.getElementById("p01");
                message.innerHTML = "";
                x = document.getElementById("demo").value;
                try {
                    if (x == "") throw "empty";
                    if (isNaN(x)) throw "not a number";
                    x = Number(x);
                    if (x < 5) throw "too low";
                    if (x > 10) throw "too high";
                } catch (err) {
                    message.innerHTML = "Input is " + err;
                } finally {
                    document.getElementById("demo").value = "";
                }
            }
        </script>
