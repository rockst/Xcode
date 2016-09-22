# 流程控制 Control Flow

## for loop

> ..<5 表示 < 5 不包括5

	for i in 0..<5 {
		print(i)
	}
	
> result

	0
	1
	2
	3
	4
	
> ...5 表示 <= 5 包括5

	for i in 0...5 {
		print(i)
	}
	
> result

	0
	1
	2
	3
	4
	5

> 傳統 for loop

	for var i = 0; i < 5 ; i++
	{
		print(i)
	}
	
> for-in where

	let numbers = [1, 2, 3, 4, 5]
	
	for number in numbers where number > 3 {
		print(number)
	}
	
	// console result
	4
	5

## if-else

	var a = 100
	if a > 100 {
	} else {
	}

## switch

> 沒有 break

	var var_name = "rock"
	
	switch var_name
	{
		case "rock":
			print("case1")
		case "sam":
			print("case2")
		default:
			print("default")
	
	}
	
> 支援範圍配對 range matching

	var score = 80
	
	switch score
	{
		case 0:
			print("case1")
		case 0...60: // 0 <= score >= 60
			print("case2")
		case 61...100: // 61 <= score >= 100
			print("case3")
		default:
			print("default")
	}

## repeat-while

> 用來取代 do-while, repeat-while 在每一次的迴圈最後作判斷來決定要不要執行

	var i = 0
	
	repeat {
		i++
		print(i)
	} while i < 10
	
## Guard

> 用來處理不想要的條件就直接 return , 讓程式碼更簡潔

> guard .... else {

>	return

> }

	struct Article {
		var title:String?
		var desc:String?
		var author:String?
		var words:Int?
	}
	
	// 未使用 guard
	func printInfo(article: Article) {
	
		if let words = article.words where words > 100 {
			if let title = article.title {
				print(title)
			} else {
				print("title is nil")
			}
		} else {
			print("words 沒有超過 100 字")
		}
	}
	
	// 使用 guard
	func printInfo(article: Article) {
	
		// 用來處理不想要的條件就直接 return
		guard let words = article.words where words > 100 else {
			print("words 沒有超過 100 字")
			return
		}
		
		// 用來處理不想要的條件就直接 return
		guard let title = article.title else {
			print("title is nil")
			return
		}
		
		// 最後執行的片段
		print(title)
	}
	
	let ArticleItem = Article(title: "rock", desc: "rock life", author: "Rock Lin", words: 50)
	printInfo(ArticleItem)