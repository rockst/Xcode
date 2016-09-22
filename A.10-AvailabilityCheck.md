# 可行性檢查 Availability Check

> 可用來檢查 iOS 版本才能使用的 API

	if #available(iOS 8, *) { // iOS 8 或以上版本
	
	} else { // 早期 iOS 版本
		
	}
	
> 使用 guard

	// 沒有符合 iOS 8.4 或 OS X 10.10 以上版本
	guard #available(iOS 8.4, OS X 10.10, *) else {
		reutrn
	}
	
> 只能適用某個版本

	@available(iOS 9, *)
	
	class xxx {
	
	}