---
title: 既定値の一覧表 - C# リファレンス
ms.custom: seodec18
description: C# の値型における既定値について説明します。
ms.date: 08/23/2018
helpviewer_keywords:
- constructors [C#], return values
- keywords [C#], new
- parameterless constructor [C#]
- defaults [C#]
- value types [C#], initializing
- variables [C#], value types
- constructors [C#], parameterless constructor
- types [C#], parameterless constructor return values
ms.openlocfilehash: dfab5107d4a0ad14c3ffbfc6a5f3c4317b44d17c
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/28/2019
ms.locfileid: "67424231"
---
# <a name="default-values-table-c-reference"></a><span data-ttu-id="a2455-103">既定値の一覧表 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="a2455-103">Default values table (C# Reference)</span></span>

<span data-ttu-id="a2455-104">次の表では、[値型](value-types.md)の既定値を示します。</span><span class="sxs-lookup"><span data-stu-id="a2455-104">The following table shows the default values of [value types](value-types.md).</span></span>

|<span data-ttu-id="a2455-105">値の種類</span><span class="sxs-lookup"><span data-stu-id="a2455-105">Value type</span></span>|<span data-ttu-id="a2455-106">既定値</span><span class="sxs-lookup"><span data-stu-id="a2455-106">Default value</span></span>|
|----------------|-------------------|
|[<span data-ttu-id="a2455-107">bool</span><span class="sxs-lookup"><span data-stu-id="a2455-107">bool</span></span>](bool.md)|`false`|
|[<span data-ttu-id="a2455-108">byte</span><span class="sxs-lookup"><span data-stu-id="a2455-108">byte</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="a2455-109">0</span><span class="sxs-lookup"><span data-stu-id="a2455-109">0</span></span>|
|[<span data-ttu-id="a2455-110">char</span><span class="sxs-lookup"><span data-stu-id="a2455-110">char</span></span>](char.md)|<span data-ttu-id="a2455-111">'\0'</span><span class="sxs-lookup"><span data-stu-id="a2455-111">'\0'</span></span>|
|[<span data-ttu-id="a2455-112">decimal</span><span class="sxs-lookup"><span data-stu-id="a2455-112">decimal</span></span>](decimal.md)|<span data-ttu-id="a2455-113">0M</span><span class="sxs-lookup"><span data-stu-id="a2455-113">0M</span></span>|
|[<span data-ttu-id="a2455-114">double</span><span class="sxs-lookup"><span data-stu-id="a2455-114">double</span></span>](double.md)|<span data-ttu-id="a2455-115">0.0D</span><span class="sxs-lookup"><span data-stu-id="a2455-115">0.0D</span></span>|
|[<span data-ttu-id="a2455-116">enum</span><span class="sxs-lookup"><span data-stu-id="a2455-116">enum</span></span>](enum.md)|<span data-ttu-id="a2455-117">式 `(E)0` によって生成される値。`E` は列挙型識別子です。</span><span class="sxs-lookup"><span data-stu-id="a2455-117">The value produced by the expression `(E)0`, where `E` is the enum identifier.</span></span>|
|[<span data-ttu-id="a2455-118">float</span><span class="sxs-lookup"><span data-stu-id="a2455-118">float</span></span>](float.md)|<span data-ttu-id="a2455-119">0.0F</span><span class="sxs-lookup"><span data-stu-id="a2455-119">0.0F</span></span>|
|[<span data-ttu-id="a2455-120">int</span><span class="sxs-lookup"><span data-stu-id="a2455-120">int</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="a2455-121">0</span><span class="sxs-lookup"><span data-stu-id="a2455-121">0</span></span>|
|[<span data-ttu-id="a2455-122">long</span><span class="sxs-lookup"><span data-stu-id="a2455-122">long</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="a2455-123">0L</span><span class="sxs-lookup"><span data-stu-id="a2455-123">0L</span></span>|
|[<span data-ttu-id="a2455-124">sbyte</span><span class="sxs-lookup"><span data-stu-id="a2455-124">sbyte</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="a2455-125">0</span><span class="sxs-lookup"><span data-stu-id="a2455-125">0</span></span>|
|[<span data-ttu-id="a2455-126">short</span><span class="sxs-lookup"><span data-stu-id="a2455-126">short</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="a2455-127">0</span><span class="sxs-lookup"><span data-stu-id="a2455-127">0</span></span>|
|[<span data-ttu-id="a2455-128">struct</span><span class="sxs-lookup"><span data-stu-id="a2455-128">struct</span></span>](struct.md)|<span data-ttu-id="a2455-129">すべての値型フィールドが既定値に設定され、すべての参照型フィールドが `null` に設定された値。</span><span class="sxs-lookup"><span data-stu-id="a2455-129">The value produced by setting all value-type fields to their default values and all reference-type fields to `null`.</span></span>|
|[<span data-ttu-id="a2455-130">uint</span><span class="sxs-lookup"><span data-stu-id="a2455-130">uint</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="a2455-131">0</span><span class="sxs-lookup"><span data-stu-id="a2455-131">0</span></span>|
|[<span data-ttu-id="a2455-132">ulong</span><span class="sxs-lookup"><span data-stu-id="a2455-132">ulong</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="a2455-133">0</span><span class="sxs-lookup"><span data-stu-id="a2455-133">0</span></span>|
|[<span data-ttu-id="a2455-134">ushort</span><span class="sxs-lookup"><span data-stu-id="a2455-134">ushort</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="a2455-135">0</span><span class="sxs-lookup"><span data-stu-id="a2455-135">0</span></span>|

## <a name="remarks"></a><span data-ttu-id="a2455-136">解説</span><span class="sxs-lookup"><span data-stu-id="a2455-136">Remarks</span></span>

<span data-ttu-id="a2455-137">C# で初期化されていない変数を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="a2455-137">You cannot use uninitialized variables in C#.</span></span> <span data-ttu-id="a2455-138">変数はその型の既定値に初期化することができます。</span><span class="sxs-lookup"><span data-stu-id="a2455-138">You can initialize a variable with the default value of its type.</span></span> <span data-ttu-id="a2455-139">また、型の既定値を使用して、メソッドの[省略可能な引数](../../programming-guide/classes-and-structs/named-and-optional-arguments.md#optional-arguments)の既定値を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="a2455-139">You also can use the default value of a type to specify the default value of a method's [optional argument](../../programming-guide/classes-and-structs/named-and-optional-arguments.md#optional-arguments).</span></span>

<span data-ttu-id="a2455-140">[既定の値式](../../programming-guide/statements-expressions-operators/default-value-expressions.md)を使用して、次の例に示すように、型の既定値を生成します。</span><span class="sxs-lookup"><span data-stu-id="a2455-140">Use the [default value expression](../../programming-guide/statements-expressions-operators/default-value-expressions.md) to produce the default value of a type, as the following example shows:</span></span>

```csharp
int a = default(int);
```

<span data-ttu-id="a2455-141">C# 7.1 以降、[`default` リテラル](../../programming-guide/statements-expressions-operators/default-value-expressions.md#default-literal-and-type-inference)を使用して、その型の既定値に変数を初期化できます。</span><span class="sxs-lookup"><span data-stu-id="a2455-141">Beginning with C# 7.1, you can use the [`default` literal](../../programming-guide/statements-expressions-operators/default-value-expressions.md#default-literal-and-type-inference) to initialize a variable with the default value of its type:</span></span>

```csharp
int a = default;
```

<span data-ttu-id="a2455-142">また、次の例に示すように、パラメーターなしのコンストラクターまたは暗黙的なパラメーターなしのコンストラクターを使用して、値型の既定値を生成することもできます。</span><span class="sxs-lookup"><span data-stu-id="a2455-142">You also can use the parameterless constructor or the implicit parameterless constructor to produce the default value of a value type, as the following example shows.</span></span> <span data-ttu-id="a2455-143">コンストラクターの詳細については、[コンストラクター](../../programming-guide/classes-and-structs/constructors.md)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2455-143">For more information about constructors, see the [Constructors](../../programming-guide/classes-and-structs/constructors.md) article.</span></span>

```csharp
int a = new int();
```

<span data-ttu-id="a2455-144">[参照型](reference-types.md)の既定値は `null` です。</span><span class="sxs-lookup"><span data-stu-id="a2455-144">The default value of any [reference type](reference-types.md) is `null`.</span></span> <span data-ttu-id="a2455-145">[null 許容型](../../programming-guide/nullable-types/index.md)の既定値は、<xref:System.Nullable%601.HasValue%2A> プロパティが `false` で、<xref:System.Nullable%601.Value%2A> プロパティが未定義のインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="a2455-145">The default value of a [nullable type](../../programming-guide/nullable-types/index.md) is an instance for which the <xref:System.Nullable%601.HasValue%2A> property is `false` and the <xref:System.Nullable%601.Value%2A> property is undefined.</span></span>

## <a name="see-also"></a><span data-ttu-id="a2455-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="a2455-146">See also</span></span>

- [<span data-ttu-id="a2455-147">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="a2455-147">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="a2455-148">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="a2455-148">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="a2455-149">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="a2455-149">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="a2455-150">値型</span><span class="sxs-lookup"><span data-stu-id="a2455-150">Value types</span></span>](value-types.md)
- [<span data-ttu-id="a2455-151">値型の一覧表</span><span class="sxs-lookup"><span data-stu-id="a2455-151">Value types table</span></span>](value-types-table.md)
- [<span data-ttu-id="a2455-152">組み込み型の一覧表</span><span class="sxs-lookup"><span data-stu-id="a2455-152">Built-in types table</span></span>](built-in-types-table.md)
