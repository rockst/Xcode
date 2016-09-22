# Generics 泛型

> 舉例說明

	// 比較兩個數字
	func isEqual(a: Int, b: Int) -> Bool {
		return a == b
	}
	
	// 比較兩個字串
	func isEqual(a: String, b: String) -> Bool {
		return a == b
	}
	
> 使用 Generics 泛型來合成一個 func

	// T : placeholder type
	func isEqual<T>(a: T, b: T) {
		return a == b
	}
	
> 使用 Equatable 約束型態, 因為並不是所有型態都可以支援 ==

	func isEqual<T: Equatable>(a: T, b: T) -> Bool {
		return a == b
	]
	
## Generic Types

> IntStore 是一個處理 Int 的類別

	class IntStore {
		var items = [Int]()
		
		// 新增項目
		func addItem(item: Int) {
			items.append(item)
		}
		
		// 取得項目
		func getItem(index: Int) -> Int {
			return items[index]
		}
	}
	
> 修改為 Generic, 就可以支援所有型態


	class ValueStore<T> {
	
		var items = [T]()
		
		func addItem(item: T) {
			items.append(item)
		}
		
		func getItem(index: Int) -> T {
			return items[index]
		}
	}
	
	var Store = ValueStore<String>()
	Store.addItem("Qoo")
	let value = Store.getItem(1)
	
	