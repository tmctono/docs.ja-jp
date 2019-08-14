---
title: 既定値の一覧表 - C# リファレンス
ms.custom: seodec18
description: C# の型における既定値について説明します。
ms.date: 07/29/2019
helpviewer_keywords:
- default [C#]
- parameterless constructor [C#]
ms.openlocfilehash: d9889ce389eed73a9af0a3f72dcca6ec476cae15
ms.sourcegitcommit: bbfcc913c275885381820be28f61efcf8e83eecc
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2019
ms.locfileid: "68796500"
---
# <a name="default-values-table-c-reference"></a><span data-ttu-id="0c5dd-103">既定値の一覧表 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="0c5dd-103">Default values table (C# reference)</span></span>

<span data-ttu-id="0c5dd-104">次の表では、C# の型の既定値を示します。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-104">The following table shows the default values of C# types:</span></span>

|<span data-ttu-id="0c5dd-105">型</span><span class="sxs-lookup"><span data-stu-id="0c5dd-105">Type</span></span>|<span data-ttu-id="0c5dd-106">既定値</span><span class="sxs-lookup"><span data-stu-id="0c5dd-106">Default value</span></span>|
|---------|------------------|
|<span data-ttu-id="0c5dd-107">すべての参照型</span><span class="sxs-lookup"><span data-stu-id="0c5dd-107">Any reference type</span></span>|`null`|
|<span data-ttu-id="0c5dd-108">任意の[組み込み整数数値型](../builtin-types/integral-numeric-types.md)</span><span class="sxs-lookup"><span data-stu-id="0c5dd-108">Any [built-in integral numeric type](../builtin-types/integral-numeric-types.md)</span></span>|<span data-ttu-id="0c5dd-109">0 (ゼロ)</span><span class="sxs-lookup"><span data-stu-id="0c5dd-109">0 (zero)</span></span>|
|<span data-ttu-id="0c5dd-110">任意の[組み込み浮動小数点数値型](../builtin-types/floating-point-numeric-types.md)</span><span class="sxs-lookup"><span data-stu-id="0c5dd-110">Any [built-in floating-point numeric type](../builtin-types/floating-point-numeric-types.md)</span></span>|<span data-ttu-id="0c5dd-111">0 (ゼロ)</span><span class="sxs-lookup"><span data-stu-id="0c5dd-111">0 (zero)</span></span>|
|[<span data-ttu-id="0c5dd-112">bool</span><span class="sxs-lookup"><span data-stu-id="0c5dd-112">bool</span></span>](bool.md)|`false`|
|[<span data-ttu-id="0c5dd-113">char</span><span class="sxs-lookup"><span data-stu-id="0c5dd-113">char</span></span>](char.md)|<span data-ttu-id="0c5dd-114">`'\0'` (U+0000)</span><span class="sxs-lookup"><span data-stu-id="0c5dd-114">`'\0'` (U+0000)</span></span>|
|[<span data-ttu-id="0c5dd-115">enum</span><span class="sxs-lookup"><span data-stu-id="0c5dd-115">enum</span></span>](enum.md)|<span data-ttu-id="0c5dd-116">式 `(E)0` によって生成される値。`E` は列挙型識別子です。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-116">The value produced by the expression `(E)0`, where `E` is the enum identifier.</span></span>|
|[<span data-ttu-id="0c5dd-117">struct</span><span class="sxs-lookup"><span data-stu-id="0c5dd-117">struct</span></span>](struct.md)|<span data-ttu-id="0c5dd-118">すべての値型フィールドが既定値に設定され、すべての参照型フィールドが `null` に設定された値。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-118">The value produced by setting all value-type fields to their default values and all reference-type fields to `null`.</span></span>|
|<span data-ttu-id="0c5dd-119">任意の [null 許容値型](../../programming-guide/nullable-types/index.md)</span><span class="sxs-lookup"><span data-stu-id="0c5dd-119">Any [nullable value type](../../programming-guide/nullable-types/index.md)</span></span>|<span data-ttu-id="0c5dd-120"><xref:System.Nullable%601.HasValue%2A> プロパティが `false` で、<xref:System.Nullable%601.Value%2A> プロパティが未定義のインスタンス。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-120">An instance for which the <xref:System.Nullable%601.HasValue%2A> property is `false` and the <xref:System.Nullable%601.Value%2A> property is undefined.</span></span> <span data-ttu-id="0c5dd-121">その規定値は、null 許容値型の "*null*" 値とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-121">That default value is also known as the *null* value of the nullable value type.</span></span>|

<span data-ttu-id="0c5dd-122">次の例に示すように、型の既定値を生成するには [default 演算子](../operators/default.md)を使います。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-122">Use the [default operator](../operators/default.md) to produce the default value of a type, as the following example shows:</span></span>

```csharp
int a = default(int);
```

<span data-ttu-id="0c5dd-123">C# 7.1 以降、[`default` リテラル](../operators/default.md#default-literal)を使用して、その型の既定値に変数を初期化できます。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-123">Beginning with C# 7.1, you can use the [`default` literal](../operators/default.md#default-literal) to initialize a variable with the default value of its type:</span></span>

```csharp
int a = default;
```

<span data-ttu-id="0c5dd-124">値の型については、次の例が示すように、暗黙的なパラメーターなしのコンストラクターによっても、型の既定値が生成されます。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-124">For a value type, the implicit parameterless constructor also produces the default value of the type, as the following example shows:</span></span>

```csharp-interactive
var n = new System.Numerics.Complex();
Console.WriteLine(n);  // output: (0, 0)
```

## <a name="c-language-specification"></a><span data-ttu-id="0c5dd-125">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="0c5dd-125">C# language specification</span></span>

<span data-ttu-id="0c5dd-126">詳細については、「[C# 言語仕様](~/_csharplang/spec/introduction.md)」の次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-126">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="0c5dd-127">既定値</span><span class="sxs-lookup"><span data-stu-id="0c5dd-127">Default values</span></span>](~/_csharplang/spec/variables.md#default-values)
- [<span data-ttu-id="0c5dd-128">既定のコンストラクター</span><span class="sxs-lookup"><span data-stu-id="0c5dd-128">Default constructors</span></span>](~/_csharplang/spec/types.md#default-constructors)

## <a name="see-also"></a><span data-ttu-id="0c5dd-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="0c5dd-129">See also</span></span>

- [<span data-ttu-id="0c5dd-130">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="0c5dd-130">C# reference</span></span>](../index.md)
- [<span data-ttu-id="0c5dd-131">C# キーワード</span><span class="sxs-lookup"><span data-stu-id="0c5dd-131">C# keywords</span></span>](index.md)
- [<span data-ttu-id="0c5dd-132">組み込み型の一覧表</span><span class="sxs-lookup"><span data-stu-id="0c5dd-132">Built-in types table</span></span>](built-in-types-table.md)
- [<span data-ttu-id="0c5dd-133">コンストラクター</span><span class="sxs-lookup"><span data-stu-id="0c5dd-133">Constructors</span></span>](../../programming-guide/classes-and-structs/constructors.md)
