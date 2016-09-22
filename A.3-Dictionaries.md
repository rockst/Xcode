# Collection type

## 使用 key-value pair

	var var_name = ["index1" : "value1", "index2" : "value2"]
	
## 指定型別的方法

	var var_name: Dictionary<String, String> = ["key1" : "value1", "key2" : "value2"]
	
## 使用 for-in 取得索引和值

	for(key, value) in var_name {
		print("\(key) = \(value)")
	}
	
> 取得索引 .keys

	for key in var_name.keys {
		print("key name = \(key)")
	}
	
> 取得值 .values	

	for value in var_name.values {
		print("value = \(value)")
	}
	
## 取得特定 key 的值

	var_name["new_key"] = "new_value"