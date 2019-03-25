---
title: C# 7.2 の新機能
description: C# 7.2 の新機能の概要。
ms.date: 08/16/2017
ms.openlocfilehash: b8b2be68aac3cba92e0dbd74dfe4ee3cbbef0e88
ms.sourcegitcommit: 462dc41a13942e467984e48f4018d1f79ae67346
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58185351"
---
# <a name="whats-new-in-c-72"></a><span data-ttu-id="63849-103">C# 7.2 の新機能</span><span class="sxs-lookup"><span data-stu-id="63849-103">What's new in C# 7.2</span></span>

<span data-ttu-id="63849-104">C# 7.2 は、便利な機能が多数追加された、もう 1 つのポイント リリースです。</span><span class="sxs-lookup"><span data-stu-id="63849-104">C# 7.2 is another point release that adds a number of useful features.</span></span>
<span data-ttu-id="63849-105">このリリースのテーマの 1 つは、不要なコピーや割り当てを回避して、さまざまな値の型の操作をより効率的に行うことです。</span><span class="sxs-lookup"><span data-stu-id="63849-105">One theme for this release is working more efficiently with value types by avoiding unnecessary copies or allocations.</span></span>

<span data-ttu-id="63849-106">他の機能も、小さくても、あると助かる機能です。</span><span class="sxs-lookup"><span data-stu-id="63849-106">The remaining features are small, nice-to-have features.</span></span>

<span data-ttu-id="63849-107">C# 7.2 では[言語バージョンの選択](../language-reference/configure-language-version.md)の構成要素を使用して、コンパイラ言語バージョンを選択します。</span><span class="sxs-lookup"><span data-stu-id="63849-107">C# 7.2 uses the [language version selection](../language-reference/configure-language-version.md) configuration element to select the compiler language version.</span></span>

<span data-ttu-id="63849-108">このリリースの新しい言語機能は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="63849-108">The new language features in this release are:</span></span>

* [<span data-ttu-id="63849-109">安全で効率的なコードを記述するための手法</span><span class="sxs-lookup"><span data-stu-id="63849-109">Techniques for writing safe efficient code</span></span>](#safe-efficient-code-enhancements)
  - <span data-ttu-id="63849-110">参照セマンティクスを使用したさまざまな値の型の使用を有効にする、構文の機能強化の組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="63849-110">A combination of syntax improvements that enable working with value types using reference semantics.</span></span>
* [<span data-ttu-id="63849-111">末尾以外の名前付き引数</span><span class="sxs-lookup"><span data-stu-id="63849-111">Non-trailing named arguments</span></span>](#non-trailing-named-arguments)
  - <span data-ttu-id="63849-112">名前付き引数の後ろに位置引数を続けることができます。</span><span class="sxs-lookup"><span data-stu-id="63849-112">Named arguments can be followed by positional arguments.</span></span>
* [<span data-ttu-id="63849-113">数値リテラルでの先頭のアンダースコア (_)</span><span class="sxs-lookup"><span data-stu-id="63849-113">Leading underscores in numeric literals</span></span>](#leading-underscores-in-numeric-literals)
  - <span data-ttu-id="63849-114">数値リテラルの印刷桁の前に先頭のアンダースコア(_) を含めることができるようになりました。</span><span class="sxs-lookup"><span data-stu-id="63849-114">Numeric literals can now have leading underscores before any printed digits.</span></span>
* [<span data-ttu-id="63849-115">`private protected` アクセス修飾子</span><span class="sxs-lookup"><span data-stu-id="63849-115">`private protected` access modifier</span></span>](#private-protected-access-modifier)
  - <span data-ttu-id="63849-116">`private protected` アクセス修飾子によって、同じアセンブリ内の派生クラスのアクセスが有効になります。</span><span class="sxs-lookup"><span data-stu-id="63849-116">The `private protected` access modifier enables access for derived classes in the same assembly.</span></span>
* [<span data-ttu-id="63849-117">条件付きの `ref` 式</span><span class="sxs-lookup"><span data-stu-id="63849-117">Conditional `ref` expressions</span></span>](#conditional-ref-expressions)
  - <span data-ttu-id="63849-118">条件式 (`?:`) の結果を参照にすることができるようになりました。</span><span class="sxs-lookup"><span data-stu-id="63849-118">The result of a conditional expression (`?:`) can now be a reference.</span></span>

## <a name="safe-efficient-code-enhancements"></a><span data-ttu-id="63849-119">安全で効率的なコードの機能拡張</span><span class="sxs-lookup"><span data-stu-id="63849-119">Safe efficient code enhancements</span></span>

<span data-ttu-id="63849-120">7.2 で導入された言語機能では、参照セマンティクスを使用しているときに、さまざまな値の型を使用できます。</span><span class="sxs-lookup"><span data-stu-id="63849-120">Language features introduced in 7.2 let you work with value types while using reference semantics.</span></span> <span data-ttu-id="63849-121">これらは、参照型の使用に関連するメモリの割り当てを生じさせずに、値の型のコピーを最小限に抑えてパフォーマンスを改善するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="63849-121">They are designed to increase performance by minimizing copying value types without incurring the memory allocations associated with using reference types.</span></span> <span data-ttu-id="63849-122">次のような機能があります。</span><span class="sxs-lookup"><span data-stu-id="63849-122">The features include:</span></span>

- <span data-ttu-id="63849-123">パラメーターの `in` 修飾子。引数が参照によって渡されるが、呼び出されたメソッドでは変更されないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="63849-123">The `in` modifier on parameters, to specify that an argument is passed by reference but not modified by the called method.</span></span> <span data-ttu-id="63849-124">引数に `in` 修飾子を加えることは、[ソース互換性がある変更](version-update-considerations.md#source-compatible-changes)です。</span><span class="sxs-lookup"><span data-stu-id="63849-124">Adding the `in` modifier to an argument is a [source compatible change](version-update-considerations.md#source-compatible-changes).</span></span>
- <span data-ttu-id="63849-125">メソッド戻りの `ref readonly` 修飾子。メソッドが参照によってその値を戻しますが、そのオブジェクトに対する書き込みを許可しないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="63849-125">The `ref readonly` modifier on method returns, to indicate that a method returns its value by reference but doesn't allow writes to that object.</span></span> <span data-ttu-id="63849-126">戻り値が値に割り当てられている場合、`ref readonly` 修飾子を追加することは、[ソース互換性がある変更](version-update-considerations.md#source-compatible-changes)です。</span><span class="sxs-lookup"><span data-stu-id="63849-126">Adding the `ref readonly` modifier is a [source compatible change](version-update-considerations.md#source-compatible-changes), if the return is assigned to a value.</span></span> <span data-ttu-id="63849-127">既存の `ref` return ステートメントに `readonly` 修飾子を追加することは、[互換性がない変更](version-update-considerations.md#incompatible-changes)です。</span><span class="sxs-lookup"><span data-stu-id="63849-127">Adding the `readonly` modifier to an existing `ref` return statement is an [incompatible change](version-update-considerations.md#incompatible-changes).</span></span> <span data-ttu-id="63849-128">呼び出し元は、`readonly` 修飾子を含むように `ref` ローカル変数の宣言を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="63849-128">It requires callers to update the declaration of `ref` local variables to include the `readonly` modifier.</span></span>
- <span data-ttu-id="63849-129">`readonly struct` 宣言。変更不可の構造体で、そのメンバー メソッドの `in` パラメーターとして渡す必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="63849-129">The `readonly struct` declaration, to indicate that a struct is immutable and should be passed as an `in` parameter to its member methods.</span></span> <span data-ttu-id="63849-130">既存の構造体の宣言に `readonly` 修飾子を追加することは、[バイナリ互換性がある変更](version-update-considerations.md#binary-compatible-changes)です。</span><span class="sxs-lookup"><span data-stu-id="63849-130">Adding the `readonly` modifier to an existing struct declaration is a [binary compatible change](version-update-considerations.md#binary-compatible-changes).</span></span>
- <span data-ttu-id="63849-131">`ref struct` 宣言。構造体型がマネージド メモリに直接アクセスし、常にスタック割り当てが必要であることを示します。</span><span class="sxs-lookup"><span data-stu-id="63849-131">The `ref struct` declaration, to indicate that a struct type accesses managed memory directly and must always be stack allocated.</span></span> <span data-ttu-id="63849-132">既存の `struct` の宣言に `ref` 修飾子を追加することは、[互換性がない変更](version-update-considerations.md#incompatible-changes)です。</span><span class="sxs-lookup"><span data-stu-id="63849-132">Adding the `ref` modifier to an existing `struct` declaration is an [incompatible change](version-update-considerations.md#incompatible-changes).</span></span> <span data-ttu-id="63849-133">`ref struct` をクラスのメンバーにすることはできません。また、ヒープ上に割り当てられている可能性がある他の場所で使用することもできません。</span><span class="sxs-lookup"><span data-stu-id="63849-133">A `ref struct` cannot be a member of a class or used in other locations where it may be allocated on the heap.</span></span>

<span data-ttu-id="63849-134">これらすべての変更点の詳細については、[安全で効率的なコードを記述する方法](../write-safe-efficient-code.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="63849-134">You can read more about all these changes in [Write safe efficient code](../write-safe-efficient-code.md).</span></span>

## <a name="non-trailing-named-arguments"></a><span data-ttu-id="63849-135">末尾以外の名前付き引数</span><span class="sxs-lookup"><span data-stu-id="63849-135">Non-trailing named arguments</span></span>

<span data-ttu-id="63849-136">メソッド呼び出しで、位置引数の前に名前付き引数を使用できるようになりました。ただし、そのような名前付き引数が正しい位置にある場合です。</span><span class="sxs-lookup"><span data-stu-id="63849-136">Method calls may now use named arguments that precede positional arguments when those named arguments are in the correct positions.</span></span> <span data-ttu-id="63849-137">詳細については、「[名前付き引数と省略可能な引数](../programming-guide/classes-and-structs/named-and-optional-arguments.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63849-137">For more information see [Named and optional arguments](../programming-guide/classes-and-structs/named-and-optional-arguments.md).</span></span>

## <a name="leading-underscores-in-numeric-literals"></a><span data-ttu-id="63849-138">数値リテラルでの先頭のアンダースコア (_)</span><span class="sxs-lookup"><span data-stu-id="63849-138">Leading underscores in numeric literals</span></span>

<span data-ttu-id="63849-139">C# 7.0 の桁区切り記号のサポートの実装では、`_` をリテラル値の最初の文字にすることができませんでした。</span><span class="sxs-lookup"><span data-stu-id="63849-139">The implementation of support for digit separators in C# 7.0 didn't allow the `_` to be the first character of the literal value.</span></span> <span data-ttu-id="63849-140">16 進とバイナリの数値リテラルの先頭に `_` を使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="63849-140">Hex and binary numeric literals may now begin with an `_`.</span></span>

<span data-ttu-id="63849-141">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="63849-141">For example:</span></span>

```csharp
int binaryValue = 0b_0101_0101;
```

## <a name="private-protected-access-modifier"></a><span data-ttu-id="63849-142">_private protected_ アクセス修飾子</span><span class="sxs-lookup"><span data-stu-id="63849-142">_private protected_ access modifier</span></span>

<span data-ttu-id="63849-143">新しい複合アクセス修飾子: `private protected` は、同じアセンブリで宣言されているクラスまたは派生クラスを含むことでメンバーにアクセスできることを示しています。</span><span class="sxs-lookup"><span data-stu-id="63849-143">A new compound access modifier: `private protected` indicates that a member may be accessed by containing class or derived classes that are declared in the same assembly.</span></span> <span data-ttu-id="63849-144">`protected internal` は同じアセンブリの派生クラスまたはクラスによるアクセスを許可していますが、`private protected` は同じアセンブリで宣言された派生型へのアクセスを制限しています。</span><span class="sxs-lookup"><span data-stu-id="63849-144">While `protected internal` allows access by derived classes or classes that are in the same assembly, `private protected` limits access to derived types declared in the same assembly.</span></span>

<span data-ttu-id="63849-145">詳細については、言語リファレンスの[アクセス修飾子](../language-reference/keywords/access-modifiers.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="63849-145">For more information see [access modifiers](../language-reference/keywords/access-modifiers.md) in the language reference.</span></span>

## <a name="conditional-ref-expressions"></a><span data-ttu-id="63849-146">条件付きの `ref` 式</span><span class="sxs-lookup"><span data-stu-id="63849-146">Conditional `ref` expressions</span></span>

<span data-ttu-id="63849-147">最後に、条件式で値の結果ではなく参照結果を生成することができます。</span><span class="sxs-lookup"><span data-stu-id="63849-147">Finally, the conditional expression may produce a ref result instead of a value result.</span></span> <span data-ttu-id="63849-148">たとえば、次のように記述して、2 つの配列のいずれかに含まれる最初の要素の参照を取得できます</span><span class="sxs-lookup"><span data-stu-id="63849-148">For example, you would write the following to retrieve a reference to the first element in one of two arrays:</span></span>

```csharp
ref var r = ref (arr != null ? ref arr[0] : ref otherArr[0]);
```

<span data-ttu-id="63849-149">変数 `r` は、`arr` または `otherArr` の最初の値の参照です。</span><span class="sxs-lookup"><span data-stu-id="63849-149">The variable `r` is a reference to the first value in either `arr` or `otherArr`.</span></span>

<span data-ttu-id="63849-150">詳細については、言語リファレンスの[条件演算子 (?:)](../language-reference/operators/conditional-operator.md) に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="63849-150">For more information, see [conditional operator (?:)](../language-reference/operators/conditional-operator.md) in the language reference.</span></span>
