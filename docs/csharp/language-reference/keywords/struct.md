---
title: struct - C# リファレンス
ms.date: 07/20/2015
f1_keywords:
- struct_CSharpKeyword
helpviewer_keywords:
- struct keyword [C#]
- structs [C#], struct keyword
ms.assetid: ff3dd9b7-dc93-4720-8855-ef5558f65c7c
ms.openlocfilehash: 8d9a23a0813423571c894758257b284ad67a72e2
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744650"
---
# <a name="struct-c-reference"></a><span data-ttu-id="56e84-102">struct (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="56e84-102">struct (C# Reference)</span></span>

<span data-ttu-id="56e84-103">`struct` 型は、通常、関連する変数 (四角形の座標やインベントリ内の項目の特性など) の小さなグループをカプセル化するのに使用される値型です。</span><span class="sxs-lookup"><span data-stu-id="56e84-103">A `struct` type is a value type that is typically used to encapsulate small groups of related variables, such as the coordinates of a rectangle or the characteristics of an item in an inventory.</span></span> <span data-ttu-id="56e84-104">次の例に単純な構造体の宣言を示します。</span><span class="sxs-lookup"><span data-stu-id="56e84-104">The following example shows a simple struct declaration:</span></span>

```csharp
public struct Book
{
    public decimal price;
    public string title;
    public string author;
}
```

## <a name="remarks"></a><span data-ttu-id="56e84-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="56e84-105">Remarks</span></span>

<span data-ttu-id="56e84-106">構造体には、[コンストラクター](../../programming-guide/classes-and-structs/constructors.md)、[定数](../../programming-guide/classes-and-structs/constants.md)、[フィールド](../../programming-guide/classes-and-structs/fields.md)、[メソッド](../../programming-guide/classes-and-structs/methods.md)、[プロパティ](../../programming-guide/classes-and-structs/properties.md)、[インデクサー](../../programming-guide/indexers/index.md)、[演算子](../operators/index.md)、[イベント](../../programming-guide/events/index.md)、および[入れ子にされた型](../../programming-guide/classes-and-structs/nested-types.md)を含めることができます。ただし、複数のメンバーが必要な場合は、代わりに型をクラスに変更することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="56e84-106">Structs can also contain [constructors](../../programming-guide/classes-and-structs/constructors.md), [constants](../../programming-guide/classes-and-structs/constants.md), [fields](../../programming-guide/classes-and-structs/fields.md), [methods](../../programming-guide/classes-and-structs/methods.md), [properties](../../programming-guide/classes-and-structs/properties.md), [indexers](../../programming-guide/indexers/index.md), [operators](../operators/index.md), [events](../../programming-guide/events/index.md), and [nested types](../../programming-guide/classes-and-structs/nested-types.md), although if several such members are required, you should consider making your type a class instead.</span></span>

<span data-ttu-id="56e84-107">例については、「[構造体の使用](../../programming-guide/classes-and-structs/using-structs.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="56e84-107">For examples, see [Using Structs](../../programming-guide/classes-and-structs/using-structs.md).</span></span>

<span data-ttu-id="56e84-108">構造体はインターフェイスを実装できますが、別の構造体から継承することはできません。</span><span class="sxs-lookup"><span data-stu-id="56e84-108">Structs can implement an interface but they cannot inherit from another struct.</span></span> <span data-ttu-id="56e84-109">そのため、構造体メンバーを `protected` として宣言することはできません。</span><span class="sxs-lookup"><span data-stu-id="56e84-109">For that reason, struct members cannot be declared as `protected`.</span></span>

<span data-ttu-id="56e84-110">詳細については、「[構造体](../../programming-guide/classes-and-structs/structs.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="56e84-110">For more information, see [Structs](../../programming-guide/classes-and-structs/structs.md).</span></span>

## <a name="examples"></a><span data-ttu-id="56e84-111">使用例</span><span class="sxs-lookup"><span data-stu-id="56e84-111">Examples</span></span>

<span data-ttu-id="56e84-112">例と詳細については、「[構造体の使用](../../programming-guide/classes-and-structs/using-structs.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="56e84-112">For examples and more information, see [Using Structs](../../programming-guide/classes-and-structs/using-structs.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="56e84-113">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="56e84-113">C# language specification</span></span>

<span data-ttu-id="56e84-114">例については、「[構造体の使用](../../programming-guide/classes-and-structs/using-structs.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="56e84-114">For examples, see [Using Structs](../../programming-guide/classes-and-structs/using-structs.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="56e84-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="56e84-115">See also</span></span>

- [<span data-ttu-id="56e84-116">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="56e84-116">C# reference</span></span>](../index.md)
- [<span data-ttu-id="56e84-117">C# キーワード</span><span class="sxs-lookup"><span data-stu-id="56e84-117">C# keywords</span></span>](index.md)
- [<span data-ttu-id="56e84-118">組み込み型の一覧表</span><span class="sxs-lookup"><span data-stu-id="56e84-118">Built-in types table</span></span>](built-in-types-table.md)
- [<span data-ttu-id="56e84-119">値型</span><span class="sxs-lookup"><span data-stu-id="56e84-119">Value types</span></span>](../builtin-types/value-types.md)
- [<span data-ttu-id="56e84-120">class</span><span class="sxs-lookup"><span data-stu-id="56e84-120">class</span></span>](class.md)
- [<span data-ttu-id="56e84-121">interface</span><span class="sxs-lookup"><span data-stu-id="56e84-121">interface</span></span>](interface.md)
- [<span data-ttu-id="56e84-122">クラスと構造体</span><span class="sxs-lookup"><span data-stu-id="56e84-122">Classes and structs</span></span>](../../programming-guide/classes-and-structs/index.md)
