---
title: <UseSmallInternalThreadStacks> 要素
ms.date: 03/30/2017
helpviewer_keywords:
- UseSmallInternalThreadStacks element
- <UseSmallInternalThreadStacks> element
ms.assetid: 1e3f6ec0-1cac-4e1c-9c81-17d948ae5874
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 515ea076c5eaead50b41e45e415725d0439914bc
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252205"
---
# <a name="usesmallinternalthreadstacks-element"></a><span data-ttu-id="05163-102">\<UseSmallInternalThreadStacks > 要素</span><span class="sxs-lookup"><span data-stu-id="05163-102">\<UseSmallInternalThreadStacks> Element</span></span>
<span data-ttu-id="05163-103">共通言語ランタイム (CLR) が、内部で使用する特定のスレッドを作成するときに明示的なスタックサイズを指定することによって、メモリの使用量を削減するように要求します。これらのスレッドの既定のスタックサイズは使用されません。</span><span class="sxs-lookup"><span data-stu-id="05163-103">Requests that the common language runtime (CLR) reduce memory use by specifying explicit stack sizes when it creates certain threads that it uses internally, instead of using the default stack size for those threads.</span></span>  
  
<span data-ttu-id="05163-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="05163-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="05163-105">&nbsp;&nbsp;[ **\<ランタイム >** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="05163-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="05163-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<UseSmallInternalThreadStacks>**</span><span class="sxs-lookup"><span data-stu-id="05163-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<UseSmallInternalThreadStacks>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05163-107">構文</span><span class="sxs-lookup"><span data-stu-id="05163-107">Syntax</span></span>  
  
```xml  
<UseSmallInternalThreadStacks enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="05163-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="05163-108">Attributes and Elements</span></span>  
 <span data-ttu-id="05163-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="05163-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="05163-110">属性</span><span class="sxs-lookup"><span data-stu-id="05163-110">Attributes</span></span>  
  
|<span data-ttu-id="05163-111">属性</span><span class="sxs-lookup"><span data-stu-id="05163-111">Attribute</span></span>|<span data-ttu-id="05163-112">説明</span><span class="sxs-lookup"><span data-stu-id="05163-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="05163-113">enabled</span><span class="sxs-lookup"><span data-stu-id="05163-113">enabled</span></span>|<span data-ttu-id="05163-114">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="05163-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="05163-115">内部で使用する特定のスレッドを作成するときに、CLR が既定のスタックサイズではなく明示的なスタックサイズを使用するように要求するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="05163-115">Specifies whether to request that the CLR use explicit stack sizes instead of the default stack size when it creates certain threads that it uses internally.</span></span> <span data-ttu-id="05163-116">明示的なスタックサイズは、既定のスタックサイズの 1 MB よりも小さくなっています。</span><span class="sxs-lookup"><span data-stu-id="05163-116">The explicit stack sizes are smaller than the default stack size of 1 MB.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="05163-117">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="05163-117">enabled Attribute</span></span>  
  
|<span data-ttu-id="05163-118">値</span><span class="sxs-lookup"><span data-stu-id="05163-118">Value</span></span>|<span data-ttu-id="05163-119">説明</span><span class="sxs-lookup"><span data-stu-id="05163-119">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="05163-120">true</span><span class="sxs-lookup"><span data-stu-id="05163-120">true</span></span>|<span data-ttu-id="05163-121">明示的なスタックサイズを要求します。</span><span class="sxs-lookup"><span data-stu-id="05163-121">Request explicit stack sizes.</span></span>|  
|<span data-ttu-id="05163-122">False</span><span class="sxs-lookup"><span data-stu-id="05163-122">false</span></span>|<span data-ttu-id="05163-123">既定のスタックサイズを使用します。</span><span class="sxs-lookup"><span data-stu-id="05163-123">Use the default stack size.</span></span> <span data-ttu-id="05163-124">これは .NET Framework 4 の既定値です。</span><span class="sxs-lookup"><span data-stu-id="05163-124">This is the default for the .NET Framework 4.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="05163-125">子要素</span><span class="sxs-lookup"><span data-stu-id="05163-125">Child Elements</span></span>  
 <span data-ttu-id="05163-126">なし。</span><span class="sxs-lookup"><span data-stu-id="05163-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="05163-127">親要素</span><span class="sxs-lookup"><span data-stu-id="05163-127">Parent Elements</span></span>  
  
|<span data-ttu-id="05163-128">要素</span><span class="sxs-lookup"><span data-stu-id="05163-128">Element</span></span>|<span data-ttu-id="05163-129">説明</span><span class="sxs-lookup"><span data-stu-id="05163-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="05163-130">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="05163-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="05163-131">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="05163-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="05163-132">Remarks</span><span class="sxs-lookup"><span data-stu-id="05163-132">Remarks</span></span>  
 <span data-ttu-id="05163-133">この構成要素は、プロセスでの仮想メモリの使用量の削減を要求するために使用されます。これは、CLR が内部スレッドに使用する明示的なスレッドサイズ (要求が受け入れられた場合) が既定のサイズよりも小さいためです。</span><span class="sxs-lookup"><span data-stu-id="05163-133">This configuration element is used to request reduced virtual memory use in a process, because the explicit thread sizes that the CLR uses for its internal threads, if the request is honored, are smaller than the default size.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="05163-134">この構成要素は、絶対的な要件ではなく、CLR への要求です。</span><span class="sxs-lookup"><span data-stu-id="05163-134">This configuration element is a request to the CLR rather than an absolute requirement.</span></span> <span data-ttu-id="05163-135">.NET Framework 4 では、要求は x86 アーキテクチャに対してのみ受け入れられます。</span><span class="sxs-lookup"><span data-stu-id="05163-135">In the .NET Framework 4, the request is honored only for the x86 architecture.</span></span> <span data-ttu-id="05163-136">この要素は、CLR の将来のバージョンでは完全に無視される場合もあれば、選択した内部スレッドで常に使用される明示的なスタックサイズに置き換えられる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="05163-136">This element might be ignored completely in future versions of the CLR, or replaced by explicit stack sizes that are always used for selected internal threads.</span></span>  
  
 <span data-ttu-id="05163-137">この構成要素を指定すると、CLR が要求を受け入れた場合に、より小さなスタックサイズによってスタックオーバーフローが発生する可能性があるため、仮想メモリの使用量が少なくなります。</span><span class="sxs-lookup"><span data-stu-id="05163-137">Specifying this configuration element trades reliability for smaller virtual memory use if the CLR honors the request, because smaller stack sizes could potentially make stack overflows more likely.</span></span>  
  
## <a name="example"></a><span data-ttu-id="05163-138">例</span><span class="sxs-lookup"><span data-stu-id="05163-138">Example</span></span>  
 <span data-ttu-id="05163-139">次の例は、CLR が内部で使用する特定のスレッドに対して明示的なスタックサイズを使用するように要求する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="05163-139">The following example shows how to request that the CLR use explicit stack sizes for certain threads that it uses internally.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <UseSmallInternalThreadStacks enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="05163-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="05163-140">See also</span></span>

- [<span data-ttu-id="05163-141">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="05163-141">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="05163-142">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="05163-142">Configuration File Schema</span></span>](../index.md)
