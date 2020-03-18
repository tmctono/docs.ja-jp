---
title: インターフェイスのプロパティ - C# プログラミング ガイド
ms.date: 01/31/2020
helpviewer_keywords:
- properties [C#], on interfaces
- interfaces [C#], properties
ms.assetid: 6503e9ed-33d7-44ec-b4c1-cc16c084b795
ms.openlocfilehash: 5798b80526f34e923e2eaab43847b98f6c64e14b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "77626621"
---
# <a name="interface-properties-c-programming-guide"></a><span data-ttu-id="b6d05-102">インターフェイスのプロパティ (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="b6d05-102">Interface Properties (C# Programming Guide)</span></span>

<span data-ttu-id="b6d05-103">[interface](../../language-reference/keywords/interface.md) でプロパティを宣言することができます。</span><span class="sxs-lookup"><span data-stu-id="b6d05-103">Properties can be declared on an [interface](../../language-reference/keywords/interface.md).</span></span> <span data-ttu-id="b6d05-104">次の例では、インターフェイス プロパティ アクセサーが宣言されます。</span><span class="sxs-lookup"><span data-stu-id="b6d05-104">The following example declares an interface property accessor:</span></span>

[!code-csharp[DeclareProperties](~/samples/snippets/csharp/interfaces/properties.cs#DeclareInterfaceProperties)]

<span data-ttu-id="b6d05-105">インターフェイス プロパティには通常、本体がありません。</span><span class="sxs-lookup"><span data-stu-id="b6d05-105">Interface properties typically don't have a body.</span></span> <span data-ttu-id="b6d05-106">プロパティが読み取り/書き込み、読み取り専用、書き込み専用のうちのどれであるかは、アクセサーによって示されます。</span><span class="sxs-lookup"><span data-stu-id="b6d05-106">The accessors indicate whether the property is read-write, read-only, or write-only.</span></span> <span data-ttu-id="b6d05-107">クラスや構造体の場合とは異なり、本体なしでアクセサーを宣言した場合、[自動実装プロパティ](auto-implemented-properties.md)は宣言されません。</span><span class="sxs-lookup"><span data-stu-id="b6d05-107">Unlike in classes and structs, declaring the accessors without a body doesn't declare an [auto-implemented property](auto-implemented-properties.md).</span></span> <span data-ttu-id="b6d05-108">C# 8.0 以降では、インターフェイスによって、プロパティを含む、メンバーの既定の実装を定義できます。</span><span class="sxs-lookup"><span data-stu-id="b6d05-108">Beginning with C# 8.0, an interface may define a default implementation for members, including properties.</span></span> <span data-ttu-id="b6d05-109">インターフェイスでプロパティの既定の実装を定義することはまれです。インターフェイスでは、インスタンス データ フィールドが定義されないことがあるためです。</span><span class="sxs-lookup"><span data-stu-id="b6d05-109">Defining a default implementation for a property in an interface is rare because interfaces may not define instance data fields.</span></span>

## <a name="example"></a><span data-ttu-id="b6d05-110">例</span><span class="sxs-lookup"><span data-stu-id="b6d05-110">Example</span></span>

<span data-ttu-id="b6d05-111">この例では、インターフェイス `IEmployee` に読み取り/書き込み専用のプロパティ `Name` および読み取り専用のプロパティ `Counter` があります。</span><span class="sxs-lookup"><span data-stu-id="b6d05-111">In this example, the interface `IEmployee` has a read-write property, `Name`, and a read-only property, `Counter`.</span></span> <span data-ttu-id="b6d05-112">クラス `Employee` は `IEmployee` インターフェイスを実装し、これら 2 つのプロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="b6d05-112">The class `Employee` implements the `IEmployee` interface and uses these two properties.</span></span> <span data-ttu-id="b6d05-113">プログラムは、新しい従業員の名前と現在の従業員の数を読み込んで、従業員の名前と計算した従業員番号を表示します。</span><span class="sxs-lookup"><span data-stu-id="b6d05-113">The program reads the name of a new employee and the current number of employees and displays the employee name and the computed employee number.</span></span>

<span data-ttu-id="b6d05-114">メンバーが宣言されているインターフェイスを参照するプロパティの完全修飾名を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="b6d05-114">You could use the fully qualified name of the property, which references the interface in which the member is declared.</span></span> <span data-ttu-id="b6d05-115">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="b6d05-115">For example:</span></span>

[!code-csharp[ExplicitProperties](~/samples/snippets/csharp/interfaces/properties.cs#ExplicitImplementation)]

<span data-ttu-id="b6d05-116">前の例では、[明示的なインターフェイス実装](../interfaces/explicit-interface-implementation.md)を確認できます。</span><span class="sxs-lookup"><span data-stu-id="b6d05-116">The preceding example demonstrates [Explicit Interface Implementation](../interfaces/explicit-interface-implementation.md).</span></span> <span data-ttu-id="b6d05-117">たとえば、`Employee` クラスが 2 つのインターフェイス `ICitizen` と `IEmployee` を実装し、両方のインターフェイスが同じ `Name` プロパティを持っている場合、明示的なインターフェイス メンバーの実装が必要です。</span><span class="sxs-lookup"><span data-stu-id="b6d05-117">For example, if the class `Employee` is implementing two interfaces `ICitizen` and `IEmployee` and both interfaces have the `Name` property, the explicit interface member implementation will be necessary.</span></span> <span data-ttu-id="b6d05-118">つまり、次のプロパティの宣言があります。</span><span class="sxs-lookup"><span data-stu-id="b6d05-118">That is, the following property declaration:</span></span>

[!code-csharp[ExplicitProperties](~/samples/snippets/csharp/interfaces/properties.cs#ExplicitImplementation)]

<span data-ttu-id="b6d05-119">これは、`IEmployee` インターフェイスで `Name` プロパティを実装します。次の宣言があります。</span><span class="sxs-lookup"><span data-stu-id="b6d05-119">implements the `Name` property on the `IEmployee` interface, while the following declaration:</span></span>

[!code-csharp[ExplicitProperties](~/samples/snippets/csharp/interfaces/properties.cs#CitizenImplementation)]

<span data-ttu-id="b6d05-120">これは、`ICitizen` インターフェイスで `Name` プロパティを実装します。</span><span class="sxs-lookup"><span data-stu-id="b6d05-120">implements the `Name` property on the `ICitizen` interface.</span></span>

[!code-csharp[Example](~/samples/snippets/csharp/interfaces/properties.cs#PropertyExample)]
[!code-csharp[Example](~/samples/snippets/csharp/interfaces/properties.cs#UseProperty)]

**`210 Hazem Abolrous`**

## <a name="sample-output"></a><span data-ttu-id="b6d05-121">出力例</span><span class="sxs-lookup"><span data-stu-id="b6d05-121">Sample output</span></span>

```console
Enter number of employees: 210
Enter the name of the new employee: Hazem Abolrous
The employee information:
Employee number: 211
Employee name: Hazem Abolrous
```

## <a name="see-also"></a><span data-ttu-id="b6d05-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="b6d05-122">See also</span></span>

- [<span data-ttu-id="b6d05-123">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="b6d05-123">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="b6d05-124">プロパティ</span><span class="sxs-lookup"><span data-stu-id="b6d05-124">Properties</span></span>](./properties.md)
- [<span data-ttu-id="b6d05-125">プロパティの使用</span><span class="sxs-lookup"><span data-stu-id="b6d05-125">Using Properties</span></span>](./using-properties.md)
- [<span data-ttu-id="b6d05-126">プロパティとインデクサーの比較</span><span class="sxs-lookup"><span data-stu-id="b6d05-126">Comparison Between Properties and Indexers</span></span>](../indexers/comparison-between-properties-and-indexers.md)
- [<span data-ttu-id="b6d05-127">インデクサー</span><span class="sxs-lookup"><span data-stu-id="b6d05-127">Indexers</span></span>](../indexers/index.md)
- [<span data-ttu-id="b6d05-128">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b6d05-128">Interfaces</span></span>](../interfaces/index.md)
