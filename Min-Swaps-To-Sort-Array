/** 
 * Calculates the minimum number of swaps to sort an input array in ascending or descending order.
 * 
 * @param {[Number]} arr - The array of numbers to be sorted.
 * @param {String} dir - The direction of sorting: 'asc' for ascending, 'des' for descending (default: 'asc').
 * @return {Number} Minimum number of swaps to sort the array.
 */
function minSwapsToSort(arr, dir = 'asc') { // Time: O(n*log(n)), Space: O(n)
    let swaps = 0;

    // Create an array of objects with value and original index
    const sortedArr = arr.map((val, idx) => ({ val, idx }));

    // Sort array based on values in the given direction
    if (dir === 'des') {
        sortedArr.sort((a, b) => b.val - a.val);
    } else {
        sortedArr.sort((a, b) => a.val - b.val);
    }

    for (let i = 0; i < sortedArr.length; i++) {
        const curr = sortedArr[i];

        // If the current element is already in its correct position, skip it
        if (curr.idx === i) continue;

        // Swap the current element with the element at its original index
        const toSwapWith = sortedArr[curr.idx];
        [sortedArr[i], sortedArr[curr.idx]] = [toSwapWith, curr];

        
        swaps++;  // Increment swap count
        i--;      // Decrement index to recheck the current position after the swap
    }

    return swaps;
}

// To test and display results
function testMinSwapsToSort() {
    const arr = [0.5, 4, 2, 3, 1, -3, 0, 1.2];
    console.log('Unsorted Array:', arr, '\n');

    console.log('Sorted Array (ascending):', [...arr].sort((a, b) => a - b));
    console.log('Minimum number of swaps to sort ascending:', minSwapsToSort(arr), '\n');

    console.log('Sorted Array (descending):', [...arr].sort((a, b) => b - a));
    console.log('Minimum number of swaps to sort descending:', minSwapsToSort(arr, 'des'), '\n');

    console.log('============================================================================');
}

// Run tests
testMinSwapsToSort();
