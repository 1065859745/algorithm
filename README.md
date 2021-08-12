# 模拟几个人投掷骰子，点数最大的获胜，若点数最大的人数大于一个人，点数最大的这几个人重新投掷骰子，直到点数最大的人数只有一个人
```
var a = [{name:"a"},{name:"b"},{name:"c"}]
        
function getBigger(arr) {
let bigger = []
        for (let i = 0; i < arr.length; i++) {
            arr[i].dice = parseInt(Math.random()*6+1)
            console.log(`${arr[i].name}获得${arr[i].dice}点`)
        }
        for (let i = 0; i < arr.length; i++) {
            let isBigger = true
            for (let j = i + 1; j < arr.length; j++) {
                if (arr[i].dice < arr[j].dice) {
                    isBigger = false
                    i = j -1
                    bread
                }
            }
            if (isBigger) {
                bigger.push(arr[i])
                break
            }
        }
        for (let i = 0; i < arr.length; i++) {
            if (bigger[0].dice == arr[i].dice && bigger[0].name != arr[i].name) {
                bigger.push(arr[i])
            }
        }
console.log(bigger)
        if (bigger.length > 1) {
            getBigger(bigger)
        } else {
            console.log(`${bigger[0].name}的${bigger[0].dice}点最大`)
        }
}
getBigger(a)
```
