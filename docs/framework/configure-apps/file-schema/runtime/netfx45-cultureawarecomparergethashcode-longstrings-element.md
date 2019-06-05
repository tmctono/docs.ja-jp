---
title: <NetFx45_CultureAwareComparerGetHashCode_LongStrings> 要素
ms.date: 03/30/2017
helpviewer_keywords:
- NetFx45_CultureAwareComparerGetHashCode_LongStrings element
- <NetFx45_CultureAwareComparerGetHashCode_LongStrings> element
- GetHashCode method
- hash codes, calculating
ms.assetid: 3a5f38d1-ebc8-44de-aaeb-2929f6e6b48f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 23917977add2343732957eaa8dad5d2176315acf
ms.sourcegitcommit: d8ebe0ee198f5d38387a80ba50f395386779334f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/05/2019
ms.locfileid: "66689865"
---
# <a name="netfx45cultureawarecomparergethashcodelongstrings-element"></a><span data-ttu-id="75038-102">\<NetFx45_CultureAwareComparerGetHashCode_LongStrings > 要素</span><span class="sxs-lookup"><span data-stu-id="75038-102">\<NetFx45_CultureAwareComparerGetHashCode_LongStrings> Element</span></span>

<span data-ttu-id="75038-103">ランタイムが <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> メソッドで固定量のメモリを使用してハッシュ コードを計算するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="75038-103">Specifies whether the runtime uses a fixed amount of memory to calculate hash codes for the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="75038-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="75038-104">\<configuration>\\</span></span>
<span data-ttu-id="75038-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="75038-105">\<runtime>\\</span></span>
<span data-ttu-id="75038-106">\<NetFx45_CultureAwareComparerGetHashCode_LongStrings></span><span class="sxs-lookup"><span data-stu-id="75038-106">\<NetFx45_CultureAwareComparerGetHashCode_LongStrings></span></span>

## <a name="syntax"></a><span data-ttu-id="75038-107">構文</span><span class="sxs-lookup"><span data-stu-id="75038-107">Syntax</span></span>

```xml
<NetFx45_CultureAwareComparerGetHashCode_LongStrings enabled="0|1">
```

## <a name="attributes-and-elements"></a><span data-ttu-id="75038-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="75038-108">Attributes and Elements</span></span>

<span data-ttu-id="75038-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="75038-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="75038-110">属性</span><span class="sxs-lookup"><span data-stu-id="75038-110">Attributes</span></span>

|<span data-ttu-id="75038-111">属性</span><span class="sxs-lookup"><span data-stu-id="75038-111">Attribute</span></span>|<span data-ttu-id="75038-112">説明</span><span class="sxs-lookup"><span data-stu-id="75038-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="75038-113">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="75038-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="75038-114">ハッシュ コードを計算するときに、共通言語ランタイムが固定メモリを割り当てるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="75038-114">Specifies whether the common language runtime allocates a fixed amount of memory when calculating hash codes.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="75038-115">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="75038-115">enabled Attribute</span></span>

|<span data-ttu-id="75038-116">値</span><span class="sxs-lookup"><span data-stu-id="75038-116">Value</span></span>|<span data-ttu-id="75038-117">説明</span><span class="sxs-lookup"><span data-stu-id="75038-117">Description</span></span>|
|-----------|-----------------|
|<span data-ttu-id="75038-118">0</span><span class="sxs-lookup"><span data-stu-id="75038-118">0</span></span>|<span data-ttu-id="75038-119">共通言語ランタイムが <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> メソッドに可変メモリを割り当ててハッシュ コードを計算します。</span><span class="sxs-lookup"><span data-stu-id="75038-119">The common language runtime allocates a variable amount of memory for the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method to calculate hash codes.</span></span> <span data-ttu-id="75038-120">既定値です。</span><span class="sxs-lookup"><span data-stu-id="75038-120">This is the default.</span></span>|
|<span data-ttu-id="75038-121">1</span><span class="sxs-lookup"><span data-stu-id="75038-121">1</span></span>|<span data-ttu-id="75038-122">共通言語ランタイムが <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> メソッドに固定メモリを割り当ててハッシュ コードを計算します。</span><span class="sxs-lookup"><span data-stu-id="75038-122">The common language runtime allocates a fixed amount of memory for the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method to calculate hash codes.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="75038-123">子要素</span><span class="sxs-lookup"><span data-stu-id="75038-123">Child Elements</span></span>

<span data-ttu-id="75038-124">なし。</span><span class="sxs-lookup"><span data-stu-id="75038-124">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="75038-125">親要素</span><span class="sxs-lookup"><span data-stu-id="75038-125">Parent Elements</span></span>

|<span data-ttu-id="75038-126">要素</span><span class="sxs-lookup"><span data-stu-id="75038-126">Element</span></span>|<span data-ttu-id="75038-127">説明</span><span class="sxs-lookup"><span data-stu-id="75038-127">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="75038-128">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="75038-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="75038-129">ランタイム初期化オプションに関する情報を含んでいます。</span><span class="sxs-lookup"><span data-stu-id="75038-129">Contains information about runtime initialization options.</span></span>|

## <a name="remarks"></a><span data-ttu-id="75038-130">Remarks</span><span class="sxs-lookup"><span data-stu-id="75038-130">Remarks</span></span>

<span data-ttu-id="75038-131">既定では、共通言語ランタイムが <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> メソッドに可変メモリを割り当て、メソッドが非常に長い文字列 (数メガバイト以上) のハッシュ コードを計算しようとすると <xref:System.ArgumentException> 例外がスローされることがあります。</span><span class="sxs-lookup"><span data-stu-id="75038-131">By default, the common language runtime allocates a variable amount of memory for the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method, and an <xref:System.ArgumentException> can be thrown when the method attempts to compute the hash code of very large strings (over several million characters long).</span></span> <span data-ttu-id="75038-132">この要素をアプリケーション構成ファイルに追加し、 `enabled` 属性を 1 に設定すると、 <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> メソッドでハッシュ コードの計算時に固定メモリを割り当てる別のアルゴリズムを使用することを指定できます。</span><span class="sxs-lookup"><span data-stu-id="75038-132">By adding this element to an application configuration file and setting its `enabled` attribute to "1", you can specify that the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method use an alternate algorithm that allocates a fixed amount of memory for the computation of hash codes.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="75038-133">`<NetFx45_CultureAwareComparerGetHashCode_LongStrings>` 要素は [!INCLUDE[win8](../../../../../includes/win8-md.md)] 以降のバージョンでは使用されません。</span><span class="sxs-lookup"><span data-stu-id="75038-133">The `<NetFx45_CultureAwareComparerGetHashCode_LongStrings>` element is not used in [!INCLUDE[win8](../../../../../includes/win8-md.md)] and later versions.</span></span>

## <a name="see-also"></a><span data-ttu-id="75038-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="75038-134">See also</span></span>

- <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>
- [<span data-ttu-id="75038-135">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="75038-135">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="75038-136">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="75038-136">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
