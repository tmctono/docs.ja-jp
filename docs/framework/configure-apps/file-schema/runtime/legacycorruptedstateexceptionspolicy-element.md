---
title: <legacyCorruptedStateExceptionsPolicy> 要素
ms.date: 03/30/2017
helpviewer_keywords:
- <legacyCorruptedStateExceptionsPolicy> element
- legacyCorruptedStateExceptionsPolicy element
ms.assetid: e0a55ddc-bfa8-4f3e-ac14-d1fc3330e4bb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2715548a40579375cebbdd5fb9003738a42ff714
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663653"
---
# <a name="legacycorruptedstateexceptionspolicy-element"></a><span data-ttu-id="c2930-102">\<legacyCorruptedStateExceptionsPolicy > 要素</span><span class="sxs-lookup"><span data-stu-id="c2930-102">\<legacyCorruptedStateExceptionsPolicy> Element</span></span>
<span data-ttu-id="c2930-103">共通言語ランタイムで、マネージコードがアクセス違反とその他の破損状態例外をキャッチできるようにするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="c2930-103">Specifies whether the common language runtime allows managed code to catch access violations and other corrupted state exceptions.</span></span>  
  
 <span data-ttu-id="c2930-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="c2930-104">\<configuration></span></span>  
<span data-ttu-id="c2930-105">\<ランタイム ></span><span class="sxs-lookup"><span data-stu-id="c2930-105">\<runtime></span></span>  
<span data-ttu-id="c2930-106">\<legacyCorruptedStateExceptionsPolicy></span><span class="sxs-lookup"><span data-stu-id="c2930-106">\<legacyCorruptedStateExceptionsPolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2930-107">構文</span><span class="sxs-lookup"><span data-stu-id="c2930-107">Syntax</span></span>  
  
```xml  
<legacyCorruptedStateExceptionsPolicy enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c2930-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="c2930-108">Attributes and Elements</span></span>  
 <span data-ttu-id="c2930-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="c2930-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c2930-110">属性</span><span class="sxs-lookup"><span data-stu-id="c2930-110">Attributes</span></span>  
  
|<span data-ttu-id="c2930-111">属性</span><span class="sxs-lookup"><span data-stu-id="c2930-111">Attribute</span></span>|<span data-ttu-id="c2930-112">説明</span><span class="sxs-lookup"><span data-stu-id="c2930-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="c2930-113">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="c2930-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="c2930-114">アプリケーションがアクセス違反などの破損状態の例外エラーをキャッチすることを指定します。</span><span class="sxs-lookup"><span data-stu-id="c2930-114">Specifies that the application will catch corrupting state exception failures such as access violations.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="c2930-115">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="c2930-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="c2930-116">値</span><span class="sxs-lookup"><span data-stu-id="c2930-116">Value</span></span>|<span data-ttu-id="c2930-117">説明</span><span class="sxs-lookup"><span data-stu-id="c2930-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="c2930-118">アプリケーションでは、アクセス違反などの破損状態の例外エラーはキャッチされません。</span><span class="sxs-lookup"><span data-stu-id="c2930-118">The application will not catch corrupting state exception failures such as access violations.</span></span> <span data-ttu-id="c2930-119">既定値です。</span><span class="sxs-lookup"><span data-stu-id="c2930-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="c2930-120">アプリケーションは、アクセス違反などの破損状態の例外エラーをキャッチします。</span><span class="sxs-lookup"><span data-stu-id="c2930-120">The application will catch corrupting state exception failures such as access violations.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c2930-121">子要素</span><span class="sxs-lookup"><span data-stu-id="c2930-121">Child Elements</span></span>  
 <span data-ttu-id="c2930-122">なし。</span><span class="sxs-lookup"><span data-stu-id="c2930-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c2930-123">親要素</span><span class="sxs-lookup"><span data-stu-id="c2930-123">Parent Elements</span></span>  
  
|<span data-ttu-id="c2930-124">要素</span><span class="sxs-lookup"><span data-stu-id="c2930-124">Element</span></span>|<span data-ttu-id="c2930-125">説明</span><span class="sxs-lookup"><span data-stu-id="c2930-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="c2930-126">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="c2930-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="c2930-127">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c2930-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c2930-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="c2930-128">Remarks</span></span>  
 <span data-ttu-id="c2930-129">.NET Framework バージョン3.5 以前では、共通言語ランタイムは、破損したプロセス状態によって発生した例外をキャッチするために、マネージコードを許可しました。</span><span class="sxs-lookup"><span data-stu-id="c2930-129">In the .NET Framework version 3.5 and earlier, the common language runtime allowed managed code to catch exceptions that were raised by corrupted process states.</span></span> <span data-ttu-id="c2930-130">この種類の例外の例として、アクセス違反があります。</span><span class="sxs-lookup"><span data-stu-id="c2930-130">An access violation is an example of this type of exception.</span></span>  
  
 <span data-ttu-id="c2930-131">.NET Framework 4 以降では、マネージコードはブロック内の`catch`これらの種類の例外をキャッチしなくなりました。</span><span class="sxs-lookup"><span data-stu-id="c2930-131">Starting with the .NET Framework 4, managed code no longer catches these types of exceptions in `catch` blocks.</span></span> <span data-ttu-id="c2930-132">ただし、次の2つの方法で、この変更をオーバーライドし、破損状態例外の処理を維持することができます。</span><span class="sxs-lookup"><span data-stu-id="c2930-132">However, you can override this change and maintain the handling of corrupted state exceptions in two ways:</span></span>  
  
- <span data-ttu-id="c2930-133">要素の`enabled`属性をに`true`設定します。 `<legacyCorruptedStateExceptionsPolicy>`</span><span class="sxs-lookup"><span data-stu-id="c2930-133">Set the `<legacyCorruptedStateExceptionsPolicy>` element's `enabled` attribute to `true`.</span></span> <span data-ttu-id="c2930-134">この構成設定は、プロセス全体に適用され、すべてのメソッドに影響します。</span><span class="sxs-lookup"><span data-stu-id="c2930-134">This configuration setting is applied processwide and affects all methods.</span></span>  
  
 <span data-ttu-id="c2930-135">\- または -</span><span class="sxs-lookup"><span data-stu-id="c2930-135">-or-</span></span>  
  
- <span data-ttu-id="c2930-136"><xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=nameWithType> 例外`catch`ブロックを含むメソッドに属性を適用します。</span><span class="sxs-lookup"><span data-stu-id="c2930-136">Apply the <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=nameWithType> attribute to the method that contains the exceptions `catch` block.</span></span>  
  
 <span data-ttu-id="c2930-137">この構成要素は、.NET Framework 4 以降でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="c2930-137">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c2930-138">例</span><span class="sxs-lookup"><span data-stu-id="c2930-138">Example</span></span>  
 <span data-ttu-id="c2930-139">次の例では、アプリケーションが .NET Framework 4 より前の動作に戻し、すべての破損状態の例外エラーをキャッチするように指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c2930-139">The following example shows how to specify that the application should revert to the behavior before the .NET Framework 4, and catch all corrupting state exception failures.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyCorruptedStateExceptionsPolicy enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c2930-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="c2930-140">See also</span></span>

- <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute>
- [<span data-ttu-id="c2930-141">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="c2930-141">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="c2930-142">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="c2930-142">Configuration File Schema</span></span>](../index.md)
