# DataStructure
王道2023数据结构综合应用题（node.js）解法
对应题号，可以使用Ctrl+F跳转到对应章节

# 2.2.3(Page 18)

- 01.由顺序表中删除具有最小值（假设唯一）并由函数返回被删元素的值，空出的位置由最后一个元素填补，若顺序表为空，则显示出错信息并退出运行。
 
```JavaScript
function deleteElement(arr) {
    if (arr.length == 0) {
        return "数组为空！";
    } else {
        var tag = arr[0];
        var tagIndex = 0;
        for (var i = 0; i < arr.length; i++) {
            if (tag >= arr[i]) {
                tag = arr[i];
                tagIndex = i;
            }
        }
        arr[tagIndex] = arr[arr.length-1];
        return arr;
    }
}

//console.log(deleteElement([]));
```

- 02.设计一个高效算法，，将顺序表L的所有元素逆置，要求算法的空间复杂度为O(1)

```javascript
function reverse(arr){
    if(arr.length==0){
        return "数组为空！";
    }else if(arr.length>0&&arr.length%2==1){
        var middle = (arr.length+1)/2;  //获取中间位置
        var rear = arr.length;  //尾指针
        for(var i=0;i<middle;i++){
            var temp = arr[i];
            arr[i] = arr[rear-i-1];
            arr[rear-i-1] = temp;
        }
        return arr;
    }else if(arr.length>0&&arr.length%2==0){
        var middle = arr.length/2;  //获取中间位置
        var rear = arr.length;  //尾指针
        for(var i=0;i<middle;i++){
            var temp = arr[i];
            arr[i] = arr[rear-i-1];
            arr[rear-i-1] = temp;
        }
        return arr;
    }
}

// console.log(reverse([]));
// console.log(reverse([1,2,3]));
// console.log(reverse([1,2,3,4,5,6]));
```

- 03.对长度为n的顺序表L，编写一个时间复杂度为O(n)，空间复杂度为O(1)的算法，该算法删除线性表中所有值为x的数据元素

```javascript
function deleteAllx(arr,x){
    var count = 0;
    for(var i=0;i<arr.length;i++){
        if(arr[i]!=x){
            arr[count]=arr[i];
            count++;
        }else{
            continue;
        }
    }
    arr.length = count;
    return arr;
}

//console.log(deleteAllx([1,1,1,1,1,1,2,3,2,5,6],1));
```
