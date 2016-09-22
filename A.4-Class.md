# 類別 Class

> 使用 .swift 一個檔案定義一個類別

	class Student {
	
		// 需要預設值
		var name: String = ""
		var age: Int = 18
		var others: [String] = ["game", "art"]
		
		// 使用 ? 表示是可選擇性的值 Optional , 其 tel = nil
		var tel: String?
	
	}
	
## enum 列舉

> 定義

	enum ShoppingCartError: ErrorType {
		case cartIsFull
		case cartIsEmpty
	}
	
> 實作
	
	ShoppingCartError.cartIsFull

## struct

> 定義

	struct Item {
		var price:Double
		var name:String
	}

> 實作
	
	let ItemObject = Item(price: 100, name: "p1")
	
## 建立類別實體 Class Instance

	var StudentItem = Student()
	
	StudentItem.name = "rock"
	StudentItem.age = 40
	StudentItem.others = ["game", "movie", "food"]
	
## Extends 繼承與採用

> SimpleTableViewController 繼承 UIViewController

> SimpleTableViewController 採用 UITableViewDelegate, UITableViewDataSource 協定

	class SimpleTableViewController : UIViewController, UITableViewDelegate, UITableViewDataSource {
	
	}
	
# 方法 Method

	class Student {
	
		//  method
		func getScore() {
		
		}
	}
	
> call method

	var StudentItem = Student()
	StudentItem.getScore()
	
## Method 參數和回傳

> 參數 name 其型別為 String

> 回傳一個型別為 Integer 的值

	class Student {
		func getScore(name:String) -> Int {
			print("name = \(name)")
			return 10
		}
	}
	
	var StudentItem = Student()
	var score = StudentItem.getScore("Rock")
	print(score)
	
## 計算屬性 Computed Properties

	class Hotel {
	
		var roomCount:Int
		var roomPrice:Int
		
		var totalPrice:Int {
		
			// getter
			get {
				return roomCount * roomPrice
			}
			
			// setter
			set {
				let newRoomPrice = Int(newValue / roomCount)
				roomPrice = newRoomPrice
			}
		}
		
		// Contructer
		init(roomCount: Int = 10, roomPrice: Int = 100) {
			self.roomCount = roomCount
			self.roomPrice = roomPrice
		}
	
	}
	
	let HotelItem = Hotel(roomCount: 1, roomPrice: 100)
	print(HotelItem.totalPrice)
	
## 屬性觀察者 Property Observers

> 針對屬性值的變更做反應

> willSet : 值被儲存之前呼叫

> didSet: 值被儲存之後呼叫


	class Hotel {
		var roomPrice: Int = 0 {
			didSet {
				if roomPrice > 1000 {
					roomPrice = 1000
				}
			}
		}
	}
	
## 可失敗轉型 Failable Casts

> 使用 as! 來強迫轉型

	let cel = tableView.dequeueReusableCellWithIdentifier(cellIdentifier, forIndexPath: indexPath) as! UITableViewCell

> 使用 as? 可以判斷是否轉型成功, 失敗回傳 nil
	