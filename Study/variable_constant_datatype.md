# Variable, Constant and Data Type

Kotlin은 `static type system`을 사용하므로, 변수 선언 시 지정한 data type에 맞는 값을 대입해야한다.

Kotlin은 `type inference`를 지원하므로, 변수 선언 시 초기값을 지정할 경우 data type을 생략하더라고 값에 의해 type을 추론할 수 있다.

## Variable

변수의 생성은 다음과 같이 한다.

```kt
// var <name>: <data type> = value
```

## Constant

상수의 생성은 다음과 같이 한다.

```kt
// val <name>: <data type> = value
```

다만, val의 경우 완전한 상수는 아니다. 일부 예외 경우가 있기 때문이다. 따라서 완전한 상수의 사용을 원한다면 compile-time 상수를 사용해야한다.

Compile-time 상수의 경우 program 실행 전에 compiler가 알아야 하므로, 다음의 primitive built-in type으로 선언되어야 하며, 모든 함수의 외부에 정의되어야 한다.

* Boolean
* Char
* String
* Byte
* Short
* Int
* Long
* Float
* Double

```kt
// const val <name>: <data type> = value
```

## Data Type

### Kotlin Built-In Type

Type      | Description
----------|----------------------------------------------------------
`Boolean` | `true` or `false`.
`Char`    | Single character.
`String`  | 문자열 data.
Byte      | 8 bits 정수.
Short     | 16 bits 정수.
`Int`     | 32 bits 정수.
Long      | 64 bits 정수.
Float     | 32 bits 부동 소수점 실수.
`Double`  | 64 bits 부동 소수점 실수.
`List`    | 값을 요소로 저장하는 collection.
`Set`     | 고유한 값을 요소로 저장하는 collection.
`Map`     | key와 value의 pair로 요소를 저장하는 collection.

#### Character

Single quote를 붙여 character를 표현하며, 다음의 character들은 escape해야한다.

> \t, \b, \n, \r, \\', \\", \\\\, \\$

Unicode의 경우 다음과 같이 unicode escape를 사용한다.

> \uFF00

Double quote를 붙여 문자열을 표현한다.

다음과 같이 double quote 3개를 붙여 raw string을 표현한다.

```kt
var text = """
	This is a string.
""".trimMargin()
```

#### Number

Int의 최대값을 초과하지 않는 초기값을 가진 변수는 type inference에 의해 `Int`가 되며, 초과할 경우 `Long`이 된다.

##### Literals

* 값에 suffix `l` 또는 `L`을 붙여 `Long`을 명시할 수 있다.
* 값에 suffix `f` 또는 `F`을 붙여 `Float`을 명시할 수 있다.
* 값에 suffix `u`, `ul`, `U` 또는 `UL`를 붙여 unsigned integer를 명시할 수 있다.

실수를 초기값으로 갖는 변수는 type inference에 의해 `Double`이 된다. Kotlin의 실수는 [IEEE 754 standard](https://en.wikipedia.org/wiki/IEEE_754)를 따른다.

#### Array

Kotlin의 array에는 `Array` class와 `IntArray` 등과 같은 primitive type의 array가 있다.

Kotlin의 `Array`는 불변성을 갖고 있다. 즉, 한 번 지정한 type을 중간에 변경할 수 없다.
