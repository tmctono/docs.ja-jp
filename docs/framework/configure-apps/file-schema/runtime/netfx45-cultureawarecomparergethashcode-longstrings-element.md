---
title: <NetFx45_CultureAwareComparerGetHashCode_LongStrings> 要素
ms.date: 03/30/2017
helpviewer_keywords:
- NetFx45_CultureAwareComparerGetHashCode_LongStrings element
- <NetFx45_CultureAwareComparerGetHashCode_LongStrings> element
- GetHashCode method
- hash codes, calculating
ms.assetid: 3a5f38d1-ebc8-44de-aaeb-2929f6e6b48f
ms.openlocfilehash: 413eb6c6e61b509135601c65cf045eabd849e8b3
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802115"
---
# <a name="netfx45_cultureawarecomparergethashcode_longstrings-element"></a><span data-ttu-id="cbf7d-102">\<NetFx45_CultureAwareComparerGetHashCode_LongStrings> 要素</span><span class="sxs-lookup"><span data-stu-id="cbf7d-102">\<NetFx45_CultureAwareComparerGetHashCode_LongStrings> Element</span></span>

<span data-ttu-id="cbf7d-103">ランタイムが <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> メソッドで固定量のメモリを使用してハッシュ コードを計算するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="cbf7d-103">Specifies whether the runtime uses a fixed amount of memory to calculate hash codes for the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="cbf7d-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="cbf7d-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="cbf7d-105">&nbsp;&nbsp;[ **\<runtime>** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="cbf7d-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="cbf7d-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<NetFx45_CultureAwareComparerGetHashCode_LongStrings >**</span><span class="sxs-lookup"><span data-stu-id="cbf7d-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<NetFx45_CultureAwareComparerGetHashCode_LongStrings>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="cbf7d-107">構文</span><span class="sxs-lookup"><span data-stu-id="cbf7d-107">Syntax</span></span>

```xml
<NetFx45_CultureAwareComparerGetHashCode_LongStrings enabled="0|1">
```

## <a name="attributes-and-elements"></a><span data-ttu-id="cbf7d-108">属性と要素</span><span class="sxs-lookup"><span data-stu-id="cbf7d-108">Attributes and Elements</span></span>

<span data-ttu-id="cbf7d-109">次のセクションでは、属性、子要素、親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="cbf7d-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="cbf7d-110">属性</span><span class="sxs-lookup"><span data-stu-id="cbf7d-110">Attributes</span></span>

|<span data-ttu-id="cbf7d-111">属性</span><span class="sxs-lookup"><span data-stu-id="cbf7d-111">Attribute</span></span>|<span data-ttu-id="cbf7d-112">説明</span><span class="sxs-lookup"><span data-stu-id="cbf7d-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="cbf7d-113">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="cbf7d-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="cbf7d-114">ハッシュ コードを計算するときに、共通言語ランタイムが固定メモリを割り当てるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="cbf7d-114">Specifies whether the common language runtime allocates a fixed amount of memory when calculating hash codes.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="cbf7d-115">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="cbf7d-115">enabled Attribute</span></span>

|<span data-ttu-id="cbf7d-116">Value</span><span class="sxs-lookup"><span data-stu-id="cbf7d-116">Value</span></span>|<span data-ttu-id="cbf7d-117">説明</span><span class="sxs-lookup"><span data-stu-id="cbf7d-117">Description</span></span>|
|-----------|-----------------|
|<span data-ttu-id="cbf7d-118">0</span><span class="sxs-lookup"><span data-stu-id="cbf7d-118">0</span></span>|<span data-ttu-id="cbf7d-119">共通言語ランタイムが <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> メソッドに可変メモリを割り当ててハッシュ コードを計算します。</span><span class="sxs-lookup"><span data-stu-id="cbf7d-119">The common language runtime allocates a variable amount of memory for the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method to calculate hash codes.</span></span> <span data-ttu-id="cbf7d-120">これは既定です。</span><span class="sxs-lookup"><span data-stu-id="cbf7d-120">This is the default.</span></span>|
|<span data-ttu-id="cbf7d-121">1</span><span class="sxs-lookup"><span data-stu-id="cbf7d-121">1</span></span>|<span data-ttu-id="cbf7d-122">共通言語ランタイムが <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> メソッドに固定メモリを割り当ててハッシュ コードを計算します。</span><span class="sxs-lookup"><span data-stu-id="cbf7d-122">The common language runtime allocates a fixed amount of memory for the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method to calculate hash codes.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="cbf7d-123">子要素</span><span class="sxs-lookup"><span data-stu-id="cbf7d-123">Child Elements</span></span>

<span data-ttu-id="cbf7d-124">ありません。</span><span class="sxs-lookup"><span data-stu-id="cbf7d-124">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="cbf7d-125">親要素</span><span class="sxs-lookup"><span data-stu-id="cbf7d-125">Parent Elements</span></span>

|<span data-ttu-id="cbf7d-126">要素</span><span class="sxs-lookup"><span data-stu-id="cbf7d-126">Element</span></span>|<span data-ttu-id="cbf7d-127">説明</span><span class="sxs-lookup"><span data-stu-id="cbf7d-127">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="cbf7d-128">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="cbf7d-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="cbf7d-129">ランタイム初期化オプションに関する情報を含んでいます。</span><span class="sxs-lookup"><span data-stu-id="cbf7d-129">Contains information about runtime initialization options.</span></span>|

## <a name="remarks"></a><span data-ttu-id="cbf7d-130">Remarks</span><span class="sxs-lookup"><span data-stu-id="cbf7d-130">Remarks</span></span>

<span data-ttu-id="cbf7d-131">既定では、共通言語ランタイムが <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> メソッドに可変メモリを割り当て、メソッドが非常に長い文字列 (数メガバイト以上) のハッシュ コードを計算しようとすると <xref:System.ArgumentException> 例外がスローされることがあります。</span><span class="sxs-lookup"><span data-stu-id="cbf7d-131">By default, the common language runtime allocates a variable amount of memory for the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method, and an <xref:System.ArgumentException> can be thrown when the method attempts to compute the hash code of very large strings (over several million characters long).</span></span> <span data-ttu-id="cbf7d-132">この要素をアプリケーション構成ファイルに追加し、 `enabled` 属性を 1 に設定すると、 <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> メソッドでハッシュ コードの計算時に固定メモリを割り当てる別のアルゴリズムを使用することを指定できます。</span><span class="sxs-lookup"><span data-stu-id="cbf7d-132">By adding this element to an application configuration file and setting its `enabled` attribute to "1", you can specify that the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method use an alternate algorithm that allocates a fixed amount of memory for the computation of hash codes.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cbf7d-133">`<NetFx45_CultureAwareComparerGetHashCode_LongStrings>` 要素は、Windows 8 以降のバージョンでは使用されません。</span><span class="sxs-lookup"><span data-stu-id="cbf7d-133">The `<NetFx45_CultureAwareComparerGetHashCode_LongStrings>` element is not used in Windows 8 and later versions.</span></span>

## <a name="see-also"></a><span data-ttu-id="cbf7d-134">参照</span><span class="sxs-lookup"><span data-stu-id="cbf7d-134">See also</span></span>

- <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>
- [<span data-ttu-id="cbf7d-135">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="cbf7d-135">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="cbf7d-136">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="cbf7d-136">Configuration File Schema</span></span>](../index.md)
