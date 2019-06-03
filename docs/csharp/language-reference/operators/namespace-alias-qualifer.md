---
title: ':: 演算子 - C# リファレンス'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- ::_CSharpKeyword
helpviewer_keywords:
- ':: operator [C#]'
- 'namespaces [C#], :: operator'
- namespace alias qualifier operator (::) [C#]
ms.assetid: 698b5a73-85cf-4e0e-9e8e-6496887f8527
ms.openlocfilehash: 0b456ed3ce9965ef389d8ce40167afa4ac33da18
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/31/2019
ms.locfileid: "66422527"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="5dad5-102">:: 演算子 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="5dad5-102">:: operator (C# Reference)</span></span>

<span data-ttu-id="5dad5-103">名前空間エイリアス修飾子 (`::`) を使用して識別子を検索できます。</span><span class="sxs-lookup"><span data-stu-id="5dad5-103">The namespace alias qualifier (`::`) is used to look up identifiers.</span></span> <span data-ttu-id="5dad5-104">この例に示すように、常に 2 つの識別子の間に配置します。</span><span class="sxs-lookup"><span data-stu-id="5dad5-104">It is always positioned between two identifiers, as in this example:</span></span>

[!code-csharp[csRefOperators#27](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#27)]

<span data-ttu-id="5dad5-105">`::` 演算子は、"*using 別名ディレクティブ*" と一緒に使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="5dad5-105">The `::` operator can also be used with a *using alias directive*:</span></span>

```csharp
// using Col=System.Collections.Generic;
var numbers = new Col::List<int> { 1, 2, 3 };
```

## <a name="remarks"></a><span data-ttu-id="5dad5-106">解説</span><span class="sxs-lookup"><span data-stu-id="5dad5-106">Remarks</span></span>

<span data-ttu-id="5dad5-107">名前空間エイリアス修飾子として `global` を指定できます。</span><span class="sxs-lookup"><span data-stu-id="5dad5-107">The namespace alias qualifier can be `global`.</span></span> <span data-ttu-id="5dad5-108">これにより、エイリアスを使用した名前空間ではなく、グローバル名前空間で検索が実行されます。</span><span class="sxs-lookup"><span data-stu-id="5dad5-108">This invokes a lookup in the global namespace, rather than an aliased namespace.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="5dad5-109">詳細情報</span><span class="sxs-lookup"><span data-stu-id="5dad5-109">For more information</span></span>

<span data-ttu-id="5dad5-110">`::` 演算子の使用例については、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5dad5-110">For an example of how to use the `::` operator, see the following section:</span></span>

- [<span data-ttu-id="5dad5-111">方法: グローバル名前空間エイリアスを使用する</span><span class="sxs-lookup"><span data-stu-id="5dad5-111">How to: Use the Global Namespace Alias</span></span>](../../programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)

## <a name="c-language-specification"></a><span data-ttu-id="5dad5-112">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="5dad5-112">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="5dad5-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="5dad5-113">See also</span></span>

- [<span data-ttu-id="5dad5-114">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="5dad5-114">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="5dad5-115">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="5dad5-115">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="5dad5-116">C# 演算子</span><span class="sxs-lookup"><span data-stu-id="5dad5-116">C# operators</span></span>](index.md)
- [<span data-ttu-id="5dad5-117">演算子 .</span><span class="sxs-lookup"><span data-stu-id="5dad5-117">. operator</span></span>](member-access-operators.md#member-access-operator-)
- [<span data-ttu-id="5dad5-118">extern エイリアス</span><span class="sxs-lookup"><span data-stu-id="5dad5-118">extern alias</span></span>](../keywords/extern-alias.md)
