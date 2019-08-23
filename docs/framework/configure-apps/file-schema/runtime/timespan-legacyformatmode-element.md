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
ms.openlocfilehash: f16a2bbd2470b4aec9e95ab67ccb0e736c4c6d02
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920688"
---
# <a name="timespan_legacyformatmode-element"></a><span data-ttu-id="298e6-102">\<TimeSpan_LegacyFormatMode > 要素</span><span class="sxs-lookup"><span data-stu-id="298e6-102">\<TimeSpan_LegacyFormatMode> Element</span></span>

<span data-ttu-id="298e6-103">値を使用して<xref:System.TimeSpan?displayProperty=nameWithType> 、ランタイムが書式設定操作で従来の動作を保持するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="298e6-103">Determines whether the runtime preserves legacy behavior in formatting operations with <xref:System.TimeSpan?displayProperty=nameWithType> values.</span></span>

<span data-ttu-id="298e6-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="298e6-104">\<configuration>\</span></span>
<span data-ttu-id="298e6-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="298e6-105">\<runtime>\</span></span>
<span data-ttu-id="298e6-106">\<TimeSpan_LegacyFormatMode ></span><span class="sxs-lookup"><span data-stu-id="298e6-106">\<TimeSpan_LegacyFormatMode></span></span>

## <a name="syntax"></a><span data-ttu-id="298e6-107">構文</span><span class="sxs-lookup"><span data-stu-id="298e6-107">Syntax</span></span>

```xml
<TimeSpan_LegacyFormatMode
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="298e6-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="298e6-108">Attributes and Elements</span></span>

<span data-ttu-id="298e6-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="298e6-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="298e6-110">属性</span><span class="sxs-lookup"><span data-stu-id="298e6-110">Attributes</span></span>

|<span data-ttu-id="298e6-111">属性</span><span class="sxs-lookup"><span data-stu-id="298e6-111">Attribute</span></span>|<span data-ttu-id="298e6-112">説明</span><span class="sxs-lookup"><span data-stu-id="298e6-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="298e6-113">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="298e6-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="298e6-114">ランタイムが従来の書式設定動作を値<xref:System.TimeSpan?displayProperty=nameWithType>と共に使用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="298e6-114">Specifies whether the runtime uses legacy formatting behavior with <xref:System.TimeSpan?displayProperty=nameWithType> values.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="298e6-115">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="298e6-115">enabled Attribute</span></span>

|<span data-ttu-id="298e6-116">値</span><span class="sxs-lookup"><span data-stu-id="298e6-116">Value</span></span>|<span data-ttu-id="298e6-117">説明</span><span class="sxs-lookup"><span data-stu-id="298e6-117">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="298e6-118">ランタイムでは、従来の書式設定動作は復元されません。</span><span class="sxs-lookup"><span data-stu-id="298e6-118">The runtime does not restore legacy formatting behavior.</span></span>|
|`true`|<span data-ttu-id="298e6-119">ランタイムは、従来の書式設定動作を復元します。</span><span class="sxs-lookup"><span data-stu-id="298e6-119">The runtime restores legacy formatting behavior.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="298e6-120">子要素</span><span class="sxs-lookup"><span data-stu-id="298e6-120">Child Elements</span></span>

<span data-ttu-id="298e6-121">なし。</span><span class="sxs-lookup"><span data-stu-id="298e6-121">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="298e6-122">親要素</span><span class="sxs-lookup"><span data-stu-id="298e6-122">Parent Elements</span></span>

|<span data-ttu-id="298e6-123">要素</span><span class="sxs-lookup"><span data-stu-id="298e6-123">Element</span></span>|<span data-ttu-id="298e6-124">説明</span><span class="sxs-lookup"><span data-stu-id="298e6-124">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="298e6-125">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="298e6-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="298e6-126">ランタイム初期化オプションに関する情報を含んでいます。</span><span class="sxs-lookup"><span data-stu-id="298e6-126">Contains information about runtime initialization options.</span></span>|

## <a name="remarks"></a><span data-ttu-id="298e6-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="298e6-127">Remarks</span></span>

<span data-ttu-id="298e6-128">.NET Framework 4 以降では、構造<xref:System.TimeSpan?displayProperty=nameWithType>体は<xref:System.IFormattable>インターフェイスを実装し、標準およびカスタムの書式指定文字列を使用した書式設定操作をサポートします。</span><span class="sxs-lookup"><span data-stu-id="298e6-128">Starting with the .NET Framework 4, the <xref:System.TimeSpan?displayProperty=nameWithType> structure implements the <xref:System.IFormattable> interface and supports formatting operations with standard and custom format strings.</span></span> <span data-ttu-id="298e6-129">解析メソッドで、サポートさ<xref:System.FormatException>れていない書式指定子または書式指定文字列が検出されると、がスローされます。</span><span class="sxs-lookup"><span data-stu-id="298e6-129">If a parsing method encounters an unsupported format specifier or format string, it throws a <xref:System.FormatException>.</span></span>

<span data-ttu-id="298e6-130">以前のバージョンの .NET Framework では、 <xref:System.TimeSpan>構造体がを<xref:System.IFormattable>実装しておらず、書式指定文字列をサポートしていませんでした。</span><span class="sxs-lookup"><span data-stu-id="298e6-130">In previous versions of the .NET Framework, the <xref:System.TimeSpan> structure did not implement <xref:System.IFormattable> and did not support format strings.</span></span> <span data-ttu-id="298e6-131">しかし、多くの開発者は<xref:System.TimeSpan> 、書式指定文字列のセットをサポートし、など<xref:System.String.Format%2A?displayProperty=nameWithType>のメソッドを使用して[複合書式指定操作](../../../../standard/base-types/composite-formatting.md)で使用したことを誤って想定していました。</span><span class="sxs-lookup"><span data-stu-id="298e6-131">However, many developers mistakenly assumed that <xref:System.TimeSpan> did support a set of format strings and used them in [composite formatting operations](../../../../standard/base-types/composite-formatting.md) with methods such as <xref:System.String.Format%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="298e6-132">通常、型がを実装<xref:System.IFormattable>し、書式指定文字列をサポートする場合、サポートされていない<xref:System.FormatException>書式指定文字列を使用した書式指定メソッドの呼び出しは、通常、をスローします。</span><span class="sxs-lookup"><span data-stu-id="298e6-132">Ordinarily, if a type implements <xref:System.IFormattable> and supports format strings, calls to formatting methods with unsupported format strings usually throw a <xref:System.FormatException>.</span></span> <span data-ttu-id="298e6-133">ただし、が<xref:System.TimeSpan>実装<xref:System.IFormattable>されていないため、ランタイムは書式指定文字列を<xref:System.TimeSpan.ToString?displayProperty=nameWithType>無視し、代わりにメソッドを呼び出しました。</span><span class="sxs-lookup"><span data-stu-id="298e6-133">However, because <xref:System.TimeSpan> did not implement <xref:System.IFormattable>, the runtime ignored the format string and instead called the <xref:System.TimeSpan.ToString?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="298e6-134">これは、書式指定文字列が書式設定操作に影響を与えないことを意味し<xref:System.FormatException>ますが、その存在はになりませんでした。</span><span class="sxs-lookup"><span data-stu-id="298e6-134">This means that, although the format strings had no effect on the formatting operation, their presence did not result in a <xref:System.FormatException>.</span></span>

<span data-ttu-id="298e6-135">レガシコードによって複合書式指定メソッドと無効な書式指定文字列が渡され、そのコードを再コンパイルできない場合は`<TimeSpan_LegacyFormatMode>` 、要素を使用し<xref:System.TimeSpan>て従来の動作を復元できます。</span><span class="sxs-lookup"><span data-stu-id="298e6-135">For cases in which legacy code passes a composite formatting method and an invalid format string, and that code cannot be recompiled, you can use the `<TimeSpan_LegacyFormatMode>` element to restore the legacy <xref:System.TimeSpan> behavior.</span></span> <span data-ttu-id="298e6-136">`enabled`この要素の属性をに<xref:System.TimeSpan.ToString?displayProperty=nameWithType> `true`設定すると、複合書式指定メソッドによってではなく<xref:System.TimeSpan.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> <xref:System.FormatException>が呼び出され、がスローされません。</span><span class="sxs-lookup"><span data-stu-id="298e6-136">When you set the `enabled` attribute of this element to `true`, the composite formatting method results in a call to <xref:System.TimeSpan.ToString?displayProperty=nameWithType> rather than <xref:System.TimeSpan.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>, and a <xref:System.FormatException> is not thrown.</span></span>

## <a name="example"></a><span data-ttu-id="298e6-137">例</span><span class="sxs-lookup"><span data-stu-id="298e6-137">Example</span></span>

<span data-ttu-id="298e6-138">次の例では<xref:System.TimeSpan> 、オブジェクトをインスタンス化し、サポート<xref:System.String.Format%28System.String%2CSystem.Object%29?displayProperty=nameWithType>されていない標準書式指定文字列を使用して、メソッドを使用して書式設定を試みます。</span><span class="sxs-lookup"><span data-stu-id="298e6-138">The following example instantiates a <xref:System.TimeSpan> object and attempts to format it with the <xref:System.String.Format%28System.String%2CSystem.Object%29?displayProperty=nameWithType> method by using an unsupported standard format string.</span></span>

[!code-csharp[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/timespan.breakingchanges/cs/legacyformatmode1.cs#1)]
[!code-vb[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/timespan.breakingchanges/vb/legacyformatmode1.vb#1)]

<span data-ttu-id="298e6-139">.NET Framework 3.5 またはそれ以前のバージョンでこの例を実行すると、次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="298e6-139">When you run the example on the .NET Framework 3.5 or on an earlier version, it displays the following output:</span></span>

```
12:30:45
```

<span data-ttu-id="298e6-140">これは、.NET Framework 4 以降のバージョンで例を実行した場合の出力とは大きく異なります。</span><span class="sxs-lookup"><span data-stu-id="298e6-140">This differs markedly from the output if you run the example on the .NET Framework 4 or later version:</span></span>

```
Invalid Format
```

<span data-ttu-id="298e6-141">ただし、次の構成ファイルを例のディレクトリに追加した後、.NET Framework 4 以降のバージョンでこの例を実行すると、出力は、.NET Framework 3.5 で実行されたときに例で生成されたものと同じになります。</span><span class="sxs-lookup"><span data-stu-id="298e6-141">However, if you add the following configuration file to the example's directory and then run the example on the .NET Framework 4 or later version, the output is identical to that produced by the example when it is run on .NET Framework 3.5.</span></span>

```xml
<?xml version ="1.0"?>
<configuration>
   <runtime>
      <TimeSpan_LegacyFormatMode enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="298e6-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="298e6-142">See also</span></span>

- [<span data-ttu-id="298e6-143">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="298e6-143">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="298e6-144">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="298e6-144">Configuration File Schema</span></span>](../index.md)
