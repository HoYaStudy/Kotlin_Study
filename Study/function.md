# Function

Kotlin의 함수는 `fun` keyword를 사용하여 선언하며, 다음과 같은 구조로 되어있다.

```kt
/*
<Visibility Modifier> fun <Function Name>(<Parameters>): <Return Type> {
	expressions
}
*/

private fun testFunction(value: Int): String {
	return "Passed"
}
```

### Visibility Modifier

함수의 유효 scope를 설정한다.

* `private`: C언어의 static keyword와 유사하게 같은 file내에서만 사용할 수 있도록 한다.
* `public`: 다른 kotlin file에서도 사용할 수 있도록 한다.

### Parameter

함수의 내부에서 사용할 data의 이름과 type을 지정한다.

#### Default Arguments

다음과 같이 default arguments value를 지정할 수 있다.

```kt
private fun testFunction(value: Int = 1): String {
	return "Passed"
}
```

### Named Arguments

함수에 인자를 전달할 때, 이름과 함께 전달을 할 수 있다.

이를 사용하면 정의된 인자의 순서와 상관없이 caller가 원하는 순서로 인자를 전달할 수 있으며, 가독성을 높일 수 있다.

```kt
testFunction(value = 3)
```

## Single-Expression Functions

단일 표현식을 갖는 함수에서는 `return type`, `{ }`, `return statement`를 모두 생략할 수 있다. 또, 함수의 뒤에 `=` operator와 expression을 붙여 표현한다.

```kt
private fun testFunction(value: Int = 1) = println("Passed")
```

## Unit-Returning Functions

Kotlin에서는 return type과 return statement가 없는 함수를 Unit 함수라고 한다.

C 언어 등은 이런 함수를 위해 `void`를 return type으로 사용을 하지만, 이는 return type이 없으므로 생략한다는 의미이고, generic을 처리하기 어렵게 만든다. Kotlin에서는 이런 문제를 해결하기 위하여 `Unit`이란 return type을 지정하여 해결한다.

### `Nothing` Type

`Unit` type과 유사하지만, caller code로 제어권이 복귀되지 않는다는 차이점이 있다.

의도적으로 exception을 발생시킬 때 주로 사용된다. 예를 들어, kotlin standard library에 있는 `TODO` 함수가 사용하고 있다.

## Function Overloading

함수의 이름은 같지만 parameter의 개수나 type이 다른 여러 개의 함수로 구현하는 것이다.

```kt
private fun testFunction() {
	println("Testing")
}

private fun testFunction(value: Int) {
	println("Passed")
}

private fun testFunction(value: Int, description: String) {
	println("Failed")
}

testFunction()
testFunction(3)
testFunction(2, "First test")
```

## Backtick Function Name

Kotlin에서는 backtick symbol을 사용해서 함수의 이름을 정의하고 호출할 수 있다.

```kt
fun `this is a function name`() {

}

`this is a function name`()
```

이 기능은 다음의 목적으로 주로 사용한다.

1. Java와의 상호운용을 가능하게 해준다.
2. code를 test하는 file에서 사용되는 함수 이름을 더 알기 쉽게 나타낸다.
