# Power of JSON.Stringify

The `JSON.stringify` method converts a JavaScript object into a string

    const  obj = { name:  "Semsem", age:  29, city:  "Berlin"  };
    const strObj = JSON.stringify(obj);


> The result will be a string following the JSON notation.

**The new information for me [The Second Argument]**  

 - You can pass an array of strings
  `const strObj = JSON.stringify(obj,['name']); 
  // result: "{"name":"Semsem"}"`
  
  - You can pass method to replace text 
	  ```
	  JSON.stringify(obj, (key, value) => {
	  if (key==='age' && value > 18) {
	    return '18+'
	  }
	  return value;
	})
	// result "{"name":"Semsem","age":"18+","city":"Berlin"}"
	```

  - You can pass method to filter 
	  ```
	  JSON.stringify(obj, (key, value) => {
	  if (key==='age' && value > 18) {
	    return undefined
	  }
	  return value;
	})
	// result "{"name":"Semsem","city":"Berlin"}"
	```



**The second new information for me [The Third Argument]**  
	The third argument controls the spacing in result and this arrangement  can be (number | string)
	

  ```
  strObj = JSON.stringify(obj,null,2); //number
  // result  
  "{
  "name": "Semsem",
  "age": 29,
  "city": "Berlin"
}"
 strObj = JSON.stringify(obj,null,4);
 //result 	
 "{
    "name": "Semsem",
    "age": 29,
    "city": "Berlin"
}"

 strObj = JSON.stringify(obj,null,'=>');
 //result 	
"{
=>"name": "Semsem",
=>"age": 29,
=>"ci
  ```
