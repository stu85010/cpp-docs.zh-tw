---
title: '&lt;hash_map&gt; 函式'
ms.date: 11/04/2016
f1_keywords:
- hash_map/std::swap
- hash_map/std::swap (hash_map)
ms.assetid: 28748cd0-71f7-41b9-b068-579183645fba
ms.openlocfilehash: dae2c47ef3b84247ab1747e37719a23b220b5d08
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50627418"
---
# <a name="lthashmapgt-functions"></a>&lt;hash_map&gt; 函式

|||
|-|-|
|[swap](#swap)|[swap (hash_map)](#swap_hash_map)|

## <a name="swap_hash_map"></a>  swap (hash_map)

> [!NOTE]
> 這個 API 已過時。 替代方案是 [unordered_map 類別](../standard-library/unordered-map-class.md)。

交換兩個 hash_map 的元素。

```cpp
void swap(
    hash_map <Key, Type, Traits, Alloctor>& left,
    hash_map <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>參數

*right*<br/>
其項目要與 map 交換 hash_map*左*。

*left*<br/>
其項目要與 map 交換 hash_map*右*。

### <a name="remarks"></a>備註

範本函式是在容器類別 hash_map 特製化的演算法，用來執行成員函式 `left.`[swap](../standard-library/basic-ios-class.md#swap)*(right*)。 這是編譯器所執行的函式範本部分排序執行個體。 當因範本函式多載而導致範本與函式呼叫的比對不是唯一的時，編譯器就會選取最特製化的範本函式版本。 演算法標頭檔案中函式版本的一般範本 **template \<class T> void swap(T&, T&)** 會依指派運作而作業緩慢。 每個容器中的特製化版本運作速度會更快，因為它可以與容器類別的內部表示法一起運作。

## <a name="swap"></a>  swap

> [!NOTE]
> 這個 API 已過時。 替代方案是 [unordered_multimap 類別](../standard-library/unordered-multimap-class.md)。

交換兩個 hash_multimap 的元素。

```cpp
void swap(
    hash_multimap <Key, Type, Traits, Alloctor>& left,
    hash_multimap <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>參數

*right*<br/>
其項目要與 map 交換 hash_multimap*左*。

*left*<br/>
其項目要與 map 交換 hash_multimap*右*。

### <a name="remarks"></a>備註

範本函式是在容器類別 hash_multimap 特製化的演算法，用來執行成員函式 `left.`[swap](../standard-library/hash-multimap-class.md#swap)*(right*`)`。 這是編譯器所執行之函式樣板的部分排序執行個體。 當因範本函式多載而導致範本與函式呼叫的比對不是唯一的時，編譯器就會選取最特製化的範本函式版本。 演算法標頭檔案中函式版本的一般範本 **template \<class T> void swap(T&, T&)** 會依指派運作而作業緩慢。 每個容器中的特製化版本運作速度會更快，因為它可以與容器類別的內部表示法一起運作。

## <a name="see-also"></a>另請參閱

[<hash_map>](../standard-library/hash-map.md)<br/>
