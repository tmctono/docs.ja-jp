---
title: <assert> 要素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/assert
- http://schemas.microsoft.com/.NetConfiguration/v2.0#assert
helpviewer_keywords:
- <assert> element
- assert element
ms.assetid: ef4c3229-b151-4d85-8091-e6456af9b935
ms.openlocfilehash: f3c1a1670139a8262dea449bfff99c7c1c19f088
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "74088949"
---
# <a name="assert-element"></a><span data-ttu-id="1a53d-102">\<assert> 要素</span><span class="sxs-lookup"><span data-stu-id="1a53d-102">\<assert> Element</span></span>
<span data-ttu-id="1a53d-103"><xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> メソッドの呼び出し時にメッセージ ボックスを表示するかどうかを指定し、メッセージの書き込み先のファイルの名前も指定します。</span><span class="sxs-lookup"><span data-stu-id="1a53d-103">Specifies whether to display a message box when you call the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> method; also specifies the name of the file to write messages to.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<assert>**

## <a name="syntax"></a><span data-ttu-id="1a53d-104">構文</span><span class="sxs-lookup"><span data-stu-id="1a53d-104">Syntax</span></span>  
  
```xml  
<assert assertuienabled="true|false" logfilename="file name"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1a53d-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="1a53d-105">Attributes and Elements</span></span>  
 <span data-ttu-id="1a53d-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="1a53d-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1a53d-107">属性</span><span class="sxs-lookup"><span data-stu-id="1a53d-107">Attributes</span></span>  
  
|<span data-ttu-id="1a53d-108">属性</span><span class="sxs-lookup"><span data-stu-id="1a53d-108">Attribute</span></span>|<span data-ttu-id="1a53d-109">説明</span><span class="sxs-lookup"><span data-stu-id="1a53d-109">Description</span></span>|  
|---------------|-----------------|  
|`assertuienabled`|<span data-ttu-id="1a53d-110">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="1a53d-110">Optional attribute.</span></span><br /><br /> <span data-ttu-id="1a53d-111">**デバッグの Assert**メソッドが**false**と評価されたときにメッセージボックスを表示するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="1a53d-111">Specifies whether to display a message box when the **Debug.Assert** method evaluates to **false**.</span></span>|  
|`logfilename`|<span data-ttu-id="1a53d-112">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="1a53d-112">Optional attribute.</span></span><br /><br /> <span data-ttu-id="1a53d-113">**デバッグ**が**false**と評価された場合にメッセージを書き込むファイルの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="1a53d-113">Specifies the name of the file to write the message to if **Debug.Assert** evaluates to **false**.</span></span>|  
  
## <a name="assertuienabled-attribute"></a><span data-ttu-id="1a53d-114">assertuienabled 属性</span><span class="sxs-lookup"><span data-stu-id="1a53d-114">assertuienabled Attribute</span></span>  
  
|<span data-ttu-id="1a53d-115">値</span><span class="sxs-lookup"><span data-stu-id="1a53d-115">Value</span></span>|<span data-ttu-id="1a53d-116">Description</span><span class="sxs-lookup"><span data-stu-id="1a53d-116">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="1a53d-117">メッセージボックスを表示します。</span><span class="sxs-lookup"><span data-stu-id="1a53d-117">Displays the message box.</span></span> <span data-ttu-id="1a53d-118">既定値です。</span><span class="sxs-lookup"><span data-stu-id="1a53d-118">This is the default.</span></span>|  
|`false`|<span data-ttu-id="1a53d-119">では、メッセージボックスは表示されません。</span><span class="sxs-lookup"><span data-stu-id="1a53d-119">Does not display the message box.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1a53d-120">子要素</span><span class="sxs-lookup"><span data-stu-id="1a53d-120">Child Elements</span></span>  
 <span data-ttu-id="1a53d-121">なし。</span><span class="sxs-lookup"><span data-stu-id="1a53d-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1a53d-122">親要素</span><span class="sxs-lookup"><span data-stu-id="1a53d-122">Parent Elements</span></span>  
  
|<span data-ttu-id="1a53d-123">要素</span><span class="sxs-lookup"><span data-stu-id="1a53d-123">Element</span></span>|<span data-ttu-id="1a53d-124">Description</span><span class="sxs-lookup"><span data-stu-id="1a53d-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="1a53d-125">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="1a53d-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="1a53d-126">メッセージを収集、格納、およびルーティングするトレース リスナーとトレース スイッチを設定するレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="1a53d-126">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1a53d-127">解説</span><span class="sxs-lookup"><span data-stu-id="1a53d-127">Remarks</span></span>  
 <span data-ttu-id="1a53d-128">要素の両方の属性 **\<assert>** は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="1a53d-128">Both attributes in the **\<assert>** element are optional.</span></span> <span data-ttu-id="1a53d-129">メッセージを書き込むファイルを指定せずにメッセージボックスを無効にすることも、メッセージを有効にしたままメッセージを書き込むファイルを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="1a53d-129">You can disable message boxes without specifying a file to write the messages to, or you can specify a file to write messages to while leaving message boxes enabled.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1a53d-130">例</span><span class="sxs-lookup"><span data-stu-id="1a53d-130">Example</span></span>  
 <span data-ttu-id="1a53d-131">次の例は、 **Assert**を呼び出し、メッセージをに書き込むときに、メッセージボックスの表示を無効にする方法を示して `c:\log.txt` います。</span><span class="sxs-lookup"><span data-stu-id="1a53d-131">The following example shows how to disable displaying message boxes when you call **Debug.Assert** and write the messages to `c:\log.txt`.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <assert assertuienabled="false" logfilename="c:\log.txt"/>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1a53d-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="1a53d-132">See also</span></span>

- <xref:System.Diagnostics.Debug>
- [<span data-ttu-id="1a53d-133">トレースおよびデバッグ設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="1a53d-133">Trace and Debug Settings Schema</span></span>](index.md)
