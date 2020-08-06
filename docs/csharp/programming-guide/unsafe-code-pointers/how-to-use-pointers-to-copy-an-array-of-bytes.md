---
title: ポインターを使用してバイトの配列をコピーする方法 - C# プログラミング ガイド
description: ポインターを使用してバイトの配列をコピーする方法について説明します。 コード例と、使用可能なその他のリソースを確認します。
ms.date: 04/20/2018
helpviewer_keywords:
- byte arrays [C#]
- arrays [C#], byte
- pointers [C#], to copy bytes
ms.openlocfilehash: 70ab1441d25ea69afb2244bd94bd404a3e32838d
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381789"
---
# <a name="how-to-use-pointers-to-copy-an-array-of-bytes-c-programming-guide"></a><span data-ttu-id="8198a-104">ポインターを使用してバイトの配列をコピーする方法 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="8198a-104">How to use pointers to copy an array of bytes (C# Programming Guide)</span></span>

<span data-ttu-id="8198a-105">次の例では、ポインターを使って 1 つの配列から別の配列にバイトをコピーします。</span><span class="sxs-lookup"><span data-stu-id="8198a-105">The following example uses pointers to copy bytes from one array to another.</span></span>

<span data-ttu-id="8198a-106">この例では、[unsafe](../../language-reference/keywords/unsafe.md) キーワードを使います。このキーワードは、`Copy` メソッドでのポインターの使用を可能にします。</span><span class="sxs-lookup"><span data-stu-id="8198a-106">This example uses the [unsafe](../../language-reference/keywords/unsafe.md) keyword, which enables you to use pointers in the `Copy` method.</span></span> <span data-ttu-id="8198a-107">[fixed](../../language-reference/keywords/fixed-statement.md) ステートメントを使って、コピー元とコピー先の配列へのポインターを宣言します。</span><span class="sxs-lookup"><span data-stu-id="8198a-107">The [fixed](../../language-reference/keywords/fixed-statement.md) statement is used to declare pointers to the source and destination arrays.</span></span> <span data-ttu-id="8198a-108">`fixed` ステートメントを使って、コピー元配列とコピー先配列のメモリ内での位置を "*固定*" し、ガベージ コレクションによって移動されないようにします。</span><span class="sxs-lookup"><span data-stu-id="8198a-108">The `fixed` statement *pins* the location of the source and destination arrays in memory so that they will not be moved by garbage collection.</span></span> <span data-ttu-id="8198a-109">`fixed` ブロックが完了すると、これらの配列のメモリ ブロックは固定解除されます。</span><span class="sxs-lookup"><span data-stu-id="8198a-109">The memory blocks for the arrays are unpinned when the `fixed` block is completed.</span></span> <span data-ttu-id="8198a-110">この例の `Copy` メソッドは `unsafe` キーワードを使っているので、[-unsafe](../../language-reference/compiler-options/unsafe-compiler-option.md) コンパイラ オプションを指定してコンパイルする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8198a-110">Because the `Copy` method in this example uses the `unsafe` keyword, it must be compiled with the [-unsafe](../../language-reference/compiler-options/unsafe-compiler-option.md) compiler option.</span></span>

<span data-ttu-id="8198a-111">この例では、2 番目のアンマネージド ポインターではなくインデックスを使って、両方の配列の要素にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="8198a-111">This example accesses the elements of both arrays using indices rather than a second unmanaged pointer.</span></span> <span data-ttu-id="8198a-112">`pSource` と `pTarget` のポインターの宣言を使って配列を固定します。</span><span class="sxs-lookup"><span data-stu-id="8198a-112">The declaration of the `pSource` and `pTarget` pointers pins the arrays.</span></span> <span data-ttu-id="8198a-113">この機能は、C# 7.3 以降から使用できます。</span><span class="sxs-lookup"><span data-stu-id="8198a-113">This feature is available starting with C# 7.3.</span></span>

## <a name="example"></a><span data-ttu-id="8198a-114">例</span><span class="sxs-lookup"><span data-stu-id="8198a-114">Example</span></span>

[!code-csharp[Struct with embedded inline array](snippets/FixedKeywordExamples.cs#8)]

## <a name="see-also"></a><span data-ttu-id="8198a-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="8198a-115">See also</span></span>

- [<span data-ttu-id="8198a-116">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="8198a-116">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="8198a-117">アンセーフ コードとポインター</span><span class="sxs-lookup"><span data-stu-id="8198a-117">Unsafe Code and Pointers</span></span>](index.md)
- [<span data-ttu-id="8198a-118">-unsafe (C# コンパイラ オプション)</span><span class="sxs-lookup"><span data-stu-id="8198a-118">-unsafe (C# Compiler Options)</span></span>](../../language-reference/compiler-options/unsafe-compiler-option.md)
- [<span data-ttu-id="8198a-119">ガベージ コレクション</span><span class="sxs-lookup"><span data-stu-id="8198a-119">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
