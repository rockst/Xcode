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