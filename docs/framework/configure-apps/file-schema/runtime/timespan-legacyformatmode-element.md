---
title: <TimeSpan_LegacyFormatMode> 要素
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- <TimeSpan_LegacyFormatMode> element
- TimeSpan_LegacyFormatMode element
ms.assetid: 865e7207-d050-4442-b574-57ea29d5e2d6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 38adde3cd51a96f0e15ed5a0c539e088f2d3b480
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61701633"
---
# <a name="timespanlegacyformatmode-element"></a><span data-ttu-id="d1a81-102">\<TimeSpan_LegacyFormatMode > 要素</span><span class="sxs-lookup"><span data-stu-id="d1a81-102">\<TimeSpan_LegacyFormatMode> Element</span></span>
<span data-ttu-id="d1a81-103">ランタイムが書式設定の操作で従来の動作を保持するかどうかを判断します<xref:System.TimeSpan?displayProperty=nameWithType>値。</span><span class="sxs-lookup"><span data-stu-id="d1a81-103">Determines whether the runtime preserves legacy behavior in formatting operations with <xref:System.TimeSpan?displayProperty=nameWithType> values.</span></span>  
  
 <span data-ttu-id="d1a81-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="d1a81-104">\<configuration></span></span>  
<span data-ttu-id="d1a81-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="d1a81-105">\<runtime></span></span>  
<span data-ttu-id="d1a81-106"><TimeSpan_LegacyFormatMode></span><span class="sxs-lookup"><span data-stu-id="d1a81-106"><TimeSpan_LegacyFormatMode></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1a81-107">構文</span><span class="sxs-lookup"><span data-stu-id="d1a81-107">Syntax</span></span>  
  
```xml  
<TimeSpan_LegacyFormatMode    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d1a81-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="d1a81-108">Attributes and Elements</span></span>  
 <span data-ttu-id="d1a81-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="d1a81-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d1a81-110">属性</span><span class="sxs-lookup"><span data-stu-id="d1a81-110">Attributes</span></span>  
  
|<span data-ttu-id="d1a81-111">属性</span><span class="sxs-lookup"><span data-stu-id="d1a81-111">Attribute</span></span>|<span data-ttu-id="d1a81-112">説明</span><span class="sxs-lookup"><span data-stu-id="d1a81-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="d1a81-113">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="d1a81-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="d1a81-114">ランタイムがで従来の書式設定動作を使用しているかどうかを指定します。<xref:System.TimeSpan?displayProperty=nameWithType>値。</span><span class="sxs-lookup"><span data-stu-id="d1a81-114">Specifies whether the runtime uses legacy formatting behavior with <xref:System.TimeSpan?displayProperty=nameWithType> values.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="d1a81-115">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="d1a81-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="d1a81-116">値</span><span class="sxs-lookup"><span data-stu-id="d1a81-116">Value</span></span>|<span data-ttu-id="d1a81-117">説明</span><span class="sxs-lookup"><span data-stu-id="d1a81-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="d1a81-118">ランタイムは、従来の書式設定動作を復元できません。</span><span class="sxs-lookup"><span data-stu-id="d1a81-118">The runtime does not restore legacy formatting behavior.</span></span>|  
|`true`|<span data-ttu-id="d1a81-119">ランタイムは、従来の書式設定動作を復元します。</span><span class="sxs-lookup"><span data-stu-id="d1a81-119">The runtime restores legacy formatting behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d1a81-120">子要素</span><span class="sxs-lookup"><span data-stu-id="d1a81-120">Child Elements</span></span>  
 <span data-ttu-id="d1a81-121">なし。</span><span class="sxs-lookup"><span data-stu-id="d1a81-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d1a81-122">親要素</span><span class="sxs-lookup"><span data-stu-id="d1a81-122">Parent Elements</span></span>  
  
|<span data-ttu-id="d1a81-123">要素</span><span class="sxs-lookup"><span data-stu-id="d1a81-123">Element</span></span>|<span data-ttu-id="d1a81-124">説明</span><span class="sxs-lookup"><span data-stu-id="d1a81-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="d1a81-125">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="d1a81-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="d1a81-126">ランタイム初期化オプションに関する情報を含んでいます。</span><span class="sxs-lookup"><span data-stu-id="d1a81-126">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d1a81-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="d1a81-127">Remarks</span></span>  
 <span data-ttu-id="d1a81-128">以降では、 [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)]、 <xref:System.TimeSpan?displayProperty=nameWithType> implements 構造体、<xref:System.IFormattable>インターフェイスと書式設定を標準とカスタム書式指定文字列の操作をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="d1a81-128">Starting with the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], the <xref:System.TimeSpan?displayProperty=nameWithType> structure implements the <xref:System.IFormattable> interface and supports formatting operations with standard and custom format strings.</span></span> <span data-ttu-id="d1a81-129">解析方法には、サポートされていない書式指定子または書式指定文字列が検出されると、スロー、<xref:System.FormatException>します。</span><span class="sxs-lookup"><span data-stu-id="d1a81-129">If a parsing method encounters an unsupported format specifier or format string, it throws a <xref:System.FormatException>.</span></span>  
  
 <span data-ttu-id="d1a81-130">.NET Framework の以前のバージョンで、<xref:System.TimeSpan>構造を実装しませんでした<xref:System.IFormattable>と書式指定文字列をサポートしていませんでした。</span><span class="sxs-lookup"><span data-stu-id="d1a81-130">In previous versions of the .NET Framework, the <xref:System.TimeSpan> structure did not implement <xref:System.IFormattable> and did not support format strings.</span></span> <span data-ttu-id="d1a81-131">ただし、多くの開発者誤っていることを前提<xref:System.TimeSpan>書式指定文字列のセットをサポートして、それらを使用[複合書式設定操作](../../../../../docs/standard/base-types/composite-formatting.md)などのメソッドで<xref:System.String.Format%2A?displayProperty=nameWithType>します。</span><span class="sxs-lookup"><span data-stu-id="d1a81-131">However, many developers mistakenly assumed that <xref:System.TimeSpan> did support a set of format strings and used them in [composite formatting operations](../../../../../docs/standard/base-types/composite-formatting.md) with methods such as <xref:System.String.Format%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="d1a81-132">通常、型を実装する場合<xref:System.IFormattable>書式指定文字列、文字列は、通常はスローをサポートされていない形式で書式指定メソッドの呼び出しをサポートしていると、<xref:System.FormatException>します。</span><span class="sxs-lookup"><span data-stu-id="d1a81-132">Ordinarily, if a type implements <xref:System.IFormattable> and supports format strings, calls to formatting methods with unsupported format strings usually throw a <xref:System.FormatException>.</span></span> <span data-ttu-id="d1a81-133">ただし、ため<xref:System.TimeSpan>を実装しませんでした<xref:System.IFormattable>、ランタイムは、書式指定文字列を無視し、代わりに呼び出されます、<xref:System.TimeSpan.ToString?displayProperty=nameWithType>メソッド。</span><span class="sxs-lookup"><span data-stu-id="d1a81-133">However, because <xref:System.TimeSpan> did not implement <xref:System.IFormattable>, the runtime ignored the format string and instead called the <xref:System.TimeSpan.ToString?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="d1a81-134">これは、書式指定文字列に書式設定操作に影響はありません、その存在が発生しないことを意味する<xref:System.FormatException>します。</span><span class="sxs-lookup"><span data-stu-id="d1a81-134">This means that, although the format strings had no effect on the formatting operation, their presence did not result in a <xref:System.FormatException>.</span></span>  
  
 <span data-ttu-id="d1a81-135">レガシ コードに渡します複合メソッドと、無効な形式の文字列の書式を指定し、そのコードを再コンパイルできない場合は、使用することができます、`<TimeSpan_LegacyFormatMode>`要素、従来の復元を<xref:System.TimeSpan>動作します。</span><span class="sxs-lookup"><span data-stu-id="d1a81-135">For cases in which legacy code passes a composite formatting method and an invalid format string, and that code cannot be recompiled, you can use the `<TimeSpan_LegacyFormatMode>` element to restore the legacy <xref:System.TimeSpan> behavior.</span></span> <span data-ttu-id="d1a81-136">設定すると、`enabled`をこの要素の属性`true`複合への呼び出しでメソッドの結果を書式設定、<xref:System.TimeSpan.ToString?displayProperty=nameWithType>なく<xref:System.TimeSpan.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>、および<xref:System.FormatException>はスローされません。</span><span class="sxs-lookup"><span data-stu-id="d1a81-136">When you set the `enabled` attribute of this element to `true`, the composite formatting method results in a call to <xref:System.TimeSpan.ToString?displayProperty=nameWithType> rather than <xref:System.TimeSpan.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>, and a <xref:System.FormatException> is not thrown.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d1a81-137">例</span><span class="sxs-lookup"><span data-stu-id="d1a81-137">Example</span></span>  
 <span data-ttu-id="d1a81-138">次の例では、インスタンス化、<xref:System.TimeSpan>オブジェクトとそれをフォーマットしよう、<xref:System.String.Format%28System.String%2CSystem.Object%29?displayProperty=nameWithType>サポートされていない標準書式指定文字列を使用してメソッド。</span><span class="sxs-lookup"><span data-stu-id="d1a81-138">The following example instantiates a <xref:System.TimeSpan> object and attempts to format it with the <xref:System.String.Format%28System.String%2CSystem.Object%29?displayProperty=nameWithType> method by using an unsupported standard format string.</span></span>  
  
 [!code-csharp[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/timespan.breakingchanges/cs/legacyformatmode1.cs#1)]
 [!code-vb[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/timespan.breakingchanges/vb/legacyformatmode1.vb#1)]  
  
 <span data-ttu-id="d1a81-139">の例を実行すると、[!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)]か以前のバージョンで、次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d1a81-139">When you run the example on the [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)] or on an earlier version, it displays the following output:</span></span>  
  
```  
12:30:45  
```  
  
 <span data-ttu-id="d1a81-140">一方、著しく出力例を実行する場合、[!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)]以降のバージョン。</span><span class="sxs-lookup"><span data-stu-id="d1a81-140">This differs markedly from the output if you run the example on the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] or later version:</span></span>  
  
```  
Invalid Format  
```  
  
 <span data-ttu-id="d1a81-141">ただし、例を次の構成ファイルを追加する場合のディレクトリで例を実行し、[!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)]または以降のバージョンが、出力が実行した場合に、例によって生成されるのと同じ[!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="d1a81-141">However, if you add the following configuration file to the example's directory and then run the example on the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] or later version, the output is identical to that produced by the example when it is run on [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)].</span></span>  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <TimeSpan_LegacyFormatMode enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d1a81-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="d1a81-142">See also</span></span>

- [<span data-ttu-id="d1a81-143">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="d1a81-143">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="d1a81-144">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="d1a81-144">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
