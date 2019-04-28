---
title: <legacyCorruptedStateExceptionsPolicy> 要素
ms.date: 03/30/2017
helpviewer_keywords:
- <legacyCorruptedStateExceptionsPolicy> element
- legacyCorruptedStateExceptionsPolicy element
ms.assetid: e0a55ddc-bfa8-4f3e-ac14-d1fc3330e4bb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 777d496614435106b84b47b9aa3d35d964bc3e07
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704740"
---
# <a name="legacycorruptedstateexceptionspolicy-element"></a><span data-ttu-id="ef255-102">\<legacyCorruptedStateExceptionsPolicy > 要素</span><span class="sxs-lookup"><span data-stu-id="ef255-102">\<legacyCorruptedStateExceptionsPolicy> Element</span></span>
<span data-ttu-id="ef255-103">共通言語ランタイムがアクセス違反およびその他の破損状態例外をキャッチするマネージ コードをできるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="ef255-103">Specifies whether the common language runtime allows managed code to catch access violations and other corrupted state exceptions.</span></span>  
  
 <span data-ttu-id="ef255-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="ef255-104">\<configuration></span></span>  
<span data-ttu-id="ef255-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="ef255-105">\<runtime></span></span>  
<span data-ttu-id="ef255-106">\<legacyCorruptedStateExceptionsPolicy></span><span class="sxs-lookup"><span data-stu-id="ef255-106">\<legacyCorruptedStateExceptionsPolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef255-107">構文</span><span class="sxs-lookup"><span data-stu-id="ef255-107">Syntax</span></span>  
  
```xml  
<legacyCorruptedStateExceptionsPolicy enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ef255-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="ef255-108">Attributes and Elements</span></span>  
 <span data-ttu-id="ef255-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="ef255-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ef255-110">属性</span><span class="sxs-lookup"><span data-stu-id="ef255-110">Attributes</span></span>  
  
|<span data-ttu-id="ef255-111">属性</span><span class="sxs-lookup"><span data-stu-id="ef255-111">Attribute</span></span>|<span data-ttu-id="ef255-112">説明</span><span class="sxs-lookup"><span data-stu-id="ef255-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="ef255-113">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="ef255-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="ef255-114">アプリケーションをキャッチすることを指定します。 アクセス違反などの例外エラーの状態が破損します。</span><span class="sxs-lookup"><span data-stu-id="ef255-114">Specifies that the application will catch corrupting state exception failures such as access violations.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="ef255-115">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="ef255-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="ef255-116">値</span><span class="sxs-lookup"><span data-stu-id="ef255-116">Value</span></span>|<span data-ttu-id="ef255-117">説明</span><span class="sxs-lookup"><span data-stu-id="ef255-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="ef255-118">アプリケーションはキャッチできない破損状態例外のエラーへのアクセス違反など。</span><span class="sxs-lookup"><span data-stu-id="ef255-118">The application will not catch corrupting state exception failures such as access violations.</span></span> <span data-ttu-id="ef255-119">既定値です。</span><span class="sxs-lookup"><span data-stu-id="ef255-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="ef255-120">アプリケーションがキャッチ破損状態例外のエラーへのアクセス違反など。</span><span class="sxs-lookup"><span data-stu-id="ef255-120">The application will catch corrupting state exception failures such as access violations.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ef255-121">子要素</span><span class="sxs-lookup"><span data-stu-id="ef255-121">Child Elements</span></span>  
 <span data-ttu-id="ef255-122">なし。</span><span class="sxs-lookup"><span data-stu-id="ef255-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ef255-123">親要素</span><span class="sxs-lookup"><span data-stu-id="ef255-123">Parent Elements</span></span>  
  
|<span data-ttu-id="ef255-124">要素</span><span class="sxs-lookup"><span data-stu-id="ef255-124">Element</span></span>|<span data-ttu-id="ef255-125">説明</span><span class="sxs-lookup"><span data-stu-id="ef255-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="ef255-126">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="ef255-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="ef255-127">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ef255-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ef255-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="ef255-128">Remarks</span></span>  
 <span data-ttu-id="ef255-129">.NET Framework 3.5 およびそれ以前のバージョンでは、共通言語ランタイムは、破損したプロセス状態で発生した例外をキャッチするマネージ コードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="ef255-129">In the .NET Framework version 3.5 and earlier, the common language runtime allowed managed code to catch exceptions that were raised by corrupted process states.</span></span> <span data-ttu-id="ef255-130">アクセス違反は、この種類の例外の例を示します。</span><span class="sxs-lookup"><span data-stu-id="ef255-130">An access violation is an example of this type of exception.</span></span>  
  
 <span data-ttu-id="ef255-131">以降では、 [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)]、マネージ コードではこれらの種類の例外のキャッチされなく`catch`ブロックします。</span><span class="sxs-lookup"><span data-stu-id="ef255-131">Starting with the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], managed code no longer catches these types of exceptions in `catch` blocks.</span></span> <span data-ttu-id="ef255-132">ただし、この変更を上書きし、2 つの方法で破損状態例外の処理を維持できます。</span><span class="sxs-lookup"><span data-stu-id="ef255-132">However, you can override this change and maintain the handling of corrupted state exceptions in two ways:</span></span>  
  
- <span data-ttu-id="ef255-133">設定、`<legacyCorruptedStateExceptionsPolicy>`要素の`enabled`属性を`true`します。</span><span class="sxs-lookup"><span data-stu-id="ef255-133">Set the `<legacyCorruptedStateExceptionsPolicy>` element's `enabled` attribute to `true`.</span></span> <span data-ttu-id="ef255-134">この構成設定は適用されているプロセスであり、すべてのメソッドの影響します。</span><span class="sxs-lookup"><span data-stu-id="ef255-134">This configuration setting is applied processwide and affects all methods.</span></span>  
  
 <span data-ttu-id="ef255-135">- または -</span><span class="sxs-lookup"><span data-stu-id="ef255-135">-or-</span></span>  
  
- <span data-ttu-id="ef255-136">適用、<xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=nameWithType>属性をメソッド、例外を含む`catch`ブロックします。</span><span class="sxs-lookup"><span data-stu-id="ef255-136">Apply the <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=nameWithType> attribute to the method that contains the exceptions `catch` block.</span></span>  
  
 <span data-ttu-id="ef255-137">この構成要素はでのみ使用できますが、[!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]以降。</span><span class="sxs-lookup"><span data-stu-id="ef255-137">This configuration element is available only in the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ef255-138">例</span><span class="sxs-lookup"><span data-stu-id="ef255-138">Example</span></span>  
 <span data-ttu-id="ef255-139">次の例は、アプリケーションが前に、の動作に戻る必要がありますを指定する方法を示します、 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]、およびすべての破損状態例外のエラーをキャッチします。</span><span class="sxs-lookup"><span data-stu-id="ef255-139">The following example shows how to specify that the application should revert to the behavior before the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], and catch all corrupting state exception failures.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyCorruptedStateExceptionsPolicy enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ef255-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="ef255-140">See also</span></span>

- <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute>
- [<span data-ttu-id="ef255-141">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="ef255-141">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="ef255-142">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="ef255-142">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
