---
title: 組み込み型の一覧表 - C# リファレンス
ms.custom: seodec18
description: C# の組み込み型のキーワード
ms.date: 08/17/2018
helpviewer_keywords:
- types [C#], built-in
- built-in C# types
ms.assetid: 54f901f2-bf2f-472c-ae8d-73e8ecfc57fe
ms.openlocfilehash: bd8c52cd798496a4df3086411dfe3be6241fbff5
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/31/2019
ms.locfileid: "66422346"
---
# <a name="built-in-types-table-c-reference"></a><span data-ttu-id="749db-103">組み込み型の一覧表 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="749db-103">Built-in types table (C# Reference)</span></span>

<span data-ttu-id="749db-104">次の表は、C# の組み込み型のキーワードを示しています。これは、<xref:System> 名前空間の定義済み型の別名です。</span><span class="sxs-lookup"><span data-stu-id="749db-104">The following table shows the keywords for built-in C# types, which are aliases of predefined types in the <xref:System> namespace.</span></span>  
  
|<span data-ttu-id="749db-105">C# 型</span><span class="sxs-lookup"><span data-stu-id="749db-105">C# type</span></span>|<span data-ttu-id="749db-106">.NET 型</span><span class="sxs-lookup"><span data-stu-id="749db-106">.NET type</span></span>|  
|--------------|-------------------------|  
|[<span data-ttu-id="749db-107">bool</span><span class="sxs-lookup"><span data-stu-id="749db-107">bool</span></span>](bool.md)|<xref:System.Boolean?displayProperty=nameWithType>|  
|[<span data-ttu-id="749db-108">byte</span><span class="sxs-lookup"><span data-stu-id="749db-108">byte</span></span>](byte.md)|<xref:System.Byte?displayProperty=nameWithType>|  
|[<span data-ttu-id="749db-109">sbyte</span><span class="sxs-lookup"><span data-stu-id="749db-109">sbyte</span></span>](sbyte.md)|<xref:System.SByte?displayProperty=nameWithType>|  
|[<span data-ttu-id="749db-110">char</span><span class="sxs-lookup"><span data-stu-id="749db-110">char</span></span>](char.md)|<xref:System.Char?displayProperty=nameWithType>|  
|[<span data-ttu-id="749db-111">decimal</span><span class="sxs-lookup"><span data-stu-id="749db-111">decimal</span></span>](decimal.md)|<xref:System.Decimal?displayProperty=nameWithType>|  
|[<span data-ttu-id="749db-112">double</span><span class="sxs-lookup"><span data-stu-id="749db-112">double</span></span>](double.md)|<xref:System.Double?displayProperty=nameWithType>|  
|[<span data-ttu-id="749db-113">float</span><span class="sxs-lookup"><span data-stu-id="749db-113">float</span></span>](float.md)|<xref:System.Single?displayProperty=nameWithType>|  
|[<span data-ttu-id="749db-114">int</span><span class="sxs-lookup"><span data-stu-id="749db-114">int</span></span>](int.md)|<xref:System.Int32?displayProperty=nameWithType>|  
|[<span data-ttu-id="749db-115">uint</span><span class="sxs-lookup"><span data-stu-id="749db-115">uint</span></span>](uint.md)|<xref:System.UInt32?displayProperty=nameWithType>|  
|[<span data-ttu-id="749db-116">long</span><span class="sxs-lookup"><span data-stu-id="749db-116">long</span></span>](long.md)|<xref:System.Int64?displayProperty=nameWithType>|  
|[<span data-ttu-id="749db-117">ulong</span><span class="sxs-lookup"><span data-stu-id="749db-117">ulong</span></span>](ulong.md)|<xref:System.UInt64?displayProperty=nameWithType>|  
|[<span data-ttu-id="749db-118">object</span><span class="sxs-lookup"><span data-stu-id="749db-118">object</span></span>](object.md)|<xref:System.Object?displayProperty=nameWithType>|  
|[<span data-ttu-id="749db-119">short</span><span class="sxs-lookup"><span data-stu-id="749db-119">short</span></span>](short.md)|<xref:System.Int16?displayProperty=nameWithType>|  
|[<span data-ttu-id="749db-120">ushort</span><span class="sxs-lookup"><span data-stu-id="749db-120">ushort</span></span>](ushort.md)|<xref:System.UInt16?displayProperty=nameWithType>|  
|[<span data-ttu-id="749db-121">string</span><span class="sxs-lookup"><span data-stu-id="749db-121">string</span></span>](string.md)|<xref:System.String?displayProperty=nameWithType>|  
  
## <a name="remarks"></a><span data-ttu-id="749db-122">解説</span><span class="sxs-lookup"><span data-stu-id="749db-122">Remarks</span></span>

<span data-ttu-id="749db-123">表内の、`object` と `string` を除くすべての型が、単純型と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="749db-123">All of the types in the table, except `object` and `string`, are referred to as simple types.</span></span>  
  
<span data-ttu-id="749db-124">C# 型のキーワードと別名は相互に交換できます。</span><span class="sxs-lookup"><span data-stu-id="749db-124">The C# type keywords and their aliases are interchangeable.</span></span> <span data-ttu-id="749db-125">たとえば、整数の変数を宣言するには、次のいずれかの宣言を使用します。</span><span class="sxs-lookup"><span data-stu-id="749db-125">For example, you can declare an integer variable by using either of the following declarations:</span></span>  

```csharp
int x = 123;
System.Int32 y = 123;
```

<span data-ttu-id="749db-126">[typeof](typeof.md) 演算子を使用して、指定した型を表す <xref:System.Type?displayProperty=nameWithType> インスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="749db-126">Use the [typeof](typeof.md) operator to get the <xref:System.Type?displayProperty=nameWithType> instance that represents the specified type:</span></span>

```csharp
Type stringType = typeof(string);
Console.WriteLine(stringType.FullName);

Type doubleType = typeof(System.Double);
Console.WriteLine(doubleType.FullName);

// Output:
// System.String
// System.Double
```

## <a name="see-also"></a><span data-ttu-id="749db-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="749db-127">See also</span></span>

- [<span data-ttu-id="749db-128">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="749db-128">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="749db-129">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="749db-129">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="749db-130">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="749db-130">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="749db-131">値型</span><span class="sxs-lookup"><span data-stu-id="749db-131">Value types</span></span>](value-types.md)
- [<span data-ttu-id="749db-132">参照型</span><span class="sxs-lookup"><span data-stu-id="749db-132">Reference types</span></span>](reference-types.md)
- [<span data-ttu-id="749db-133">既定値の一覧表</span><span class="sxs-lookup"><span data-stu-id="749db-133">Default values table</span></span>](default-values-table.md)
- [<span data-ttu-id="749db-134">dynamic</span><span class="sxs-lookup"><span data-stu-id="749db-134">dynamic</span></span>](dynamic.md)
