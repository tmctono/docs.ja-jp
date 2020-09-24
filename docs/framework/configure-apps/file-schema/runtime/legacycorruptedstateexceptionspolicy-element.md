---
title: <legacyCorruptedStateExceptionsPolicy> 要素
ms.date: 03/30/2017
helpviewer_keywords:
- <legacyCorruptedStateExceptionsPolicy> element
- legacyCorruptedStateExceptionsPolicy element
ms.assetid: e0a55ddc-bfa8-4f3e-ac14-d1fc3330e4bb
ms.openlocfilehash: f36e27a1b85cff2ba8c7e838bace37890a5aa760
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91151208"
---
# <a name="legacycorruptedstateexceptionspolicy-element"></a><span data-ttu-id="c0a1c-102">\<legacyCorruptedStateExceptionsPolicy> 要素</span><span class="sxs-lookup"><span data-stu-id="c0a1c-102">\<legacyCorruptedStateExceptionsPolicy> Element</span></span>

<span data-ttu-id="c0a1c-103">共通言語ランタイムで、マネージコードがアクセス違反とその他の破損状態例外をキャッチできるようにするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="c0a1c-103">Specifies whether the common language runtime allows managed code to catch access violations and other corrupted state exceptions.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<legacyCorruptedStateExceptionsPolicy>**  
  
## <a name="syntax"></a><span data-ttu-id="c0a1c-104">構文</span><span class="sxs-lookup"><span data-stu-id="c0a1c-104">Syntax</span></span>  
  
```xml  
<legacyCorruptedStateExceptionsPolicy enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c0a1c-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="c0a1c-105">Attributes and Elements</span></span>  

 <span data-ttu-id="c0a1c-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="c0a1c-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c0a1c-107">属性</span><span class="sxs-lookup"><span data-stu-id="c0a1c-107">Attributes</span></span>  
  
|<span data-ttu-id="c0a1c-108">属性</span><span class="sxs-lookup"><span data-stu-id="c0a1c-108">Attribute</span></span>|<span data-ttu-id="c0a1c-109">説明</span><span class="sxs-lookup"><span data-stu-id="c0a1c-109">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="c0a1c-110">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="c0a1c-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="c0a1c-111">アプリケーションがアクセス違反などの破損状態の例外エラーをキャッチすることを指定します。</span><span class="sxs-lookup"><span data-stu-id="c0a1c-111">Specifies that the application will catch corrupting state exception failures such as access violations.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="c0a1c-112">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="c0a1c-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="c0a1c-113">値</span><span class="sxs-lookup"><span data-stu-id="c0a1c-113">Value</span></span>|<span data-ttu-id="c0a1c-114">[説明]</span><span class="sxs-lookup"><span data-stu-id="c0a1c-114">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="c0a1c-115">アプリケーションでは、アクセス違反などの破損状態の例外エラーはキャッチされません。</span><span class="sxs-lookup"><span data-stu-id="c0a1c-115">The application will not catch corrupting state exception failures such as access violations.</span></span> <span data-ttu-id="c0a1c-116">これは既定値です。</span><span class="sxs-lookup"><span data-stu-id="c0a1c-116">This is the default.</span></span>|  
|`true`|<span data-ttu-id="c0a1c-117">アプリケーションは、アクセス違反などの破損状態の例外エラーをキャッチします。</span><span class="sxs-lookup"><span data-stu-id="c0a1c-117">The application will catch corrupting state exception failures such as access violations.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c0a1c-118">子要素</span><span class="sxs-lookup"><span data-stu-id="c0a1c-118">Child Elements</span></span>  

 <span data-ttu-id="c0a1c-119">なし。</span><span class="sxs-lookup"><span data-stu-id="c0a1c-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c0a1c-120">親要素</span><span class="sxs-lookup"><span data-stu-id="c0a1c-120">Parent Elements</span></span>  
  
|<span data-ttu-id="c0a1c-121">要素</span><span class="sxs-lookup"><span data-stu-id="c0a1c-121">Element</span></span>|<span data-ttu-id="c0a1c-122">説明</span><span class="sxs-lookup"><span data-stu-id="c0a1c-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="c0a1c-123">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="c0a1c-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="c0a1c-124">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c0a1c-124">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c0a1c-125">解説</span><span class="sxs-lookup"><span data-stu-id="c0a1c-125">Remarks</span></span>  

 <span data-ttu-id="c0a1c-126">.NET Framework バージョン3.5 以前では、共通言語ランタイムは、破損したプロセス状態によって発生した例外をキャッチするために、マネージコードを許可しました。</span><span class="sxs-lookup"><span data-stu-id="c0a1c-126">In the .NET Framework version 3.5 and earlier, the common language runtime allowed managed code to catch exceptions that were raised by corrupted process states.</span></span> <span data-ttu-id="c0a1c-127">この種類の例外の例として、アクセス違反があります。</span><span class="sxs-lookup"><span data-stu-id="c0a1c-127">An access violation is an example of this type of exception.</span></span>  
  
 <span data-ttu-id="c0a1c-128">.NET Framework 4 以降では、マネージコードはブロック内のこれらの種類の例外をキャッチしなくなりました `catch` 。</span><span class="sxs-lookup"><span data-stu-id="c0a1c-128">Starting with the .NET Framework 4, managed code no longer catches these types of exceptions in `catch` blocks.</span></span> <span data-ttu-id="c0a1c-129">ただし、次の2つの方法で、この変更をオーバーライドし、破損状態例外の処理を維持することができます。</span><span class="sxs-lookup"><span data-stu-id="c0a1c-129">However, you can override this change and maintain the handling of corrupted state exceptions in two ways:</span></span>  
  
- <span data-ttu-id="c0a1c-130">`<legacyCorruptedStateExceptionsPolicy>`要素の `enabled` 属性をに設定 `true` します。</span><span class="sxs-lookup"><span data-stu-id="c0a1c-130">Set the `<legacyCorruptedStateExceptionsPolicy>` element's `enabled` attribute to `true`.</span></span> <span data-ttu-id="c0a1c-131">この構成設定は、プロセス全体に適用され、すべてのメソッドに影響します。</span><span class="sxs-lookup"><span data-stu-id="c0a1c-131">This configuration setting is applied processwide and affects all methods.</span></span>  
  
 <span data-ttu-id="c0a1c-132">- または -</span><span class="sxs-lookup"><span data-stu-id="c0a1c-132">-or-</span></span>  
  
- <span data-ttu-id="c0a1c-133"><xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=nameWithType>例外ブロックを含むメソッドに属性を適用 `catch` します。</span><span class="sxs-lookup"><span data-stu-id="c0a1c-133">Apply the <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=nameWithType> attribute to the method that contains the exceptions `catch` block.</span></span>  
  
 <span data-ttu-id="c0a1c-134">この構成要素は、.NET Framework 4 以降でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="c0a1c-134">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c0a1c-135">例</span><span class="sxs-lookup"><span data-stu-id="c0a1c-135">Example</span></span>  

 <span data-ttu-id="c0a1c-136">次の例では、アプリケーションが .NET Framework 4 より前の動作に戻し、すべての破損状態の例外エラーをキャッチするように指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c0a1c-136">The following example shows how to specify that the application should revert to the behavior before the .NET Framework 4, and catch all corrupting state exception failures.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyCorruptedStateExceptionsPolicy enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c0a1c-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="c0a1c-137">See also</span></span>

- <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute>
- [<span data-ttu-id="c0a1c-138">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="c0a1c-138">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="c0a1c-139">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="c0a1c-139">Configuration File Schema</span></span>](../index.md)
