# Move Zeroes
Given an integer array nums, move all 0's to the end of it while maintaining the relative order of the non-zero elements.You must do this in-place without making a copy of the array. Minimise the total number of operations.

```javascript

function moveZeroes(arr) {
    let insertPos = 0;
    
    // Step 1: Shift non-zero values forward
    for (let i = 0; i < arr.length; i++) {
        if (arr[i] !== 0) {
            arr[insertPos] = arr[i];
            insertPos++;
        }
    }
    
    // Step 2: Fill the rest with zeros
    while (insertPos < arr.length) {
        arr[insertPos] = 0;
        insertPos++;
    }
    
    return arr;
}
let array = [1, 1, 0, 0, 23];console.log(moveZeroes(array));
```


  Follow-up ChallengeCould you minimise the total number of write operations? (Hint: Consider swapping elements instead of rewriting them twice).
  ```javascript
function moveZeroesOptimized(nums) {
    let insertPos = 0;
    
    for (let i = 0; i < nums.length; i++) {
        if (nums[i] !== 0) {
            if (i !== insertPos) {
                // Swap elements
                let temp = nums[i];
                nums[i] = nums[insertPos];
                nums[insertPos] = temp;
            }
            insertPos++;
        }
    }
    return nums;
}

// Test
let array = [1, 1, 0, 0, 23];
```
