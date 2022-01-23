const obj1 = {
  "1": ["C", "F", "G"],
  "2": ["A", "B", "C"],
  "3": ["A", "B", "D"],
};

const obj3 = {
  "11": ["P", "R", "S", "D"],
  "53": ["L", "G", "B", "C"],
  "236": ["L", "A", "X", "G", "H", "X"],
  "432": ["A", "A", "B", "D"],
};
/*
result should be
{
      "11": ["P", "R", "S"],
      "53": ["C"],
      "236": ["L", "X", "G", "H"],
      "432": ["A", "B", "D"],
    });
*/

const obj4 = {
  '295': [ 'B', 'F', 'D', 'P', 'C', 'M', 'E' ],
  '323': [ 'P', 'X', 'N', 'F', 'Y', 'S', 'I', 'Q', 'G' ],
  '324': [ 'C', 'H', 'U', 'P' ],
  '356': [ 'J', 'J', 'K', 'F', 'B', 'Q', 'Q', 'U', 'H' ],
  '520': [ 'U', 'C', 'T', 'F', 'Q' ],
  '808': [ 'T', 'L', 'M', 'C', 'A', 'P' ],
  '914': [ 'K', 'Y', 'S', 'B', 'E', 'Y', 'R' ],
  '990': [ 'D', 'I', 'U', 'I', 'Y', 'A', 'Q', 'B', 'C' ] 
};

const obj5 = {
  '608': [ 'Q', 'Y', 'J', 'C', 'G', 'X', 'T', 'C', 'C' ],
  '917': [ 'W', 'B', 'U', 'G', 'A', 'D', 'R', 'M', 'G' ],
  '933': [ 'W', 'L', 'U', 'U', 'L' ] 
}

/*
should be
{ '608': [ 'Q', 'Y', 'J', 'C', 'X', 'T' ],
  '917': [ 'B', 'G', 'A', 'D', 'R', 'M' ],
  '933': [ 'W', 'L', 'U' ] }
*/


const removeDuplicateIds = (obj) => {
    console.log (obj);
    for (let key in obj){
        for (let key2 in obj){
            if (key != key2){
                for (let i = 0; i < obj[key].length; i++){
                    for (let i2 = 0; i2 < obj[key2].length; i2++){
                        console.log (`compare ${key} : ${obj[key][i]} to ${key2} : ${obj[key2][i2]}`);
                        if (obj[key][i] == obj[key2][i2]){
                          console.log ('*****Match found!*****');
                          if (Number(key) > Number(key2)){
                            console.log (`removing ${obj[key2][i]} from ${key2}`);
                            obj[key2].splice(i,1);
                            i--;
                          }else{
                            console.log (`removing ${obj[key][i]} from ${key}`);
                            obj[key].splice(i,1);
                            i--;
                          }
                        }
                    }
                }
            }
        }
    }
    //remove dupes within the same key
    for (let key in obj){
      for (let i1 = 0; i1 < obj[key].length; i1++){
        for(let i2 = obj[key].length - 1; i2 >= 0; i2--){
          if (i1 != i2 && obj[key][i1] == obj[key][i2]){
            obj[key].splice(i2,1);
          }
        }
      }
    }
    for (let key in obj){
      console.log (`${key}: ${obj[key]}`);
    }
    return obj;
};

removeDuplicateIds(obj5);




/*

const obj = {
  "1": ["A", "B", "C"],
  "2": ["A", "B", "D", "A"],
};
const result = removeDuplicateIds(obj);

const obj1 = {
  "1": ["C", "F", "G"],
  "2": ["A", "B", "C"],
  "3": ["A", "B", "D"],
};
const result1 = removeDuplicateIds(obj1);

const obj2 = {
  "1": ["A"],
  "2": ["A"],
  "3": ["A"],
};
const result2 = removeDuplicateIds(obj2);
        
const obj3 = {
  "432": ["A", "A", "B", "D"],
  "53": ["L", "G", "B", "C"],
  "236": ["L", "A", "X", "G", "H", "X"],
  "11": ["P", "R", "S", "D"],
};
const result3 = removeDuplicateIds(obj3);


describe("removeDuplicateIds",()=>{
  it("Example Tests",()=>{
    Test.assertDeepEquals(result, { "1": ["C"], "2": ["A", "B", "D"] });
    Test.assertDeepEquals(result1, { "1": ["F", "G"], "2": ["C"], "3": ["A", "B", "D"] });
    Test.assertDeepEquals(result2, { "1": [], "2": [], "3": ["A"] });
    Test.assertDeepEquals(result3, {
      "11": ["P", "R", "S"],
      "53": ["C"],
      "236": ["L", "X", "G", "H"],
      "432": ["A", "B", "D"],
    });
  });
});



You are given a table, in which every key is a stringified number, and each corresponding value is an array of characters, e.g.

{
  "1": ["A", "B", "C"],
  "2": ["A", "B", "D", "A"],
}
Create a function that returns a table with the same keys, but each character should appear only once among the value-arrays, e.g.

{
  "1": ["C"],
  "2": ["A", "B", "D"],
}
Rules
Whenever two keys share the same character, they should be compared numerically, and the larger key will keep that character. That's why in the example above the array under the key "2" contains "A" and "B", as 2 > 1.
If duplicate characters are found in the same array, the first occurance should be kept.
Example 1
input = {
  "1": ["C", "F", "G"],
  "2": ["A", "B", "C"],
  "3": ["A", "B", "D"],
}

output = {
  "1": ["F", "G"],
  "2": ["C"],
  "3": ["A", "B", "D"],
}
Example 2
input = {
  "1": ["A"],
  "2": ["A"],
  "3": ["A"],
}

output = {
  "1": [],
  "2": [],
  "3": ["A"],
}
Example 3
input = {
  "432": ["A", "A", "B", "D"],
  "53": ["L", "G", "B", "C"],
  "236": ["L", "A", "X", "G", "H", "X"],
  "11": ["P", "R", "S", "D"],
}

output = {
  "11": ["P", "R", "S"],
  "53": ["C"],
  "236": ["L", "X", "G", "H"],
  "432": ["A", "B", "D"],
}

*/