---
title: struct - C# リファレンス
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- struct_CSharpKeyword
helpviewer_keywords:
- struct keyword [C#]
- structs [C#], struct keyword
ms.assetid: ff3dd9b7-dc93-4720-8855-ef5558f65c7c
ms.openlocfilehash: 1f1c512e1995df07fc4b9e18e34a85119e270bda
ms.sourcegitcommit: 1e7ac70be1b4d89708c0d9552897515f2cbf52c4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2019
ms.locfileid: "68433785"
---
# <a name="struct-c-reference"></a><span data-ttu-id="e6c6b-102">struct (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="e6c6b-102">struct (C# Reference)</span></span>

<span data-ttu-id="e6c6b-103">`struct` 型は、通常、関連する変数 (四角形の座標やインベントリ内の項目の特性など) の小さなグループをカプセル化するのに使用される値型です。</span><span class="sxs-lookup"><span data-stu-id="e6c6b-103">A `struct` type is a value type that is typically used to encapsulate small groups of related variables, such as the coordinates of a rectangle or the characteristics of an item in an inventory.</span></span> <span data-ttu-id="e6c6b-104">次の例に単純な構造体の宣言を示します。</span><span class="sxs-lookup"><span data-stu-id="e6c6b-104">The following example shows a simple struct declaration:</span></span>

```csharp
public struct Book
{
    public decimal price;
    public string title;
    public string author;
}
```

## <a name="remarks"></a><span data-ttu-id="e6c6b-105">解説</span><span class="sxs-lookup"><span data-stu-id="e6c6b-105">Remarks</span></span>

<span data-ttu-id="e6c6b-106">構造体には、[コンストラクター](../../programming-guide/classes-and-structs/constructors.md)、[定数](../../programming-guide/classes-and-structs/constants.md)、[フィールド](../../programming-guide/classes-and-structs/fields.md)、[メソッド](../../programming-guide/classes-and-structs/methods.md)、[プロパティ](../../programming-guide/classes-and-structs/properties.md)、[インデクサー](../../programming-guide/indexers/index.md)、[演算子](../../programming-guide/statements-expressions-operators/operators.md)、[イベント](../../programming-guide/events/index.md)、および[入れ子にされた型](../../programming-guide/classes-and-structs/nested-types.md)を含めることができます。ただし、複数のメンバーが必要な場合は、代わりに型をクラスに変更することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="e6c6b-106">Structs can also contain [constructors](../../programming-guide/classes-and-structs/constructors.md), [constants](../../programming-guide/classes-and-structs/constants.md), [fields](../../programming-guide/classes-and-structs/fields.md), [methods](../../programming-guide/classes-and-structs/methods.md), [properties](../../programming-guide/classes-and-structs/properties.md), [indexers](../../programming-guide/indexers/index.md), [operators](../../programming-guide/statements-expressions-operators/operators.md), [events](../../programming-guide/events/index.md), and [nested types](../../programming-guide/classes-and-structs/nested-types.md), although if several such members are required, you should consider making your type a class instead.</span></span>

<span data-ttu-id="e6c6b-107">例については、「[構造体の使用](../../programming-guide/classes-and-structs/using-structs.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e6c6b-107">For examples, see [Using Structs](../../programming-guide/classes-and-structs/using-structs.md).</span></span>

<span data-ttu-id="e6c6b-108">構造体はインターフェイスを実装できますが、別の構造体から継承することはできません。</span><span class="sxs-lookup"><span data-stu-id="e6c6b-108">Structs can implement an interface but they cannot inherit from another struct.</span></span> <span data-ttu-id="e6c6b-109">そのため、構造体メンバーを `protected` として宣言することはできません。</span><span class="sxs-lookup"><span data-stu-id="e6c6b-109">For that reason, struct members cannot be declared as `protected`.</span></span>

<span data-ttu-id="e6c6b-110">詳細については、「[構造体](../../programming-guide/classes-and-structs/structs.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e6c6b-110">For more information, see [Structs](../../programming-guide/classes-and-structs/structs.md).</span></span>

## <a name="examples"></a><span data-ttu-id="e6c6b-111">使用例</span><span class="sxs-lookup"><span data-stu-id="e6c6b-111">Examples</span></span>

<span data-ttu-id="e6c6b-112">例と詳細については、「[構造体の使用](../../programming-guide/classes-and-structs/using-structs.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e6c6b-112">For examples and more information, see [Using Structs](../../programming-guide/classes-and-structs/using-structs.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="e6c6b-113">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="e6c6b-113">C# language specification</span></span>

<span data-ttu-id="e6c6b-114">例については、「[構造体の使用](../../programming-guide/classes-and-structs/using-structs.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e6c6b-114">For examples, see [Using Structs](../../programming-guide/classes-and-structs/using-structs.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e6c6b-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="e6c6b-115">See also</span></span>

- [<span data-ttu-id="e6c6b-116">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="e6c6b-116">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="e6c6b-117">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="e6c6b-117">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="e6c6b-118">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="e6c6b-118">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="e6c6b-119">既定値の一覧表</span><span class="sxs-lookup"><span data-stu-id="e6c6b-119">Default Values Table</span></span>](default-values-table.md)
- [<span data-ttu-id="e6c6b-120">組み込み型の一覧表</span><span class="sxs-lookup"><span data-stu-id="e6c6b-120">Built-In Types Table</span></span>](built-in-types-table.md)
- [<span data-ttu-id="e6c6b-121">型</span><span class="sxs-lookup"><span data-stu-id="e6c6b-121">Types</span></span>](types.md)
- [<span data-ttu-id="e6c6b-122">値型</span><span class="sxs-lookup"><span data-stu-id="e6c6b-122">Value Types</span></span>](value-types.md)
- [<span data-ttu-id="e6c6b-123">class</span><span class="sxs-lookup"><span data-stu-id="e6c6b-123">class</span></span>](class.md)
- [<span data-ttu-id="e6c6b-124">interface</span><span class="sxs-lookup"><span data-stu-id="e6c6b-124">interface</span></span>](interface.md)
- [<span data-ttu-id="e6c6b-125">クラスと構造体</span><span class="sxs-lookup"><span data-stu-id="e6c6b-125">Classes and Structs</span></span>](../../programming-guide/classes-and-structs/index.md)
