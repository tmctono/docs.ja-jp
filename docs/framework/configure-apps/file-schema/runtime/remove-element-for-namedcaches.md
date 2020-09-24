---
title: <namedCaches> の <remove> 要素
ms.date: 03/30/2017
helpviewer_keywords:
- remove element for namedCaches
- <remove> element for namedCaches
ms.assetid: 24211ea5-163e-4fe5-aed8-004d8499760c
ms.openlocfilehash: c8ad5a0ce6d7a3059943b3962b9255385cea6e15
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183989"
---
# <a name="remove-element-for-namedcaches"></a>\<namedCaches> の \<remove> 要素

名前付きキャッシュ エントリを、メモリ キャッシュの `namedCaches` コレクションから削除します。  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namedCaches>**](namedcaches-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**  
  
## <a name="syntax"></a>構文  
  
```xml  
<namedCaches>  
    <remove name="default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a>種類  

 `None`  
  
## <a name="attributes-and-elements"></a>属性および要素  

 以降のセクションでは、属性、子要素、および親要素について説明します。  
  
### <a name="attributes"></a>属性  

 `None`  
  
### <a name="child-elements"></a>子要素  

 `None`  
  
### <a name="parent-elements"></a>親要素  
  
|要素|説明|  
|-------------|-----------------|  
|[\<namedCaches>](namedcaches-element-cache-settings.md)|名前付きインスタンスの構成設定のコレクションを格納 <xref:System.Runtime.Caching.MemoryCache> します。|  
  
## <a name="remarks"></a>解説  

 要素は、 `remove` `namedCache` メモリキャッシュの名前付きキャッシュコレクションからエントリを削除します。  
  
## <a name="see-also"></a>関連項目

- [\<namedCaches> 要素 (キャッシュ設定)](namedcaches-element-cache-settings.md)
