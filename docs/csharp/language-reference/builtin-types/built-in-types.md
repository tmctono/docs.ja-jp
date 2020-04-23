---
title: 組み込み型 - C# リファレンス
description: C# の組み込みの値型と参照型を示します
ms.date: 02/04/2020
helpviewer_keywords:
- types [C#], built-in
- built-in C# types
ms.assetid: 54f901f2-bf2f-472c-ae8d-73e8ecfc57fe
ms.openlocfilehash: bf8823c6674b1ff3f0028a50df8ce8d0f803cfc1
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389495"
---
# <a name="built-in-types-c-reference"></a><span data-ttu-id="c17fa-103">組み込み型 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="c17fa-103">Built-in types (C# reference)</span></span>

<span data-ttu-id="c17fa-104">C# の組み込みの[値](value-types.md)型を次の表に一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="c17fa-104">The following table lists the C# built-in [value](value-types.md) types:</span></span>

|<span data-ttu-id="c17fa-105">C# 型キーワード</span><span class="sxs-lookup"><span data-stu-id="c17fa-105">C# type keyword</span></span>|<span data-ttu-id="c17fa-106">.NET 型</span><span class="sxs-lookup"><span data-stu-id="c17fa-106">.NET type</span></span>|
|--------------|-------------------------|
|[`bool`](bool.md)|<xref:System.Boolean?displayProperty=nameWithType>|
|[`byte`](integral-numeric-types.md)|<xref:System.Byte?displayProperty=nameWithType>|
|[`sbyte`](integral-numeric-types.md)|<xref:System.SByte?displayProperty=nameWithType>|
|[`char`](char.md)|<xref:System.Char?displayProperty=nameWithType>|
|[`decimal`](floating-point-numeric-types.md)|<xref:System.Decimal?displayProperty=nameWithType>|
|[`double`](floating-point-numeric-types.md)|<xref:System.Double?displayProperty=nameWithType>|
|[`float`](floating-point-numeric-types.md)|<xref:System.Single?displayProperty=nameWithType>|
|[`int`](integral-numeric-types.md)|<xref:System.Int32?displayProperty=nameWithType>|
|[`uint`](integral-numeric-types.md)|<xref:System.UInt32?displayProperty=nameWithType>|
|[`long`](integral-numeric-types.md)|<xref:System.Int64?displayProperty=nameWithType>|
|[`ulong`](integral-numeric-types.md)|<xref:System.UInt64?displayProperty=nameWithType>|
|[`short`](integral-numeric-types.md)|<xref:System.Int16?displayProperty=nameWithType>|
|[`ushort`](integral-numeric-types.md)|<xref:System.UInt16?displayProperty=nameWithType>|

<span data-ttu-id="c17fa-107">C# の組み込みの[参照](../keywords/reference-types.md)型を次の表に一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="c17fa-107">The following table lists the C# built-in [reference](../keywords/reference-types.md) types:</span></span>

|<span data-ttu-id="c17fa-108">C# 型キーワード</span><span class="sxs-lookup"><span data-stu-id="c17fa-108">C# type keyword</span></span>|<span data-ttu-id="c17fa-109">.NET 型</span><span class="sxs-lookup"><span data-stu-id="c17fa-109">.NET type</span></span>|
|--------------|-------------------------|
|[`object`](reference-types.md#the-object-type)|<xref:System.Object?displayProperty=nameWithType>|
|[`string`](reference-types.md#the-string-type)|<xref:System.String?displayProperty=nameWithType>|

<span data-ttu-id="c17fa-110">上の表の左の列にある各 C# 型キーワードは、対応する .NET 型の別名です。</span><span class="sxs-lookup"><span data-stu-id="c17fa-110">In the preceding tables, each C# type keyword from the left column is an alias for the corresponding .NET type.</span></span> <span data-ttu-id="c17fa-111">これらは交換可能です。</span><span class="sxs-lookup"><span data-stu-id="c17fa-111">They are interchangeable.</span></span> <span data-ttu-id="c17fa-112">たとえば、次の宣言では、同じ型の変数が宣言されています。</span><span class="sxs-lookup"><span data-stu-id="c17fa-112">For example, the following declarations declare variables of the same type:</span></span>

```csharp
int a = 123;
System.Int32 b = 123;
```

<span data-ttu-id="c17fa-113">[`void`](void.md) キーワードで、値がないことが表されます。</span><span class="sxs-lookup"><span data-stu-id="c17fa-113">The [`void`](void.md) keyword represents the absence of a type.</span></span> <span data-ttu-id="c17fa-114">値を返さないメソッドの戻り値の型として使用します。</span><span class="sxs-lookup"><span data-stu-id="c17fa-114">You use it as the return type of a method that doesn't return a value.</span></span>

## <a name="see-also"></a><span data-ttu-id="c17fa-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="c17fa-115">See also</span></span>

- [<span data-ttu-id="c17fa-116">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="c17fa-116">C# reference</span></span>](../index.md)
- [<span data-ttu-id="c17fa-117">C# 型の既定値</span><span class="sxs-lookup"><span data-stu-id="c17fa-117">Default values of C# types</span></span>](default-values.md)
- [<span data-ttu-id="c17fa-118">`dynamic` キーワード</span><span class="sxs-lookup"><span data-stu-id="c17fa-118">`dynamic` keyword</span></span>](reference-types.md#the-dynamic-type)
