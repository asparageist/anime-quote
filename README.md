1. Plan for day:

- understand how to use api

## API Docs overview

UI/Business, Service (API Calls) -> Weather Service class is in the service layer
correct api call: <URL>
CORS?: Cross-Origin Resource Sharing?
How is the response structured? -> copy/paste the url on postman
Do we need auth? What kind? - API Key: - Free Version?

```js
`https://animechan.xyz/api/random/character?name=${character_name}`;

const response = {
  anime: "One Piece",
  character: "Monkey D. Luffy",
  quote: "Being alone is more painful than getting hurt.",
};

const quote = response[quote];
//store in p#result

//Luffy
//Eren Yaeger
//Edward Elrich
//Light Yagami
```

get quote from server given name
query server in proper syntax

business logic: do something with the API response

UI:

- handle user input
- displays results

service logic - send a request to the server --> return JSON api response based UI option

```js
export default class WeatherService {
  static async getWeather(city) {
    try {
      const response = await fetch(
        `http://api.openweathermap.org/data/2.5/weather?q=${city}&appid=${process.env.API_KEY}`
      );
      const jsonifiedResponse = await response.json();
      if (!response.ok) {
        const errorMessage = `${response.status} ${response.statusText}
        ${jsonifiedResponse.message}`;
        throw new Error(errorMessage);
      }
      return jsonifiedResponse;
    } catch (error) {
      return error;
    }
  }
}
```

linked list: pointer (variable that stores a memory address)

array.forEach(function(element){
array[index] = //whatever you want to change
})

at reference, at value

At value makes a copy of the array
At reference changes the value "in-place"

const array = [4,5,1,3]
array.sort()

console.log(array); -> [1,3,4,5];

the location in memory of your data

int [-10^28 and 10^28] -> // 2s complement

int\* = myPointer;

fEx37362;

1. we can access the memory location of data using pointers

Arrays in memory
[1,3,4,5] -> 0 1
1 [1] [3] [4] [5]

console.log(array[0]) -> 1

Replacement is complicated

array[1] = '';
array[1] = 5;

     Node [int (pointer)]

     -> next node in the list

int [pointer to int2] -> int2[pointer to int3] int3[pointer to int 4] int4[null]

getLength
node only returns data and pointer to next data;

class LinkedList{
constructor(data){
this.next= fE34342x;
this.data = data;
}
}

5 [hEx4453] -> 7 [null]

9 [null]

1. copy memory address of 9, put it in the next property of 5
2. copy memory address of 7, put it into the next property of 9

5[hex772] -> 9[hEx4453] -> 7[null]

data structures are pre-written solutions to common problems in cs
