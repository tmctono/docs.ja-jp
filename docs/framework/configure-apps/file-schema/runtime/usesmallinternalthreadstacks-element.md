---
title: <UseSmallInternalThreadStacks> 要素
ms.date: 03/30/2017
helpviewer_keywords:
- UseSmallInternalThreadStacks element
- <UseSmallInternalThreadStacks> element
ms.assetid: 1e3f6ec0-1cac-4e1c-9c81-17d948ae5874
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b9833d768b84faaf6e1dcf8c9cb8b00b92adc3d1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673987"
---
# <a name="usesmallinternalthreadstacks-element"></a><span data-ttu-id="33176-102">\<UseSmallInternalThreadStacks > 要素</span><span class="sxs-lookup"><span data-stu-id="33176-102">\<UseSmallInternalThreadStacks> Element</span></span>
<span data-ttu-id="33176-103">要求の共通言語ランタイム (CLR) がメモリを減らすことは、内部的には、これらのスレッドの既定のスタック サイズを使用する代わりに使用する特定のスレッドの作成時に、明示的なスタック サイズを指定することによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="33176-103">Requests that the common language runtime (CLR) reduce memory use by specifying explicit stack sizes when it creates certain threads that it uses internally, instead of using the default stack size for those threads.</span></span>  
  
 <span data-ttu-id="33176-104">\<configuration > 要素</span><span class="sxs-lookup"><span data-stu-id="33176-104">\<configuration> Element</span></span>  
<span data-ttu-id="33176-105">\<runtime> 要素</span><span class="sxs-lookup"><span data-stu-id="33176-105">\<runtime> Element</span></span>  
<span data-ttu-id="33176-106">\<UseSmallInternalThreadStacks > 要素</span><span class="sxs-lookup"><span data-stu-id="33176-106">\<UseSmallInternalThreadStacks> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33176-107">構文</span><span class="sxs-lookup"><span data-stu-id="33176-107">Syntax</span></span>  
  
```xml  
<UseSmallInternalThreadStacks enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="33176-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="33176-108">Attributes and Elements</span></span>  
 <span data-ttu-id="33176-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="33176-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="33176-110">属性</span><span class="sxs-lookup"><span data-stu-id="33176-110">Attributes</span></span>  
  
|<span data-ttu-id="33176-111">属性</span><span class="sxs-lookup"><span data-stu-id="33176-111">Attribute</span></span>|<span data-ttu-id="33176-112">説明</span><span class="sxs-lookup"><span data-stu-id="33176-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="33176-113">enabled</span><span class="sxs-lookup"><span data-stu-id="33176-113">enabled</span></span>|<span data-ttu-id="33176-114">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="33176-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="33176-115">内部的に使用する特定のスレッドを作成するときを要求するかどうかに既定のスタック サイズではなく、CLR の使用の明示的なスタック サイズを指定します。</span><span class="sxs-lookup"><span data-stu-id="33176-115">Specifies whether to request that the CLR use explicit stack sizes instead of the default stack size when it creates certain threads that it uses internally.</span></span> <span data-ttu-id="33176-116">明示的なスタック サイズは 1 MB の既定のスタック サイズより小さいです。</span><span class="sxs-lookup"><span data-stu-id="33176-116">The explicit stack sizes are smaller than the default stack size of 1 MB.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="33176-117">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="33176-117">enabled Attribute</span></span>  
  
|<span data-ttu-id="33176-118">値</span><span class="sxs-lookup"><span data-stu-id="33176-118">Value</span></span>|<span data-ttu-id="33176-119">説明</span><span class="sxs-lookup"><span data-stu-id="33176-119">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="33176-120">true</span><span class="sxs-lookup"><span data-stu-id="33176-120">true</span></span>|<span data-ttu-id="33176-121">明示的なスタック サイズを要求します。</span><span class="sxs-lookup"><span data-stu-id="33176-121">Request explicit stack sizes.</span></span>|  
|<span data-ttu-id="33176-122">False</span><span class="sxs-lookup"><span data-stu-id="33176-122">false</span></span>|<span data-ttu-id="33176-123">既定のスタック サイズを使用します。</span><span class="sxs-lookup"><span data-stu-id="33176-123">Use the default stack size.</span></span> <span data-ttu-id="33176-124">これは、既定値は、[!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="33176-124">This is the default for the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="33176-125">子要素</span><span class="sxs-lookup"><span data-stu-id="33176-125">Child Elements</span></span>  
 <span data-ttu-id="33176-126">なし。</span><span class="sxs-lookup"><span data-stu-id="33176-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="33176-127">親要素</span><span class="sxs-lookup"><span data-stu-id="33176-127">Parent Elements</span></span>  
  
|<span data-ttu-id="33176-128">要素</span><span class="sxs-lookup"><span data-stu-id="33176-128">Element</span></span>|<span data-ttu-id="33176-129">説明</span><span class="sxs-lookup"><span data-stu-id="33176-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="33176-130">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="33176-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="33176-131">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="33176-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="33176-132">Remarks</span><span class="sxs-lookup"><span data-stu-id="33176-132">Remarks</span></span>  
 <span data-ttu-id="33176-133">この構成要素は、CLR は、その内部のスレッドの場合は、要求が受け入れられます、明示的なスレッドのサイズが既定のサイズより小さいために、プロセスより少ない仮想メモリの使用を要求に使用されます。</span><span class="sxs-lookup"><span data-stu-id="33176-133">This configuration element is used to request reduced virtual memory use in a process, because the explicit thread sizes that the CLR uses for its internal threads, if the request is honored, are smaller than the default size.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="33176-134">この構成要素は、絶対要件ではなく、CLR に要求です。</span><span class="sxs-lookup"><span data-stu-id="33176-134">This configuration element is a request to the CLR rather than an absolute requirement.</span></span> <span data-ttu-id="33176-135">[!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]X86 にのみ、要求が受け入れられますアーキテクチャ。</span><span class="sxs-lookup"><span data-stu-id="33176-135">In the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], the request is honored only for the x86 architecture.</span></span> <span data-ttu-id="33176-136">この要素は、CLR の将来のバージョンでは完全に無視されます。 または選択した内部スレッドに常に使用される明示的なスタック サイズを指定して置換可能性があります。</span><span class="sxs-lookup"><span data-stu-id="33176-136">This element might be ignored completely in future versions of the CLR, or replaced by explicit stack sizes that are always used for selected internal threads.</span></span>  
  
 <span data-ttu-id="33176-137">この構成要素、信頼性が低下より小さい仮想メモリの使用を要求が受け入れられる場合スタック サイズが小さくなる可能性があるため可能性のあるスタックを指定することは、多くの場合オーバーフローします。</span><span class="sxs-lookup"><span data-stu-id="33176-137">Specifying this configuration element trades reliability for smaller virtual memory use if the CLR honors the request, because smaller stack sizes could potentially make stack overflows more likely.</span></span>  
  
## <a name="example"></a><span data-ttu-id="33176-138">例</span><span class="sxs-lookup"><span data-stu-id="33176-138">Example</span></span>  
 <span data-ttu-id="33176-139">次の例では、CLR の使用の明示的なスタックのサイズが内部的に使用するスレッドを特定のことを要求する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="33176-139">The following example shows how to request that the CLR use explicit stack sizes for certain threads that it uses internally.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <UseSmallInternalThreadStacks enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="33176-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="33176-140">See also</span></span>

- [<span data-ttu-id="33176-141">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="33176-141">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="33176-142">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="33176-142">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
