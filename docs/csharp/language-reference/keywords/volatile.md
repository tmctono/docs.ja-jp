---
title: volatile - C# リファレンス
ms.date: 10/24/2018
f1_keywords:
- volatile_CSharpKeyword
- volatile
helpviewer_keywords:
- volatile keyword [C#]
ms.assetid: 78089bc7-7b38-4cfd-9e49-87ac036af009
ms.openlocfilehash: c7a6c442c33ac2b41f652805837f455a957819de
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712846"
---
# <a name="volatile-c-reference"></a><span data-ttu-id="bd931-102">volatile (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="bd931-102">volatile (C# Reference)</span></span>

<span data-ttu-id="bd931-103">`volatile` キーワードは、同時に実行されている複数のスレッドによって、フィールドが変更される可能性があることを示します。</span><span class="sxs-lookup"><span data-stu-id="bd931-103">The `volatile` keyword indicates that a field might be modified by multiple threads that are executing at the same time.</span></span> <span data-ttu-id="bd931-104">コンパイラ、ランタイム システム、さらにはハードウェアで、パフォーマンスを上げる目的でメモリの読み書き場所を再配置するかもしれません。</span><span class="sxs-lookup"><span data-stu-id="bd931-104">The compiler, the runtime system, and even hardware may rearrange reads and writes to memory locations for performance reasons.</span></span> <span data-ttu-id="bd931-105">`volatile` が宣言されているフィールドはこのような最適化の対象になりません。</span><span class="sxs-lookup"><span data-stu-id="bd931-105">Fields that are declared `volatile` are not subject to these optimizations.</span></span> <span data-ttu-id="bd931-106">`volatile` 修飾子を追加することで、すべてのスレッドによって、他のスレッドにより実行される volatile 書き込みがその実行順序どおりに観察されます。</span><span class="sxs-lookup"><span data-stu-id="bd931-106">Adding the `volatile` modifier ensures that all threads will observe volatile writes performed by any other thread in the order in which they were performed.</span></span> <span data-ttu-id="bd931-107">全ての実行スレッドから見たvolatile 書き込みの全体的順序が単一である保証はありません。</span><span class="sxs-lookup"><span data-stu-id="bd931-107">There is no guarantee of a single total ordering of volatile writes as seen from all threads of execution.</span></span>

<span data-ttu-id="bd931-108">`volatile` キーワードは次の型のフィールドに使用できます。</span><span class="sxs-lookup"><span data-stu-id="bd931-108">The `volatile` keyword can be applied to fields of these types:</span></span>

- <span data-ttu-id="bd931-109">参照型。</span><span class="sxs-lookup"><span data-stu-id="bd931-109">Reference types.</span></span>
- <span data-ttu-id="bd931-110">ポインター型 (unsafe コンテキスト内)。</span><span class="sxs-lookup"><span data-stu-id="bd931-110">Pointer types (in an unsafe context).</span></span> <span data-ttu-id="bd931-111">ポインター自体は volatile にできますが、ポインターが指しているオブジェクトは volatile にできません。</span><span class="sxs-lookup"><span data-stu-id="bd931-111">Note that although the pointer itself can be volatile, the object that it points to cannot.</span></span> <span data-ttu-id="bd931-112">つまり、"volatile を指すポインター" は宣言できません。</span><span class="sxs-lookup"><span data-stu-id="bd931-112">In other words, you cannot declare a "pointer to volatile."</span></span>
- <span data-ttu-id="bd931-113">`sbyte`、`byte`、`short`、`ushort`、`int`、`uint`、`char`、`float`、`bool` など、単純型。</span><span class="sxs-lookup"><span data-stu-id="bd931-113">Simple types such as `sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `char`, `float`, and `bool`.</span></span>
- <span data-ttu-id="bd931-114">基本型が `byte`、`sbyte`、`short`、`ushort`、`int`、`uint` のいずれかの `enum` 型。</span><span class="sxs-lookup"><span data-stu-id="bd931-114">An `enum` type with one of the following base types: `byte`, `sbyte`, `short`, `ushort`, `int`, or `uint`.</span></span>
- <span data-ttu-id="bd931-115">参照型であることが判明しているジェネリック型パラメーター。</span><span class="sxs-lookup"><span data-stu-id="bd931-115">Generic type parameters known to be reference types.</span></span>
- <span data-ttu-id="bd931-116"><xref:System.IntPtr> および <xref:System.UIntPtr>。</span><span class="sxs-lookup"><span data-stu-id="bd931-116"><xref:System.IntPtr> and <xref:System.UIntPtr>.</span></span>

<span data-ttu-id="bd931-117">`double` や `long` など、その他の型には `volatile` を指定できません。そのような型のフィールドに対する読み書きはアトミックになるとは限らないためです。</span><span class="sxs-lookup"><span data-stu-id="bd931-117">Other types, including `double` and `long`, cannot be marked `volatile` because reads and writes to fields of those types cannot be guaranteed to be atomic.</span></span> <span data-ttu-id="bd931-118">そのような型のフィールドへのマルチスレッド アクセスを保護するために、<xref:System.Threading.Interlocked> クラス メンバーを使用するか、[`lock`](lock-statement.md) ステートメントでアクセスを保護します。</span><span class="sxs-lookup"><span data-stu-id="bd931-118">To protect multi-threaded access to those types of fields, use the <xref:System.Threading.Interlocked> class members or protect access using the [`lock`](lock-statement.md) statement.</span></span>

<span data-ttu-id="bd931-119">`volatile` キーワードは `class` または `struct` のフィールドにのみ適用できます。</span><span class="sxs-lookup"><span data-stu-id="bd931-119">The `volatile` keyword can only be applied to fields of a `class` or `struct`.</span></span> <span data-ttu-id="bd931-120">ローカル変数を `volatile` として宣言することはできません。</span><span class="sxs-lookup"><span data-stu-id="bd931-120">Local variables cannot be declared `volatile`.</span></span>

## <a name="example"></a><span data-ttu-id="bd931-121">例</span><span class="sxs-lookup"><span data-stu-id="bd931-121">Example</span></span>

<span data-ttu-id="bd931-122">次の例は、public のフィールド変数を `volatile` として宣言する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="bd931-122">The following example shows how to declare a public field variable as `volatile`.</span></span>

[!code-csharp[declareVolatile](~/samples/snippets/csharp/language-reference/keywords/volatile/Program.cs#Declaration)]

<span data-ttu-id="bd931-123">次の例は、補助スレッドつまりワーカー スレッドを作成および使用して、プライマリ スレッドとの並行処理を実行する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="bd931-123">The following example demonstrates how an auxiliary or worker thread can be created and used to perform processing in parallel with that of the primary thread.</span></span> <span data-ttu-id="bd931-124">マルチスレッドについて詳しくは、「[マネージド スレッド処理](../../../standard/threading/index.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="bd931-124">For more information about multithreading, see [Managed Threading](../../../standard/threading/index.md).</span></span>

[!code-csharp[declareVolatile](~/samples/snippets/csharp/language-reference/keywords/volatile/Program.cs#Volatile)]

<span data-ttu-id="bd931-125">`volatile` 修飾子を `_shouldStop` の宣言に追加することで、(前述のコードにある抜粋に似た) 同じ結果が常に得られます。</span><span class="sxs-lookup"><span data-stu-id="bd931-125">With the `volatile` modifier added to the declaration of `_shouldStop` in place, you'll always get the same results (similar to the excerpt shown in the preceding code).</span></span> <span data-ttu-id="bd931-126">しかしながら、この修飾子が `_shouldStop` メンバーになければ、動作は予測できません。</span><span class="sxs-lookup"><span data-stu-id="bd931-126">However, without that modifier on the `_shouldStop` member, the behavior is unpredictable.</span></span> <span data-ttu-id="bd931-127">`DoWork` メソッドでメンバー アクセスが最適化されることがありますが、古いデータが読み取られます。</span><span class="sxs-lookup"><span data-stu-id="bd931-127">The `DoWork` method may optimize the member access, resulting in reading stale data.</span></span> <span data-ttu-id="bd931-128">マルチスレッド プログラミングの性質上、古い読み取りの数は予測できません。</span><span class="sxs-lookup"><span data-stu-id="bd931-128">Because of the nature of multi-threaded programming, the number of stale reads is unpredictable.</span></span> <span data-ttu-id="bd931-129">プログラムを実行するたびに若干異なる結果が得られます。</span><span class="sxs-lookup"><span data-stu-id="bd931-129">Different runs of the program will produce somewhat different results.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="bd931-130">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="bd931-130">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="bd931-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="bd931-131">See also</span></span>

- [<span data-ttu-id="bd931-132">C# 言語仕様: volatile キーワード</span><span class="sxs-lookup"><span data-stu-id="bd931-132">C# language specification: volatile keyword</span></span>](../../../../_csharplang/spec/classes.md#volatile-fields)
- [<span data-ttu-id="bd931-133">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="bd931-133">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="bd931-134">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="bd931-134">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="bd931-135">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="bd931-135">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="bd931-136">修飾子</span><span class="sxs-lookup"><span data-stu-id="bd931-136">Modifiers</span></span>](index.md)
- [<span data-ttu-id="bd931-137">lock ステートメント</span><span class="sxs-lookup"><span data-stu-id="bd931-137">lock statement</span></span>](lock-statement.md)
- <xref:System.Threading.Interlocked>
