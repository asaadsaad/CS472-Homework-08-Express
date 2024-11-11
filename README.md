## CS472-Homework-08-Express

## Exercise 01
Write an Express application to provide a calculator API. 
* There should be an API endpoint for each basic math operation: `addition`, `subtraction`, `multiplication`, `division`, and `modulus`. 
* Each endpoint will receive the input numbers and return a JSON response with the results as follows: `{results: number}`. 
* The calculator router should be designed with flexibility to receive the input numbers as query parameters, parameters, or in the body as JSON or urlEncoded format, For example, all of these requests will return the same results value `{results: 5}`:
  * `GET /addition/2/3`
  * `GET /addition/?a=2&b=3`
  * `POST /addition/` BODY `?a=2&b=3`
  * `POST /addition/` BODY `{a:2,b:3}`
* Use [morgan](https://www.npmjs.com/package/morgan) and print a log of all incoming requests to the console.
* Use [cors](https://www.npmjs.com/package/cors) and allow cross-origin requests to be shared.
  
## Exercise 02
This application reads/writes the state from/to [node-localstorage](https://www.npmjs.com/package/node-localstorage) which is used as a form of data storage. Create the following API end points as follows:
* `POST /numbers/:n` for saving a input number, return the all saved numbers as a JSON. For example
  * `POST /numbers/1` -> `{ results: [1] }`
  * `POST /numbers/2` -> `{ results: [1,2] }`
  * `POST /numbers/5` -> `{ results: [1,2,5] }`
* `GET /numbers`, return the array of saved numbers -> `{ results: [1,2,5] }`
* `GET /numbers/:index`, return the array value at specified index
  * `GET /numbers/0` -> `{ results: 1 }`
  * `GET /numbers/1` -> `{ results: 2 }`
  * `GET /numbers/2` -> `{ results: 5 }`
* `DELETE /numbers/:n`, remove the number in the array
  * `DELETE /numbers/1` -> `{ results: [2,5] }`
  * `DELETE /numbers/2` → `{ results: [5] }`
* `PUT /numbers/:n1/:n2`, change the number in the array
  * `PUT /numbers/5/10` -> `{ results: [10] }`
