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
ms.openlocfilehash: 9d9eedf52f5d711412e4549e39e6ea23abb68ff3
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2019
ms.locfileid: "73968908"
---
# <a name="timespan_legacyformatmode-element"></a><span data-ttu-id="f2c37-102">\<TimeSpan_LegacyFormatMode > 要素</span><span class="sxs-lookup"><span data-stu-id="f2c37-102">\<TimeSpan_LegacyFormatMode> Element</span></span>

<span data-ttu-id="f2c37-103"><xref:System.TimeSpan?displayProperty=nameWithType> 値を持つ書式設定操作で、ランタイムが従来の動作を保持するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="f2c37-103">Determines whether the runtime preserves legacy behavior in formatting operations with <xref:System.TimeSpan?displayProperty=nameWithType> values.</span></span>

<span data-ttu-id="f2c37-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f2c37-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f2c37-105">&nbsp;&nbsp;[ **\<runtime>** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="f2c37-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="f2c37-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<TimeSpan_LegacyFormatMode >**</span><span class="sxs-lookup"><span data-stu-id="f2c37-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<TimeSpan_LegacyFormatMode>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="f2c37-107">構文</span><span class="sxs-lookup"><span data-stu-id="f2c37-107">Syntax</span></span>

```xml
<TimeSpan_LegacyFormatMode
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f2c37-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="f2c37-108">Attributes and Elements</span></span>

<span data-ttu-id="f2c37-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="f2c37-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="f2c37-110">属性</span><span class="sxs-lookup"><span data-stu-id="f2c37-110">Attributes</span></span>

|<span data-ttu-id="f2c37-111">属性</span><span class="sxs-lookup"><span data-stu-id="f2c37-111">Attribute</span></span>|<span data-ttu-id="f2c37-112">説明</span><span class="sxs-lookup"><span data-stu-id="f2c37-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="f2c37-113">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="f2c37-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="f2c37-114">ランタイムが <xref:System.TimeSpan?displayProperty=nameWithType> 値に対して従来の書式設定動作を使用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="f2c37-114">Specifies whether the runtime uses legacy formatting behavior with <xref:System.TimeSpan?displayProperty=nameWithType> values.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="f2c37-115">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="f2c37-115">enabled Attribute</span></span>

|<span data-ttu-id="f2c37-116">[値]</span><span class="sxs-lookup"><span data-stu-id="f2c37-116">Value</span></span>|<span data-ttu-id="f2c37-117">説明</span><span class="sxs-lookup"><span data-stu-id="f2c37-117">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="f2c37-118">ランタイムでは、従来の書式設定動作は復元されません。</span><span class="sxs-lookup"><span data-stu-id="f2c37-118">The runtime does not restore legacy formatting behavior.</span></span>|
|`true`|<span data-ttu-id="f2c37-119">ランタイムは、従来の書式設定動作を復元します。</span><span class="sxs-lookup"><span data-stu-id="f2c37-119">The runtime restores legacy formatting behavior.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="f2c37-120">子要素</span><span class="sxs-lookup"><span data-stu-id="f2c37-120">Child Elements</span></span>

<span data-ttu-id="f2c37-121">なし。</span><span class="sxs-lookup"><span data-stu-id="f2c37-121">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f2c37-122">親要素</span><span class="sxs-lookup"><span data-stu-id="f2c37-122">Parent Elements</span></span>

|<span data-ttu-id="f2c37-123">要素</span><span class="sxs-lookup"><span data-stu-id="f2c37-123">Element</span></span>|<span data-ttu-id="f2c37-124">説明</span><span class="sxs-lookup"><span data-stu-id="f2c37-124">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="f2c37-125">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="f2c37-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="f2c37-126">ランタイム初期化オプションに関する情報を含んでいます。</span><span class="sxs-lookup"><span data-stu-id="f2c37-126">Contains information about runtime initialization options.</span></span>|

## <a name="remarks"></a><span data-ttu-id="f2c37-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="f2c37-127">Remarks</span></span>

<span data-ttu-id="f2c37-128">.NET Framework 4 以降、<xref:System.TimeSpan?displayProperty=nameWithType> 構造体は <xref:System.IFormattable> インターフェイスを実装し、標準およびカスタムの書式指定文字列を使用した書式設定操作をサポートします。</span><span class="sxs-lookup"><span data-stu-id="f2c37-128">Starting with the .NET Framework 4, the <xref:System.TimeSpan?displayProperty=nameWithType> structure implements the <xref:System.IFormattable> interface and supports formatting operations with standard and custom format strings.</span></span> <span data-ttu-id="f2c37-129">解析メソッドで、サポートされていない書式指定子または書式指定文字列が検出されると、<xref:System.FormatException>がスローされます。</span><span class="sxs-lookup"><span data-stu-id="f2c37-129">If a parsing method encounters an unsupported format specifier or format string, it throws a <xref:System.FormatException>.</span></span>

<span data-ttu-id="f2c37-130">以前のバージョンの .NET Framework では、<xref:System.TimeSpan> 構造体は <xref:System.IFormattable> を実装しておらず、書式指定文字列をサポートしていませんでした。</span><span class="sxs-lookup"><span data-stu-id="f2c37-130">In previous versions of the .NET Framework, the <xref:System.TimeSpan> structure did not implement <xref:System.IFormattable> and did not support format strings.</span></span> <span data-ttu-id="f2c37-131">しかし、多くの開発者は、<xref:System.TimeSpan> が一連の書式指定文字列をサポートし、<xref:System.String.Format%2A?displayProperty=nameWithType>などのメソッドを使用して[複合書式指定操作](../../../../standard/base-types/composite-formatting.md)で使用したことを誤って想定していました。</span><span class="sxs-lookup"><span data-stu-id="f2c37-131">However, many developers mistakenly assumed that <xref:System.TimeSpan> did support a set of format strings and used them in [composite formatting operations](../../../../standard/base-types/composite-formatting.md) with methods such as <xref:System.String.Format%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="f2c37-132">通常、型が <xref:System.IFormattable> を実装し、書式指定文字列をサポートしている場合、サポートされていない書式指定文字列を使用した書式指定メソッドの呼び出しは、通常、<xref:System.FormatException>をスローします。</span><span class="sxs-lookup"><span data-stu-id="f2c37-132">Ordinarily, if a type implements <xref:System.IFormattable> and supports format strings, calls to formatting methods with unsupported format strings usually throw a <xref:System.FormatException>.</span></span> <span data-ttu-id="f2c37-133">ただし、<xref:System.TimeSpan> は <xref:System.IFormattable>を実装しなかったため、ランタイムは書式設定文字列を無視し、代わりに <xref:System.TimeSpan.ToString?displayProperty=nameWithType> メソッドと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="f2c37-133">However, because <xref:System.TimeSpan> did not implement <xref:System.IFormattable>, the runtime ignored the format string and instead called the <xref:System.TimeSpan.ToString?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="f2c37-134">これは、書式指定文字列が書式設定操作に影響を与えないことを意味しますが、その存在は <xref:System.FormatException>になりませんでした。</span><span class="sxs-lookup"><span data-stu-id="f2c37-134">This means that, although the format strings had no effect on the formatting operation, their presence did not result in a <xref:System.FormatException>.</span></span>

<span data-ttu-id="f2c37-135">レガシコードによって複合書式指定メソッドと無効な書式指定文字列が渡され、そのコードを再コンパイルできない場合は、`<TimeSpan_LegacyFormatMode>` 要素を使用して、従来の <xref:System.TimeSpan> の動作を復元できます。</span><span class="sxs-lookup"><span data-stu-id="f2c37-135">For cases in which legacy code passes a composite formatting method and an invalid format string, and that code cannot be recompiled, you can use the `<TimeSpan_LegacyFormatMode>` element to restore the legacy <xref:System.TimeSpan> behavior.</span></span> <span data-ttu-id="f2c37-136">この要素の `enabled` 属性を `true`に設定すると、複合書式指定メソッドによって <xref:System.TimeSpan.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>ではなく <xref:System.TimeSpan.ToString?displayProperty=nameWithType> が呼び出され、<xref:System.FormatException> はスローされません。</span><span class="sxs-lookup"><span data-stu-id="f2c37-136">When you set the `enabled` attribute of this element to `true`, the composite formatting method results in a call to <xref:System.TimeSpan.ToString?displayProperty=nameWithType> rather than <xref:System.TimeSpan.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>, and a <xref:System.FormatException> is not thrown.</span></span>

## <a name="example"></a><span data-ttu-id="f2c37-137">例</span><span class="sxs-lookup"><span data-stu-id="f2c37-137">Example</span></span>

<span data-ttu-id="f2c37-138">次の例では、<xref:System.TimeSpan> オブジェクトをインスタンス化し、サポートされていない標準書式指定文字列を使用して、<xref:System.String.Format%28System.String%2CSystem.Object%29?displayProperty=nameWithType> メソッドで書式設定しようとしています。</span><span class="sxs-lookup"><span data-stu-id="f2c37-138">The following example instantiates a <xref:System.TimeSpan> object and attempts to format it with the <xref:System.String.Format%28System.String%2CSystem.Object%29?displayProperty=nameWithType> method by using an unsupported standard format string.</span></span>

[!code-csharp[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/timespan.breakingchanges/cs/legacyformatmode1.cs#1)]
[!code-vb[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/timespan.breakingchanges/vb/legacyformatmode1.vb#1)]

<span data-ttu-id="f2c37-139">.NET Framework 3.5 またはそれ以前のバージョンでこの例を実行すると、次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f2c37-139">When you run the example on the .NET Framework 3.5 or on an earlier version, it displays the following output:</span></span>

```console
12:30:45
```

<span data-ttu-id="f2c37-140">これは、.NET Framework 4 以降のバージョンで例を実行した場合の出力とは大きく異なります。</span><span class="sxs-lookup"><span data-stu-id="f2c37-140">This differs markedly from the output if you run the example on the .NET Framework 4 or later version:</span></span>

```console
Invalid Format
```

<span data-ttu-id="f2c37-141">ただし、次の構成ファイルを例のディレクトリに追加した後、.NET Framework 4 以降のバージョンでこの例を実行すると、出力は、.NET Framework 3.5 で実行されたときに例で生成されたものと同じになります。</span><span class="sxs-lookup"><span data-stu-id="f2c37-141">However, if you add the following configuration file to the example's directory and then run the example on the .NET Framework 4 or later version, the output is identical to that produced by the example when it is run on .NET Framework 3.5.</span></span>

```xml
<?xml version ="1.0"?>
<configuration>
   <runtime>
      <TimeSpan_LegacyFormatMode enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="f2c37-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="f2c37-142">See also</span></span>

- [<span data-ttu-id="f2c37-143">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="f2c37-143">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="f2c37-144">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="f2c37-144">Configuration File Schema</span></span>](../index.md)
