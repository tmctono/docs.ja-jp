---
title: 基本型
description: 'F # 言語で使用される基本的な基本型について説明します。'
ms.date: 08/15/2020
ms.openlocfilehash: 659ac8424c62985affcca1741e1b2a74c9c3ee8d
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/18/2020
ms.locfileid: "88557699"
---
# <a name="basic-types"></a><span data-ttu-id="0e47e-103">基本型</span><span class="sxs-lookup"><span data-stu-id="0e47e-103">Basic types</span></span>

<span data-ttu-id="0e47e-104">このトピックでは、F # 言語で定義されている基本型の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="0e47e-104">This topic lists the basic types that are defined in the F# language.</span></span> <span data-ttu-id="0e47e-105">これらの型は F # で最も基本的なものであり、ほぼすべての F # プログラムの基礎となります。</span><span class="sxs-lookup"><span data-stu-id="0e47e-105">These types are the most fundamental in F#, forming the basis of nearly every F# program.</span></span> <span data-ttu-id="0e47e-106">これらは、.NET プリミティブ型のスーパーセットです。</span><span class="sxs-lookup"><span data-stu-id="0e47e-106">They are a superset of .NET primitive types.</span></span>

|<span data-ttu-id="0e47e-107">Type</span><span class="sxs-lookup"><span data-stu-id="0e47e-107">Type</span></span>|<span data-ttu-id="0e47e-108">.NET の種類</span><span class="sxs-lookup"><span data-stu-id="0e47e-108">.NET type</span></span>|<span data-ttu-id="0e47e-109">説明</span><span class="sxs-lookup"><span data-stu-id="0e47e-109">Description</span></span>|<span data-ttu-id="0e47e-110">例</span><span class="sxs-lookup"><span data-stu-id="0e47e-110">Example</span></span>|
|----|---------|-----------|-------|
|`bool`|<xref:System.Boolean>|<span data-ttu-id="0e47e-111">設定可能な値は `true` および `false` です。</span><span class="sxs-lookup"><span data-stu-id="0e47e-111">Possible values are `true` and `false`.</span></span>|`true`/`false`|
|`byte`|<xref:System.Byte>|<span data-ttu-id="0e47e-112">0 ~ 255 の値。</span><span class="sxs-lookup"><span data-stu-id="0e47e-112">Values from 0 to 255.</span></span>|`1uy`|
|`sbyte`|<xref:System.SByte>|<span data-ttu-id="0e47e-113">-128 から127までの値。</span><span class="sxs-lookup"><span data-stu-id="0e47e-113">Values from -128 to 127.</span></span>|`1y`|
|`int16`|<xref:System.Int16>|<span data-ttu-id="0e47e-114">-32768 から32767までの値。</span><span class="sxs-lookup"><span data-stu-id="0e47e-114">Values from -32768 to 32767.</span></span>|`1s`|
|`uint16`|<xref:System.UInt16>|<span data-ttu-id="0e47e-115">0 ~ 65535 の値。</span><span class="sxs-lookup"><span data-stu-id="0e47e-115">Values from 0 to 65535.</span></span>|`1us`|
|`int`|<xref:System.Int32>|<span data-ttu-id="0e47e-116">-2147483648 から2147483647までの値。</span><span class="sxs-lookup"><span data-stu-id="0e47e-116">Values from -2,147,483,648 to 2,147,483,647.</span></span>|`1`|
|`uint`|<xref:System.UInt32>|<span data-ttu-id="0e47e-117">0 ~ 4294967295 の値。</span><span class="sxs-lookup"><span data-stu-id="0e47e-117">Values from 0 to 4,294,967,295.</span></span>|`1u`|
|`int64`|<xref:System.Int64>|<span data-ttu-id="0e47e-118">-9223372036854775808 ~ 9223372036854775807 の値。</span><span class="sxs-lookup"><span data-stu-id="0e47e-118">Values from -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807.</span></span>|`1L`|
|`uint64`|<xref:System.UInt64>|<span data-ttu-id="0e47e-119">0 ~ 18446744073709551615 の値。</span><span class="sxs-lookup"><span data-stu-id="0e47e-119">Values from 0 to 18,446,744,073,709,551,615.</span></span>|`1UL`|
|`nativeint`|<xref:System.IntPtr>|<span data-ttu-id="0e47e-120">符号付き整数としてのネイティブポインター。</span><span class="sxs-lookup"><span data-stu-id="0e47e-120">A native pointer as a signed integer.</span></span>|`nativeint 1`|
|`unativeint`|<xref:System.UIntPtr>|<span data-ttu-id="0e47e-121">符号なし整数としてのネイティブポインター。</span><span class="sxs-lookup"><span data-stu-id="0e47e-121">A native pointer as an unsigned integer.</span></span>|`unativeint 1`|
|`decimal`|<xref:System.Decimal>|<span data-ttu-id="0e47e-122">有効桁数が28以上の浮動小数点データ型。</span><span class="sxs-lookup"><span data-stu-id="0e47e-122">A floating point data type that has at least 28 significant digits.</span></span>|`1.0`|
|<span data-ttu-id="0e47e-123">`float`, `double`</span><span class="sxs-lookup"><span data-stu-id="0e47e-123">`float`, `double`</span></span>|<xref:System.Double>|<span data-ttu-id="0e47e-124">64ビットの浮動小数点型。</span><span class="sxs-lookup"><span data-stu-id="0e47e-124">A 64-bit floating point type.</span></span>|`1.0`|
|<span data-ttu-id="0e47e-125">`float32`, `single`</span><span class="sxs-lookup"><span data-stu-id="0e47e-125">`float32`, `single`</span></span>|<xref:System.Single>|<span data-ttu-id="0e47e-126">32ビットの浮動小数点型。</span><span class="sxs-lookup"><span data-stu-id="0e47e-126">A 32-bit floating point type.</span></span>|`1.0f`|
|`char`|<xref:System.Char>|<span data-ttu-id="0e47e-127">Unicode 文字の値。</span><span class="sxs-lookup"><span data-stu-id="0e47e-127">Unicode character values.</span></span>|`'c'`|
|`string`|<xref:System.String>|<span data-ttu-id="0e47e-128">Unicode テキスト。</span><span class="sxs-lookup"><span data-stu-id="0e47e-128">Unicode text.</span></span>|`"str"`|
|`unit`|<span data-ttu-id="0e47e-129">適用外</span><span class="sxs-lookup"><span data-stu-id="0e47e-129">not applicable</span></span>|<span data-ttu-id="0e47e-130">実際の値が存在しないことを示します。</span><span class="sxs-lookup"><span data-stu-id="0e47e-130">Indicates the absence of an actual value.</span></span> <span data-ttu-id="0e47e-131">型には、示されている仮値が1つだけあり `()` ます。</span><span class="sxs-lookup"><span data-stu-id="0e47e-131">The type has only one formal value, which is denoted `()`.</span></span> <span data-ttu-id="0e47e-132">単位値は、 `()` 値が必要であるものの、実際の値を使用できない、または意味を持つプレースホルダーとしてよく使用されます。</span><span class="sxs-lookup"><span data-stu-id="0e47e-132">The unit value, `()`, is often used as a placeholder where a value is needed but no real value is available or makes sense.</span></span>|`()`|

> [!NOTE]
> <span data-ttu-id="0e47e-133">[Bigint](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-bigint.html)型を使用して、整数値が64ビット整数型に対して大きすぎる計算を実行できます。</span><span class="sxs-lookup"><span data-stu-id="0e47e-133">You can perform computations with integers too big for the 64-bit integer type by using the [bigint](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-bigint.html) type.</span></span> <span data-ttu-id="0e47e-134">`bigint` は基本的な型とは見なされません。これは、の省略形です `System.Numerics.BigInteger` 。</span><span class="sxs-lookup"><span data-stu-id="0e47e-134">`bigint` is not considered a basic type; it is an abbreviation for `System.Numerics.BigInteger`.</span></span>

## <a name="see-also"></a><span data-ttu-id="0e47e-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="0e47e-135">See also</span></span>

- [<span data-ttu-id="0e47e-136">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="0e47e-136">F# Language Reference</span></span>](index.md)
