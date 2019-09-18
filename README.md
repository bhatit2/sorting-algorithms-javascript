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
function merge(listA, listB){
	let res = [];
	let i = 0 ,j = 0;
        while(i < listA.length || j < listB.length){
			if(i === listA.length){
				res.push(...listB.splice(j));
				break;
			}
			if(j === listB.length){
				res.push(...listA.splice(i));
				break;
			}
			if(listA[i] < listB[j]){
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
function mergeSort(arr){
	if(arr.length > 1){ 
		var mid = parseInt(arr.length/2);
        var leftArr = mergeSort(arr.slice(0,mid));
        var rightArr = mergeSort(arr.slice(mid, arr.length));
        return merge(leftArr, rightArr); 
	} else {
		return arr;
	}
}
```
