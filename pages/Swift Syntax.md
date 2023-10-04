tags:: [[Swift]]
---

-
- ## print (打印)
	- ``` swift
	  print("Hello, world!")
	  ```
- ## Simple Values (简单值)
	- ### let 与 var 的使用
		- `let` 关键字定义 **常量(constant)** , 在程序中必须赋一次值 (如果没用到的话, 不赋值也可以)，且只能赋一次值 .
		- `var` 关键字定义 **变量(variable)** .
		- ``` swift
		  var myVariable = 42
		  myVariable = 50
		  let myConstant = 42
		  ```
	- ### 常量与变量的类型
		- 无需 **显式(explicitly)** 指定 **常量或变量** 的类型, **编译器** 可以通过赋值来推断其类型 .
		- **变量或常量** 如果在声明时未被赋值的话，则必须 显式 声明其类型。
		- 一个变量被赋的多个值的类型, 必须一致 .
		- ``` swift
		  // 显式声明 常量 的类型。
		  let explicitDouble: Double = 70
		  ```
		- 一个类型从来不会被 **隐式地(implicitly)** 转换成另一种类型，必须 显式地 转换 .
		- ``` swift
		  let label = "The width is "
		  let width = 94
		  let widthLabel = label + String(width)
		  ```
	- ### 将 value 转成 String
		- 使用 `\(变量名)` 将值转成字符串。
		- ``` swift
		  let apples = 3
		  let oranges = 5
		  let appleSummary = "I have \(apples) apples."
		  let fruitSummary = "I have \(apples + oranges) pieces of fruit."
		  ```
	- ### 三个双引号
		- 使用 **三个双引号** 可以定义多行字符串 .
		- ``` swift
		  let apples = 3
		  let oranges = 5
		  let quotation = """
		         Even though there's whitespace to the left,
		      the actual lines aren't indented.
		              Except for this line.
		          Double quotes (") can appear without being escaped.
		  
		          I still have \(apples + oranges) pieces of fruit.
		      """
		  print(quotation)
		  ```
		- 实际的字符串的值，将会忽略与 结尾 `"""`保持一致 **缩进** 的行的前面的缩进；其他行，都会参照结尾 `"""` 保留相应的缩进。
	- ### array (数组)
		- 数组大小会根据元素的增加 (使用 `append()` 方法) 而增大 .
		- ``` swift
		  var shoppingList = ["catfish", "water", "tulips", "blue paint"]
		  shoppingList[1] = "bottle of water"
		  
		  shoppingList.append("apples")
		  print(shoppingList)
		  
		  shoppingList[4] = "bananas"
		  
		  print(shoppingList)
		  ```、
		- 空数组: `shoppingList = []` .
		- 数组类型是这样声明的
			- ``` swift
			  let emptyArray: [String] = []
			  ```
	- ### dictionary (字典)
		- ``` swift
		  var occupations = [
		      "Malcolm": "Captain",
		      "Kaylee": "Mechanic",
		  ]
		  occupations["Jayne"] = "Public Relations"
		  ```
		- 空字典: `occupations = [:]` .
		- 字典类型是这样声明的
			- ``` swift
			  let emptyDictionary: [String: Float] = [:]
			  ```
- ## Control Flow (控制流)
	-
	-