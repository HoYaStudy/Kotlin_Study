# Control Flow

## if Expression

```kt
// if (condition) {
//   statement
// } else if (condition) {
//   statement
// }
```

## When Expression

다른 language의 switch-case expression과 같은 기능을 한다.

```kt
// when (condition) {
//   pattern -> statement
//   pattern -> statement
//   ...
// }
```


## Ranges

Kotlin에는 range operator와 range function이 있다.

`..` operator를 사용하여 range를 나타내며, ***from..to***와 같은 형태로 사용한다.

`in` keyword를 사용하여 조건식 등에서 range에 포함되는지를 check할 수도 있다.

`downTo` function은 감소되는 값의 range를 생성한다.

`until` function은 상한값을 제외한 range를 생성한다.
