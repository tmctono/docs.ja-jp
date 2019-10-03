---
title: 値型 - C# リファレンス
ms.custom: seodec18
ms.date: 11/26/2018
f1_keywords:
- cs.valuetypes
helpviewer_keywords:
- value types [C#]
- types [C#], value types
- C# language, value types
ms.assetid: 471eb994-2958-49d5-a6be-19b4313f80a3
ms.openlocfilehash: 2a3e7f02ee9d210acae881edd170edbced82dab6
ms.sourcegitcommit: da2dd2772fcf32b44eb18b1cbe8affd17b1753c9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2019
ms.locfileid: "71353751"
---
# <a name="value-types-c-reference"></a><span data-ttu-id="67693-102">値型 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="67693-102">Value types (C# Reference)</span></span>

<span data-ttu-id="67693-103">2 種類の値型があります。</span><span class="sxs-lookup"><span data-stu-id="67693-103">There are two kinds of value types:</span></span>

- [<span data-ttu-id="67693-104">構造体</span><span class="sxs-lookup"><span data-stu-id="67693-104">Structs</span></span>](struct.md)

- [<span data-ttu-id="67693-105">列挙型</span><span class="sxs-lookup"><span data-stu-id="67693-105">Enumerations</span></span>](enum.md)

## <a name="main-features-of-value-types"></a><span data-ttu-id="67693-106">値型の主な機能</span><span class="sxs-lookup"><span data-stu-id="67693-106">Main features of value types</span></span>

<span data-ttu-id="67693-107">値型の変数には、その型の値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="67693-107">A variable of a value type contains a value of the type.</span></span> <span data-ttu-id="67693-108">たとえば、`int` 型の変数には値 `42` が含まれている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="67693-108">For example, a variable of the `int` type might contain the value `42`.</span></span> <span data-ttu-id="67693-109">これは、オブジェクトとも呼ばれる型のインスタンスへの参照を含む参照型の変数とは異なります。</span><span class="sxs-lookup"><span data-stu-id="67693-109">This differs from a variable of a reference type, which contains a reference to an instance of the type, also known as an object.</span></span> <span data-ttu-id="67693-110">値型の変数に新しい値を割り当てると、その値はコピーされます。</span><span class="sxs-lookup"><span data-stu-id="67693-110">When you assign a new value to a variable of a value type, that value is copied.</span></span> <span data-ttu-id="67693-111">参照型の変数に新しい値を割り当てると、オブジェクト自体ではなく参照がコピーされます。</span><span class="sxs-lookup"><span data-stu-id="67693-111">When you assign a new value to a variable of a reference type, the reference is copied, not the object itself.</span></span>

<span data-ttu-id="67693-112">すべての値型が <xref:System.ValueType?displayProperty=nameWithType> から暗黙的に派生されます。</span><span class="sxs-lookup"><span data-stu-id="67693-112">All value types are derived implicitly from the <xref:System.ValueType?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="67693-113">参照型とは異なり、値型から新しい型を派生することはできません。</span><span class="sxs-lookup"><span data-stu-id="67693-113">Unlike with reference types, you cannot derive a new type from a value type.</span></span> <span data-ttu-id="67693-114">ただし、参照型の場合と同様に、構造体はインターフェイスを実装できます。</span><span class="sxs-lookup"><span data-stu-id="67693-114">However, like reference types, structs can implement interfaces.</span></span>

<span data-ttu-id="67693-115">値型の変数は既定で `null` にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="67693-115">Value type variables cannot be `null` by default.</span></span> <span data-ttu-id="67693-116">ただし、対応する [null 許容値型](../../programming-guide/nullable-types/index.md)の変数を `null` にすることはできます。</span><span class="sxs-lookup"><span data-stu-id="67693-116">However, variables of the corresponding [nullable value types](../../programming-guide/nullable-types/index.md) can be `null`.</span></span>

<span data-ttu-id="67693-117">各値型には、その型の既定値を初期化する暗黙のパラメーターなしのコンストラクターがあります。</span><span class="sxs-lookup"><span data-stu-id="67693-117">Each value type has an implicit parameterless constructor that initializes the default value of that type.</span></span> <span data-ttu-id="67693-118">値型の既定値の詳細については、「[既定値の一覧表](default-values-table.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="67693-118">For information about default values of value types, see [Default values table](default-values-table.md).</span></span>

## <a name="simple-types"></a><span data-ttu-id="67693-119">単純型</span><span class="sxs-lookup"><span data-stu-id="67693-119">Simple types</span></span>

<span data-ttu-id="67693-120">*単純型*は、C# に用意されている定義済みの構造体型のセットであり、次の型を構成します。</span><span class="sxs-lookup"><span data-stu-id="67693-120">The *simple types* are a set of predefined struct types provided by C# and comprise the following types:</span></span>

- <span data-ttu-id="67693-121">[整数型](../builtin-types/integral-numeric-types.md): 整数の数値型と [char](char.md) 型</span><span class="sxs-lookup"><span data-stu-id="67693-121">[Integral types](../builtin-types/integral-numeric-types.md): integer numeric types and the [char](char.md) type</span></span>
- [<span data-ttu-id="67693-122">浮動小数点型</span><span class="sxs-lookup"><span data-stu-id="67693-122">Floating-point types</span></span>](../builtin-types/floating-point-numeric-types.md)
- [<span data-ttu-id="67693-123">bool</span><span class="sxs-lookup"><span data-stu-id="67693-123">bool</span></span>](bool.md)

<span data-ttu-id="67693-124">単純型はキーワードで識別されますが、これらのキーワードは、<xref:System> 名前空間に事前に定義されている構造体型の単なるエイリアスです。</span><span class="sxs-lookup"><span data-stu-id="67693-124">The simple types are identified through keywords, but these keywords are simply aliases for predefined struct types in the <xref:System> namespace.</span></span> <span data-ttu-id="67693-125">たとえば、[int](../builtin-types/integral-numeric-types.md) は <xref:System.Int32?displayProperty=nameWithType> のエイリアスです。</span><span class="sxs-lookup"><span data-stu-id="67693-125">For example, [int](../builtin-types/integral-numeric-types.md) is an alias of <xref:System.Int32?displayProperty=nameWithType>.</span></span> <span data-ttu-id="67693-126">エイリアスの完全な一覧については、「[組み込み型の一覧表](built-in-types-table.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="67693-126">For a complete list of aliases, see [Built-in types table](built-in-types-table.md).</span></span>

<span data-ttu-id="67693-127">単純型は、ある追加の操作を許可している点で、他の構造体型とは異なります。</span><span class="sxs-lookup"><span data-stu-id="67693-127">The simple types differ from other struct types in that they permit certain additional operations:</span></span>

- <span data-ttu-id="67693-128">単純型はリテラルを使用して初期化できます。</span><span class="sxs-lookup"><span data-stu-id="67693-128">Simple types can be initialized by using literals.</span></span> <span data-ttu-id="67693-129">たとえば、`'A'` は `char` 型のリテラルで、`2001` は `int` 型のリテラルです。</span><span class="sxs-lookup"><span data-stu-id="67693-129">For example, `'A'` is a literal of the type `char` and `2001` is a literal of the type `int`.</span></span>

- <span data-ttu-id="67693-130">単純型の定数は、[const](const.md) キーワードを使用して宣言できます。</span><span class="sxs-lookup"><span data-stu-id="67693-130">You can declare constants of the simple types with the [const](const.md) keyword.</span></span> <span data-ttu-id="67693-131">他の構造体型の定数を持つことはできません。</span><span class="sxs-lookup"><span data-stu-id="67693-131">It's not possible to have constants of other struct types.</span></span>

- <span data-ttu-id="67693-132">オペランドがすべて単純型の定数式は、コンパイル時に評価されます。</span><span class="sxs-lookup"><span data-stu-id="67693-132">Constant expressions, whose operands are all simple type constants, are evaluated at compile time.</span></span>

<span data-ttu-id="67693-133">詳細については、「[C# 言語仕様](../language-specification/index.md)」の[単純型](~/_csharplang/spec/types.md#simple-types)に関するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="67693-133">For more information, see the [Simple types](~/_csharplang/spec/types.md#simple-types) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="initializing-value-types"></a><span data-ttu-id="67693-134">値型の初期化</span><span class="sxs-lookup"><span data-stu-id="67693-134">Initializing value types</span></span>

<span data-ttu-id="67693-135">C# では、ローカル変数を使用する前に初期化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="67693-135">Local variables in C# must be initialized before they are used.</span></span> <span data-ttu-id="67693-136">たとえば、次の例のように、初期化せずにローカル変数を宣言した場合、</span><span class="sxs-lookup"><span data-stu-id="67693-136">For example, you might declare a local variable without initialization as in the following example:</span></span>

```csharp
int myInt;
```

<span data-ttu-id="67693-137">初期化してからでないとこれを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="67693-137">You cannot use it before you initialize it.</span></span> <span data-ttu-id="67693-138">次のステートメントを使用して初期化できます。</span><span class="sxs-lookup"><span data-stu-id="67693-138">You can initialize it using the following statement:</span></span>

```csharp
myInt = new int();  // Invoke parameterless constructor for int type.
```

<span data-ttu-id="67693-139">このステートメントは、次のステートメントと同じです。</span><span class="sxs-lookup"><span data-stu-id="67693-139">This statement is equivalent to the following statement:</span></span>

```csharp
myInt = 0;         // Assign an initial value, 0 in this example.
```

<span data-ttu-id="67693-140">もちろん、次の例のように、宣言と初期化を同じステートメントに含めることができます。</span><span class="sxs-lookup"><span data-stu-id="67693-140">You can, of course, have the declaration and the initialization in the same statement as in the following examples:</span></span>

```csharp
int myInt = new int();
```

<span data-ttu-id="67693-141">または</span><span class="sxs-lookup"><span data-stu-id="67693-141">–or–</span></span>

```csharp
int myInt = 0;
```

<span data-ttu-id="67693-142">[new](../operators/new-operator.md) 演算子を使用すると、特定の型のパラメーターなしのコンストラクターを呼び出し、既定値を変数に代入します。</span><span class="sxs-lookup"><span data-stu-id="67693-142">Using the [new](../operators/new-operator.md) operator calls the parameterless constructor of the specific type and assigns the default value to the variable.</span></span> <span data-ttu-id="67693-143">前の例では、パラメーターなしのコンス トラクターで値 `0` を `myInt` に代入していました。</span><span class="sxs-lookup"><span data-stu-id="67693-143">In the preceding example, the parameterless constructor assigned the value `0` to `myInt`.</span></span> <span data-ttu-id="67693-144">パラメーターなしのコンストラクターの呼び出しによって代入される値の詳細については、「[既定値の一覧表](default-values-table.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="67693-144">For more information about values assigned by calling parameterless constructors, see [Default values table](default-values-table.md).</span></span>

<span data-ttu-id="67693-145">ユーザー定義型では、[new](../operators/new-operator.md) を使用してパラメーターなしのコンストラクターを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="67693-145">With user-defined types, use [new](../operators/new-operator.md) to invoke the parameterless constructor.</span></span> <span data-ttu-id="67693-146">たとえば、次のステートメントは、`Point` 構造体のパラメーターなしのコンストラクターを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="67693-146">For example, the following statement invokes the parameterless constructor of the `Point` struct:</span></span>

```csharp
var p = new Point(); // Invoke parameterless constructor for the struct.
```

<span data-ttu-id="67693-147">この呼び出しの後、構造体は明示的に代入されると見なされます。つまり、すべてのメンバーがその既定値に初期化されます。</span><span class="sxs-lookup"><span data-stu-id="67693-147">After this call, the struct is considered to be definitely assigned; that is, all its members are initialized to their default values.</span></span>

<span data-ttu-id="67693-148">`new` 演算子の詳細については、「[new](../operators/new-operator.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="67693-148">For more information about the `new` operator, see [new](../operators/new-operator.md).</span></span>

<span data-ttu-id="67693-149">数値型の出力の書式設定については、「[数値結果テーブルの書式設定](formatting-numeric-results-table.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="67693-149">For information about formatting the output of numeric types, see [Formatting numeric results table](formatting-numeric-results-table.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="67693-150">関連項目</span><span class="sxs-lookup"><span data-stu-id="67693-150">See also</span></span>

- [<span data-ttu-id="67693-151">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="67693-151">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="67693-152">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="67693-152">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="67693-153">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="67693-153">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="67693-154">型</span><span class="sxs-lookup"><span data-stu-id="67693-154">Types</span></span>](types.md)
- [<span data-ttu-id="67693-155">参照型</span><span class="sxs-lookup"><span data-stu-id="67693-155">Reference types</span></span>](reference-types.md)
- [<span data-ttu-id="67693-156">null 許容値型</span><span class="sxs-lookup"><span data-stu-id="67693-156">Nullable value types</span></span>](../../programming-guide/nullable-types/index.md)
