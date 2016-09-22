# Tuples

> 一個可以回傳多個值的方法

		let company = ("Apple", "apple.com", 93.5)
		
> 解開 Tuples 的方法

	let(comp_name, comp_url, comp_price) = company
	
> 使用 key

	let company = (name: "Apple", url: "apple.com", price: 93.5)
	
	print("name = \(company.name)")
	print("url = \(company.url)")
	print("price = \(company.price)")
	
> method 回傳 tuples

	func getProdice(number: Int) -> (name: String, url: String, price: Int) {
	
		var name = "rock", url = "rockst.com", price = 100
		
		return (name, url, price)
	
	}