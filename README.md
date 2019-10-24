# sorting-algorithms-javascript
#### Implementation of sorting algorithms in javascript

### Selection Sort O(n2)

```
function selectionSort(arr){
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
}
```
### Bubble Sort O(n2)

```
function bubbleSort(arr){
for(var i = 0; i < arr.length; i++){
	for(var j = 0; j < arr.length-i; j++){
		if(arr[j] > arr[j + 1]){
			let temp = arr[j];
			arr[j] = arr[j + 1];
			arr[j + 1] = temp;
		}
	}
}
return arr;
}
```

### Merge Sort O(nlogn)

#### Merge function
```
function merge(listA, listB) {
    let res = [];
    let i = 0, j = 0;
    while (i < listA.length || j < listB.length) {
        if (i === listA.length) {
            let remainingArr = listB.splice(j);
            return res.concat(remainingArr);
        }
        if (j === listB.length) {
            let remainingArr = listA.splice(i);
            return res.concat(remainingArr);
        }
        if (listA[i] < listB[j]) {
            res.push(listA[i])
            i++
        } else {
            res.push(listB[j])
            j++
        }
    }
    return res;
}
```
#### Merge Sort
```
function mergeSort(arr) {
  if (arr.length < 2) {
    return arr; }
  else {
    var midpoint = parseInt(arr.length / 2);
    var leftArr   = arr.slice(0, midpoint);
    var rightArr  = arr.slice(midpoint, arr.length);
    return merge(mergesort(leftArr), mergesort(rightArr));
  }
}
```
