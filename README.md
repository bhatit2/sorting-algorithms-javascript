# sorting-algorithms-javascript
Implementation of sorting algorithms in javascript

*Selection Sort O(n2)*

`function selectionSort(arr){
	let min;
	let findMin = function(index){
		let min = {index : index, val : arr[index]};
        for(var i = index; i < arr.length; i++){
            if(arr[i] < min.val){
              min = { index : i, val : arr[i] }
            }
		    }
		return min;
	}
	for(let i= 0; i < arr.length; i++){
		min = findMin(i);
		let temp = arr[i]
		arr[i] = min.val;
		arr[min.index] = temp;
	}
	return arr;
}`
