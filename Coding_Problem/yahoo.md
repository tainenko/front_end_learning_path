1-1: 修改once讓他只會log一次  
function once(){  
   console.log(‘hi)  
}  
once()  
once()  
once()  

Ans.  
1. 閉包  

            function once(fn) { 
                var result;
            
              return  function() { 
                    if(fn) {
                        result = fn.apply(this, arguments);
                        fn = null;
                    }
                    return result;
                };

2. 第一次調用後，把func清空，func= function(){};

        var func = function () {
            alert("正常调用");
            func= function(){};
        }
        func();
        func();
 

3. 設置flag，透過flag控制function的調用。

            var flag = true;

            function once() {
                if (flag) {
                    alert("我被调用");
                    flag = false;
                } else {
                    return;
                }
            }
            once();
            once();


1-2 改寫once，使之接受以下用法  
Const newOnce = once(word=>  
console.log(word))  
newOnce(‘hello’)  
newOnce(‘hello’)  
newOnce(‘hello’)  

2.給一正整數陣列n跟正整數target，如果任意兩整數相加等於target，就回傳一陣列存這兩個整數的index，例如n=[1,3,2,9],target=10就回傳[0,3]  
Ans.  
TwoSum  

3.有一個按鈕，點了會跳出popup，點popup背景可以關掉popup，寫HTML,CSS,JS  

4.有一組連續的數字，但沒有排序過，從1~10000，有一個數字有重複，問怎麼找出這個重複的數字。  
Ans.  
1. 數學法  
將array全部的數字累加，其結果減去1~10000的和，差值即為重複的數字。  
2. 遍歷  
只要array當前的index與value不相等，則做一次判斷，if arr[i]==arr[arr[i]]，如果兩者相等就是找到了重複的數字，如果不相等就交換兩者，繼續往下找。  

5.怎麼判斷Linked list裡面形成迴圈(最後一個node指向某個node而不是null)  
Ans.  
  使用兩個指標，快慢一起遍歷，如果快指標追上了慢指標，則linked list裡有迴圈，如果查找到node=null，則回報沒有迴圈存在。  

6.為什麼要用translate，比起position差別在哪？  

7.Display: inline 跟inline-block差別  

8.解釋CORS  

9.有做過什麼提升網站安全性，問XSS，CSRF  

10.平時開發時如何檢測效能。  

11.這裡的this是什麼？加上use strict後會是什麼？如何讓this指向obj  

function reveal(){  
console.log(this)  
}  
  
const obj={…}  
