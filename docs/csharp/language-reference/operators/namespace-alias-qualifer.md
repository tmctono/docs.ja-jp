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
ms.openlocfilehash: c494e8dbb18f44ce5520b21800a21d3feb03da59
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2019
ms.locfileid: "67025073"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="0b25d-102">:: 演算子 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="0b25d-102">:: operator (C# reference)</span></span>

<span data-ttu-id="0b25d-103">名前空間エイリアス修飾子 (`::`) を使用して識別子を検索できます。</span><span class="sxs-lookup"><span data-stu-id="0b25d-103">The namespace alias qualifier (`::`) is used to look up identifiers.</span></span> <span data-ttu-id="0b25d-104">この例に示すように、常に 2 つの識別子の間に配置します。</span><span class="sxs-lookup"><span data-stu-id="0b25d-104">It is always positioned between two identifiers, as in this example:</span></span>

[!code-csharp[csRefOperators#27](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#27)]

<span data-ttu-id="0b25d-105">`::` 演算子は、"*using 別名ディレクティブ*" と一緒に使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="0b25d-105">The `::` operator can also be used with a *using alias directive*:</span></span>

```csharp
// using Col=System.Collections.Generic;
var numbers = new Col::List<int> { 1, 2, 3 };
```

## <a name="remarks"></a><span data-ttu-id="0b25d-106">解説</span><span class="sxs-lookup"><span data-stu-id="0b25d-106">Remarks</span></span>

<span data-ttu-id="0b25d-107">名前空間エイリアス修飾子として `global` を指定できます。</span><span class="sxs-lookup"><span data-stu-id="0b25d-107">The namespace alias qualifier can be `global`.</span></span> <span data-ttu-id="0b25d-108">これにより、エイリアスを使用した名前空間ではなく、グローバル名前空間で検索が実行されます。</span><span class="sxs-lookup"><span data-stu-id="0b25d-108">This invokes a lookup in the global namespace, rather than an aliased namespace.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="0b25d-109">BLOB の詳細</span><span class="sxs-lookup"><span data-stu-id="0b25d-109">For more information</span></span>

<span data-ttu-id="0b25d-110">`::` 演算子の使用例については、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b25d-110">For an example of how to use the `::` operator, see the following section:</span></span>

- [<span data-ttu-id="0b25d-111">方法: グローバル名前空間エイリアスを使用する</span><span class="sxs-lookup"><span data-stu-id="0b25d-111">How to: Use the Global Namespace Alias</span></span>](../../programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)

## <a name="c-language-specification"></a><span data-ttu-id="0b25d-112">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="0b25d-112">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="0b25d-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="0b25d-113">See also</span></span>

- [<span data-ttu-id="0b25d-114">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="0b25d-114">C# reference</span></span>](../index.md)
- [<span data-ttu-id="0b25d-115">C# 演算子</span><span class="sxs-lookup"><span data-stu-id="0b25d-115">C# operators</span></span>](index.md)
- [<span data-ttu-id="0b25d-116">演算子 .</span><span class="sxs-lookup"><span data-stu-id="0b25d-116">. operator</span></span>](member-access-operators.md#member-access-operator-)
- [<span data-ttu-id="0b25d-117">extern エイリアス</span><span class="sxs-lookup"><span data-stu-id="0b25d-117">extern alias</span></span>](../keywords/extern-alias.md)
