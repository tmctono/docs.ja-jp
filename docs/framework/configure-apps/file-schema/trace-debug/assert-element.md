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
ms.openlocfilehash: eb29701912a45a484b1716195b449e8a97d1d4b5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91149297"
---
# <a name="assert-element"></a><span data-ttu-id="2dae7-102">\<assert> 要素</span><span class="sxs-lookup"><span data-stu-id="2dae7-102">\<assert> Element</span></span>

<span data-ttu-id="2dae7-103"><xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> メソッドの呼び出し時にメッセージ ボックスを表示するかどうかを指定し、メッセージの書き込み先のファイルの名前も指定します。</span><span class="sxs-lookup"><span data-stu-id="2dae7-103">Specifies whether to display a message box when you call the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> method; also specifies the name of the file to write messages to.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<assert>**

## <a name="syntax"></a><span data-ttu-id="2dae7-104">構文</span><span class="sxs-lookup"><span data-stu-id="2dae7-104">Syntax</span></span>  
  
```xml  
<assert assertuienabled="true|false" logfilename="file name"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2dae7-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="2dae7-105">Attributes and Elements</span></span>  

 <span data-ttu-id="2dae7-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="2dae7-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2dae7-107">属性</span><span class="sxs-lookup"><span data-stu-id="2dae7-107">Attributes</span></span>  
  
|<span data-ttu-id="2dae7-108">属性</span><span class="sxs-lookup"><span data-stu-id="2dae7-108">Attribute</span></span>|<span data-ttu-id="2dae7-109">説明</span><span class="sxs-lookup"><span data-stu-id="2dae7-109">Description</span></span>|  
|---------------|-----------------|  
|`assertuienabled`|<span data-ttu-id="2dae7-110">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="2dae7-110">Optional attribute.</span></span><br /><br /> <span data-ttu-id="2dae7-111">**デバッグの Assert**メソッドが**false**と評価されたときにメッセージボックスを表示するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="2dae7-111">Specifies whether to display a message box when the **Debug.Assert** method evaluates to **false**.</span></span>|  
|`logfilename`|<span data-ttu-id="2dae7-112">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="2dae7-112">Optional attribute.</span></span><br /><br /> <span data-ttu-id="2dae7-113">**デバッグ**が**false**と評価された場合にメッセージを書き込むファイルの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="2dae7-113">Specifies the name of the file to write the message to if **Debug.Assert** evaluates to **false**.</span></span>|  
  
## <a name="assertuienabled-attribute"></a><span data-ttu-id="2dae7-114">assertuienabled 属性</span><span class="sxs-lookup"><span data-stu-id="2dae7-114">assertuienabled Attribute</span></span>  
  
|<span data-ttu-id="2dae7-115">値</span><span class="sxs-lookup"><span data-stu-id="2dae7-115">Value</span></span>|<span data-ttu-id="2dae7-116">[説明]</span><span class="sxs-lookup"><span data-stu-id="2dae7-116">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="2dae7-117">メッセージボックスを表示します。</span><span class="sxs-lookup"><span data-stu-id="2dae7-117">Displays the message box.</span></span> <span data-ttu-id="2dae7-118">これは既定値です。</span><span class="sxs-lookup"><span data-stu-id="2dae7-118">This is the default.</span></span>|  
|`false`|<span data-ttu-id="2dae7-119">では、メッセージボックスは表示されません。</span><span class="sxs-lookup"><span data-stu-id="2dae7-119">Does not display the message box.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2dae7-120">子要素</span><span class="sxs-lookup"><span data-stu-id="2dae7-120">Child Elements</span></span>  

 <span data-ttu-id="2dae7-121">なし。</span><span class="sxs-lookup"><span data-stu-id="2dae7-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2dae7-122">親要素</span><span class="sxs-lookup"><span data-stu-id="2dae7-122">Parent Elements</span></span>  
  
|<span data-ttu-id="2dae7-123">要素</span><span class="sxs-lookup"><span data-stu-id="2dae7-123">Element</span></span>|<span data-ttu-id="2dae7-124">説明</span><span class="sxs-lookup"><span data-stu-id="2dae7-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="2dae7-125">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="2dae7-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="2dae7-126">メッセージを収集、格納、およびルーティングするトレース リスナーとトレース スイッチを設定するレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="2dae7-126">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2dae7-127">解説</span><span class="sxs-lookup"><span data-stu-id="2dae7-127">Remarks</span></span>  

 <span data-ttu-id="2dae7-128">要素の両方の属性 **\<assert>** は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="2dae7-128">Both attributes in the **\<assert>** element are optional.</span></span> <span data-ttu-id="2dae7-129">メッセージを書き込むファイルを指定せずにメッセージボックスを無効にすることも、メッセージを有効にしたままメッセージを書き込むファイルを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="2dae7-129">You can disable message boxes without specifying a file to write the messages to, or you can specify a file to write messages to while leaving message boxes enabled.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2dae7-130">例</span><span class="sxs-lookup"><span data-stu-id="2dae7-130">Example</span></span>  

 <span data-ttu-id="2dae7-131">次の例は、 **Assert** を呼び出し、メッセージをに書き込むときに、メッセージボックスの表示を無効にする方法を示して `c:\log.txt` います。</span><span class="sxs-lookup"><span data-stu-id="2dae7-131">The following example shows how to disable displaying message boxes when you call **Debug.Assert** and write the messages to `c:\log.txt`.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <assert assertuienabled="false" logfilename="c:\log.txt"/>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2dae7-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="2dae7-132">See also</span></span>

- <xref:System.Diagnostics.Debug>
- [<span data-ttu-id="2dae7-133">トレースおよびデバッグ設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="2dae7-133">Trace and Debug Settings Schema</span></span>](index.md)
