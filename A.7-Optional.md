# Optional

	class Message {
	
		var message1: String = "i am message1"
		var message2: String? // 使用 optional, 值為 nil
	
	}

## Why useing Optional

> Swift 為了安全性考量使用 Optional
> 使用 Object-c 時回傳 nil 其值在做後續處理時會發生錯誤

	func findCode(name: String) -> String? {
	
		if name == "rock" {
			return "value1"
		} else if name == "sam" {
			return "value2"
		}
		
		return nil
	
	}	
	
	var code:String? = findCode("claire")
	let text = "Hello - "

> error

	let message = text + code // error
	print(message)

## Unwrapping Optionals

> 處理 nil

	if code != nil {
		let message = text + code
	}

> 使用 ! 來 unwrap Optional, 但要確保包含一個值

	let message = text + code!
	
## Optional Binding

	var code:String? = findCode("claire")
	let text = "Hello - "
	
	if let tmpCode = code { // 如果 code 有包含一個值，解開它，並設定給 tmpCode，然後執行條件式
		let message = text + tmpCode
		print(message)
	}
	
## Optional Chaining

	class Stock {
		var code: String?
		var price: Double?
	}
	
	func findStockCode(company: String) -> Stock? {
	
		if company == "Apple" {
		
			let aapl: Stock = Stock()
			aapl.code = "AAPL"
			aapl.price = 90.32
			
			return appl
			
		} else if company == "Google" {
		
			let goog: Stock = Stock()
			goog.code = "GOOG"
			goog.price = 556.36
			
			return goog
			
		}
	
		return nil
	
	}
	
> 不使用 Optional Chaining

	// findStockCode 回傳值為 Optional, 使用 Optional Unwrapping 解開
	if let stock = findStockCode("Apple") {
		if let price = stock.price { // stock.price 為 optional
			let cost = price * 100
			print(cost)
		}
	}
	
> 使用 Optional Chaining

> 使用 ?. 鏈結起來

	if let price = findStockCode("Apple")?.price {
		let cost = stock.price * 100
		print(cost)
	}
	
## 可失敗化初始器 Failable Initializers

	if let myFont = UIFont(name : "Somefont", size: 22.0) {
		// 初始化失敗後要處理的程序
	}