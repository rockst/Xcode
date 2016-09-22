# 類別 Class

> 使用 .swift 一個檔案定義一個類別

	class Student {
	
		// 需要預設值
		var name: String = ""
		var age: Int = 18
		var others: String[] = ["game", "art"]
		
		// 使用 ? 表示是可選擇性的值 Optional , 其 tel = nil
		var tel: String?
	
	}
	
## 建立類別實體 Class Instance

	var StudentItem = Student()
	
	Student.name = "rock"
	Student.age = 40
	Student.others = ["game", "movie", "food"]
	
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
			reutrn 10
		}
	}
	
	var StudentItem = Student()
	var score = StudentItem.getScore("Rock")
	print(score)
	

	