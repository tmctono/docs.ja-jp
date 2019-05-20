---
title: sizeof - C# リファレンス
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- sizeof_CSharpKeyword
- sizeof
helpviewer_keywords:
- sizeof keyword [C#]
ms.assetid: c548592c-677c-4f40-a4ce-e613f7529141
ms.openlocfilehash: 8bb6d4a37b2eea3060921937cf15a1fdd1be97b4
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65634006"
---
# <a name="sizeof-c-reference"></a><span data-ttu-id="69e8a-102">sizeof (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="69e8a-102">sizeof (C# Reference)</span></span>

<span data-ttu-id="69e8a-103">アンマネージ型のサイズ (バイト単位) を取得するときに使用します。</span><span class="sxs-lookup"><span data-stu-id="69e8a-103">Used to obtain the size in bytes for an unmanaged type.</span></span>

<span data-ttu-id="69e8a-104">アンマネージド型には次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="69e8a-104">Unmanaged types include:</span></span>

- <span data-ttu-id="69e8a-105">次の表は単純型の一覧です。</span><span class="sxs-lookup"><span data-stu-id="69e8a-105">The simple types that are listed in the following table:</span></span>

   |<span data-ttu-id="69e8a-106">正規表現</span><span class="sxs-lookup"><span data-stu-id="69e8a-106">Expression</span></span>|<span data-ttu-id="69e8a-107">定数値</span><span class="sxs-lookup"><span data-stu-id="69e8a-107">Constant value</span></span>|
   |----------------|--------------------|
   |`sizeof(sbyte)`|<span data-ttu-id="69e8a-108">1</span><span class="sxs-lookup"><span data-stu-id="69e8a-108">1</span></span>|
   |`sizeof(byte)`|<span data-ttu-id="69e8a-109">1</span><span class="sxs-lookup"><span data-stu-id="69e8a-109">1</span></span>|
   |`sizeof(short)`|<span data-ttu-id="69e8a-110">2</span><span class="sxs-lookup"><span data-stu-id="69e8a-110">2</span></span>|
   |`sizeof(ushort)`|<span data-ttu-id="69e8a-111">2</span><span class="sxs-lookup"><span data-stu-id="69e8a-111">2</span></span>|
   |`sizeof(int)`|<span data-ttu-id="69e8a-112">4</span><span class="sxs-lookup"><span data-stu-id="69e8a-112">4</span></span>|
   |`sizeof(uint)`|<span data-ttu-id="69e8a-113">4</span><span class="sxs-lookup"><span data-stu-id="69e8a-113">4</span></span>|
   |`sizeof(long)`|<span data-ttu-id="69e8a-114">8</span><span class="sxs-lookup"><span data-stu-id="69e8a-114">8</span></span>|
   |`sizeof(ulong)`|<span data-ttu-id="69e8a-115">8</span><span class="sxs-lookup"><span data-stu-id="69e8a-115">8</span></span>|
   |`sizeof(char)`|<span data-ttu-id="69e8a-116">2 (Unicode)</span><span class="sxs-lookup"><span data-stu-id="69e8a-116">2 (Unicode)</span></span>|
   |`sizeof(float)`|<span data-ttu-id="69e8a-117">4</span><span class="sxs-lookup"><span data-stu-id="69e8a-117">4</span></span>|
   |`sizeof(double)`|<span data-ttu-id="69e8a-118">8</span><span class="sxs-lookup"><span data-stu-id="69e8a-118">8</span></span>|
   |`sizeof(decimal)`|<span data-ttu-id="69e8a-119">16</span><span class="sxs-lookup"><span data-stu-id="69e8a-119">16</span></span>|
   |`sizeof(bool)`|<span data-ttu-id="69e8a-120">1</span><span class="sxs-lookup"><span data-stu-id="69e8a-120">1</span></span>|

- <span data-ttu-id="69e8a-121">列挙型。</span><span class="sxs-lookup"><span data-stu-id="69e8a-121">Enum types.</span></span>

- <span data-ttu-id="69e8a-122">ポインター型。</span><span class="sxs-lookup"><span data-stu-id="69e8a-122">Pointer types.</span></span>

- <span data-ttu-id="69e8a-123">参照型または構築された型である任意のインスタンス フィールドまたは自動実装インスタンス プロパティが含まれていないユーザー定義の構造体。</span><span class="sxs-lookup"><span data-stu-id="69e8a-123">User-defined structs that do not contain any instance fields or auto-implemented instance properties that are reference types or constructed types.</span></span>

<span data-ttu-id="69e8a-124">次の例は、`int` のサイズを取得する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="69e8a-124">The following example shows how to retrieve the size of an `int`:</span></span>

```csharp
// Constant value 4:
int intSize = sizeof(int);
```

## <a name="remarks"></a><span data-ttu-id="69e8a-125">解説</span><span class="sxs-lookup"><span data-stu-id="69e8a-125">Remarks</span></span>

<span data-ttu-id="69e8a-126">C# のバージョン 2.0 以降、`sizeof` を単純型または列挙型に適用する場合、そのコードを [unsafe](unsafe.md) コンテキストでコンパイルする必要がなくなりました。</span><span class="sxs-lookup"><span data-stu-id="69e8a-126">Starting with version 2.0 of C#, applying `sizeof` to simple or enum types no longer requires that code be compiled in an [unsafe](unsafe.md) context.</span></span>

<span data-ttu-id="69e8a-127">`sizeof` 演算子はオーバーロードできません。</span><span class="sxs-lookup"><span data-stu-id="69e8a-127">The `sizeof` operator cannot be overloaded.</span></span> <span data-ttu-id="69e8a-128">`sizeof` 演算子により返される値の型は `int` です。</span><span class="sxs-lookup"><span data-stu-id="69e8a-128">The values returned by the `sizeof` operator are of type `int`.</span></span> <span data-ttu-id="69e8a-129">上記の表に、特定の単純型をオペランドとする `sizeof` 式と、代用される定数値を示します。</span><span class="sxs-lookup"><span data-stu-id="69e8a-129">The previous table shows the constant values that are substituted for `sizeof` expressions that have certain simple types as operands.</span></span>

<span data-ttu-id="69e8a-130">struct など、その他の型については、`sizeof` 演算子はアンセーフ コード ブロックでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="69e8a-130">For all other types, including structs, the `sizeof` operator can be used only in unsafe code blocks.</span></span> <span data-ttu-id="69e8a-131"><xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> メソッドを使用できますが、このメソッドによって返される値は常に `sizeof` によって返される値と同じとは限りません。</span><span class="sxs-lookup"><span data-stu-id="69e8a-131">Although you can use the <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> method, the value returned by this method is not always the same as the value returned by `sizeof`.</span></span> <span data-ttu-id="69e8a-132"><xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> は、型のマーシャリング後にサイズを返します。一方、`sizeof` は、共通言語ランタイムによって割り当てられたサイズ (埋め込みを含む) を返します。</span><span class="sxs-lookup"><span data-stu-id="69e8a-132"><xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> returns the size after the type has been marshaled, whereas `sizeof` returns the size as it has been allocated by the common language runtime, including any padding.</span></span>

## <a name="example"></a><span data-ttu-id="69e8a-133">例</span><span class="sxs-lookup"><span data-stu-id="69e8a-133">Example</span></span>

[!code-csharp[csrefKeywordsOperator#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#11)]

## <a name="c-language-specification"></a><span data-ttu-id="69e8a-134">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="69e8a-134">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="69e8a-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="69e8a-135">See also</span></span>

- [<span data-ttu-id="69e8a-136">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="69e8a-136">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="69e8a-137">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="69e8a-137">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="69e8a-138">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="69e8a-138">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="69e8a-139">演算子のキーワード</span><span class="sxs-lookup"><span data-stu-id="69e8a-139">Operator Keywords</span></span>](operator-keywords.md)
- [<span data-ttu-id="69e8a-140">enum</span><span class="sxs-lookup"><span data-stu-id="69e8a-140">enum</span></span>](enum.md)
- [<span data-ttu-id="69e8a-141">アンセーフ コードとポインター</span><span class="sxs-lookup"><span data-stu-id="69e8a-141">Unsafe Code and Pointers</span></span>](../../programming-guide/unsafe-code-pointers/index.md)
- [<span data-ttu-id="69e8a-142">構造体</span><span class="sxs-lookup"><span data-stu-id="69e8a-142">Structs</span></span>](../../programming-guide/classes-and-structs/structs.md)
- [<span data-ttu-id="69e8a-143">定数</span><span class="sxs-lookup"><span data-stu-id="69e8a-143">Constants</span></span>](../../programming-guide/classes-and-structs/constants.md)
