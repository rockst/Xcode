# 例外處理 Exception

> Try / throw / catch

	let request = NSURLRequest(URL: NSURL(string: "http://www.apple.com")!)
	var response:NSURLResponse?
	
	do {
	
		let data = try NSURLConnection.sendSynchronousRequest(request, returningResponse: &response)
		print(response)
	
	} catch {
		print(error)
	}
	
## 購物車範例

* 購物車最多只能 5 個商品，否則會丟出 cartIsFull 的錯誤
* 結帳時至少要有 1 個商品，否則會丟出 cartIsEmpty 的錯誤

> 遵詢 ErrorType 協定，使用 enum 列舉來規劃

	enum ShoppingCartError: ErrorType {
		case cartIsFull
		case cartIsEmpty
	}
	
> 商品

	struct Item {
		var price:Double
		var name:String
	}

> Shopping Cart

	class LiteShoppingCart {
		var items:[Item] = []
		
		func addItem(item: Item) throws { // 使用 throws 表示這個 method 可以丟出錯誤
			guard items.count < 5 else {
				throw ShoppingCartError.cartIsFull
			}
			items.append(item)
		}
		
		func checkout() throws {
			guard items.count > 0 else {
				throw ShoppingCartError.cartIsEmpty
			}
			// 繼續結帳
		}
	}
	
> 實作

	let shoppingCart = LiteShoppingCart()
	
	do {
		
		try shoppingCart.checkout()
		print("success")
		
	} catch ShoppingCartError.cartIsFull {
		print("cartIsFull")
	} catch ShoppingCartError.cartIsEmpty {
		print("cartIsEmpty")
	} catch {
		print(error) // error 常數
	}
	
> 實作

	try shoppingCart.addItem(Item(price: 100, name: "P1"))
	try shoppingCart.addItem(Item(price: 100, name: "P2"))
	try shoppingCart.addItem(Item(price: 100, name: "P3"))
	try shoppingCart.addItem(Item(price: 100, name: "P4"))
	try shoppingCart.addItem(Item(price: 100, name: "P5"))
	try shoppingCart.addItem(Item(price: 100, name: "P6"))