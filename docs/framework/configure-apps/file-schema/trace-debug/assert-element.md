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
ms.openlocfilehash: 2f3823265e358976f970cdfa36772d2251894280
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59197608"
---
# <a name="assert-element"></a><span data-ttu-id="ba2f2-102">\<アサート > 要素</span><span class="sxs-lookup"><span data-stu-id="ba2f2-102">\<assert> Element</span></span>
<span data-ttu-id="ba2f2-103"><xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> メソッドの呼び出し時にメッセージ ボックスを表示するかどうかを指定し、メッセージの書き込み先のファイルの名前も指定します。</span><span class="sxs-lookup"><span data-stu-id="ba2f2-103">Specifies whether to display a message box when you call the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> method; also specifies the name of the file to write messages to.</span></span>  
  
 <span data-ttu-id="ba2f2-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="ba2f2-104">\<configuration></span></span>  
<span data-ttu-id="ba2f2-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="ba2f2-105">\<system.diagnostics></span></span>  
<span data-ttu-id="ba2f2-106">\<assert></span><span class="sxs-lookup"><span data-stu-id="ba2f2-106">\<assert></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba2f2-107">構文</span><span class="sxs-lookup"><span data-stu-id="ba2f2-107">Syntax</span></span>  
  
```xml  
<assert assertuienabled="true|false" logfilename="file name"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ba2f2-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="ba2f2-108">Attributes and Elements</span></span>  
 <span data-ttu-id="ba2f2-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="ba2f2-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ba2f2-110">属性</span><span class="sxs-lookup"><span data-stu-id="ba2f2-110">Attributes</span></span>  
  
|<span data-ttu-id="ba2f2-111">属性</span><span class="sxs-lookup"><span data-stu-id="ba2f2-111">Attribute</span></span>|<span data-ttu-id="ba2f2-112">説明</span><span class="sxs-lookup"><span data-stu-id="ba2f2-112">Description</span></span>|  
|---------------|-----------------|  
|`assertuienabled`|<span data-ttu-id="ba2f2-113">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="ba2f2-113">Optional attribute.</span></span><br /><br /> <span data-ttu-id="ba2f2-114">かどうかを表示する際にメッセージ ボックスを指定します、 **Debug.Assert**メソッドを評価する**false**します。</span><span class="sxs-lookup"><span data-stu-id="ba2f2-114">Specifies whether to display a message box when the **Debug.Assert** method evaluates to **false**.</span></span>|  
|`logfilename`|<span data-ttu-id="ba2f2-115">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="ba2f2-115">Optional attribute.</span></span><br /><br /> <span data-ttu-id="ba2f2-116">場合に、メッセージを書き込むファイルの名前を示す**Debug.Assert**に評価される**false**します。</span><span class="sxs-lookup"><span data-stu-id="ba2f2-116">Specifies the name of the file to write the message to if **Debug.Assert** evaluates to **false**.</span></span>|  
  
## <a name="assertuienabled-attribute"></a><span data-ttu-id="ba2f2-117">assertuienabled 属性</span><span class="sxs-lookup"><span data-stu-id="ba2f2-117">assertuienabled Attribute</span></span>  
  
|<span data-ttu-id="ba2f2-118">[値]</span><span class="sxs-lookup"><span data-stu-id="ba2f2-118">Value</span></span>|<span data-ttu-id="ba2f2-119">説明</span><span class="sxs-lookup"><span data-stu-id="ba2f2-119">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="ba2f2-120">メッセージ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ba2f2-120">Displays the message box.</span></span> <span data-ttu-id="ba2f2-121">既定値です。</span><span class="sxs-lookup"><span data-stu-id="ba2f2-121">This is the default.</span></span>|  
|`false`|<span data-ttu-id="ba2f2-122">メッセージ ボックスは表示されません。</span><span class="sxs-lookup"><span data-stu-id="ba2f2-122">Does not display the message box.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ba2f2-123">子要素</span><span class="sxs-lookup"><span data-stu-id="ba2f2-123">Child Elements</span></span>  
 <span data-ttu-id="ba2f2-124">なし。</span><span class="sxs-lookup"><span data-stu-id="ba2f2-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ba2f2-125">親要素</span><span class="sxs-lookup"><span data-stu-id="ba2f2-125">Parent Elements</span></span>  
  
|<span data-ttu-id="ba2f2-126">要素</span><span class="sxs-lookup"><span data-stu-id="ba2f2-126">Element</span></span>|<span data-ttu-id="ba2f2-127">説明</span><span class="sxs-lookup"><span data-stu-id="ba2f2-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="ba2f2-128">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="ba2f2-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="ba2f2-129">メッセージを収集、格納、およびルーティングするトレース リスナーとトレース スイッチを設定するレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="ba2f2-129">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ba2f2-130">Remarks</span><span class="sxs-lookup"><span data-stu-id="ba2f2-130">Remarks</span></span>  
 <span data-ttu-id="ba2f2-131">両方の属性で、 **\<アサート >** 要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="ba2f2-131">Both attributes in the **\<assert>** element are optional.</span></span> <span data-ttu-id="ba2f2-132">メッセージ ボックスに、メッセージを書き込むファイルを指定せず無効にできますか、メッセージ ボックスが有効のままにしてメッセージを記述するファイルを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="ba2f2-132">You can disable message boxes without specifying a file to write the messages to, or you can specify a file to write messages to while leaving message boxes enabled.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ba2f2-133">例</span><span class="sxs-lookup"><span data-stu-id="ba2f2-133">Example</span></span>  
 <span data-ttu-id="ba2f2-134">次の例は、呼び出すときに表示するメッセージ ボックスを無効にする方法を示しています。 **Debug.Assert**にメッセージを書き込むと`c:\log.txt`します。</span><span class="sxs-lookup"><span data-stu-id="ba2f2-134">The following example shows how to disable displaying message boxes when you call **Debug.Assert** and write the messages to `c:\log.txt`.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <assert assertuienabled="false" logfilename="c:\log.txt"/>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ba2f2-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="ba2f2-135">See also</span></span>

- <xref:System.Diagnostics.Debug>
- [<span data-ttu-id="ba2f2-136">トレースおよびデバッグ設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="ba2f2-136">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
