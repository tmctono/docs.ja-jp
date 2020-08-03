---
title: インターフェイスのプロパティ - C# プログラミング ガイド
description: C# のインターフェイスでプロパティを宣言することができます。 この例では、インターフェイス プロパティ アクセサーが宣言されます。
ms.date: 01/31/2020
helpviewer_keywords:
- properties [C#], on interfaces
- interfaces [C#], properties
ms.assetid: 6503e9ed-33d7-44ec-b4c1-cc16c084b795
ms.openlocfilehash: 920381ae804a6a968bfd667171269377f3d7e448
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2020
ms.locfileid: "86864970"
---
# <a name="interface-properties-c-programming-guide"></a><span data-ttu-id="97480-104">インターフェイスのプロパティ (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="97480-104">Interface Properties (C# Programming Guide)</span></span>

<span data-ttu-id="97480-105">[interface](../../language-reference/keywords/interface.md) でプロパティを宣言することができます。</span><span class="sxs-lookup"><span data-stu-id="97480-105">Properties can be declared on an [interface](../../language-reference/keywords/interface.md).</span></span> <span data-ttu-id="97480-106">次の例では、インターフェイス プロパティ アクセサーが宣言されます。</span><span class="sxs-lookup"><span data-stu-id="97480-106">The following example declares an interface property accessor:</span></span>

[!code-csharp[DeclareProperties](~/samples/snippets/csharp/interfaces/properties.cs#DeclareInterfaceProperties)]

<span data-ttu-id="97480-107">インターフェイス プロパティには通常、本体がありません。</span><span class="sxs-lookup"><span data-stu-id="97480-107">Interface properties typically don't have a body.</span></span> <span data-ttu-id="97480-108">プロパティが読み取り/書き込み、読み取り専用、書き込み専用のうちのどれであるかは、アクセサーによって示されます。</span><span class="sxs-lookup"><span data-stu-id="97480-108">The accessors indicate whether the property is read-write, read-only, or write-only.</span></span> <span data-ttu-id="97480-109">クラスや構造体の場合とは異なり、本体なしでアクセサーを宣言した場合、[自動実装プロパティ](auto-implemented-properties.md)は宣言されません。</span><span class="sxs-lookup"><span data-stu-id="97480-109">Unlike in classes and structs, declaring the accessors without a body doesn't declare an [auto-implemented property](auto-implemented-properties.md).</span></span> <span data-ttu-id="97480-110">C# 8.0 以降では、インターフェイスによって、プロパティを含む、メンバーの既定の実装を定義できます。</span><span class="sxs-lookup"><span data-stu-id="97480-110">Beginning with C# 8.0, an interface may define a default implementation for members, including properties.</span></span> <span data-ttu-id="97480-111">インターフェイスでプロパティの既定の実装を定義することはまれです。インターフェイスでは、インスタンス データ フィールドが定義されないことがあるためです。</span><span class="sxs-lookup"><span data-stu-id="97480-111">Defining a default implementation for a property in an interface is rare because interfaces may not define instance data fields.</span></span>

## <a name="example"></a><span data-ttu-id="97480-112">例</span><span class="sxs-lookup"><span data-stu-id="97480-112">Example</span></span>

<span data-ttu-id="97480-113">この例では、インターフェイス `IEmployee` に読み取り/書き込み専用のプロパティ `Name` および読み取り専用のプロパティ `Counter` があります。</span><span class="sxs-lookup"><span data-stu-id="97480-113">In this example, the interface `IEmployee` has a read-write property, `Name`, and a read-only property, `Counter`.</span></span> <span data-ttu-id="97480-114">クラス `Employee` は `IEmployee` インターフェイスを実装し、これら 2 つのプロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="97480-114">The class `Employee` implements the `IEmployee` interface and uses these two properties.</span></span> <span data-ttu-id="97480-115">プログラムは、新しい従業員の名前と現在の従業員の数を読み込んで、従業員の名前と計算した従業員番号を表示します。</span><span class="sxs-lookup"><span data-stu-id="97480-115">The program reads the name of a new employee and the current number of employees and displays the employee name and the computed employee number.</span></span>

<span data-ttu-id="97480-116">メンバーが宣言されているインターフェイスを参照するプロパティの完全修飾名を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="97480-116">You could use the fully qualified name of the property, which references the interface in which the member is declared.</span></span> <span data-ttu-id="97480-117">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="97480-117">For example:</span></span>

[!code-csharp[ExplicitProperties](~/samples/snippets/csharp/interfaces/properties.cs#ExplicitImplementation)]

<span data-ttu-id="97480-118">前の例では、[明示的なインターフェイス実装](../interfaces/explicit-interface-implementation.md)を確認できます。</span><span class="sxs-lookup"><span data-stu-id="97480-118">The preceding example demonstrates [Explicit Interface Implementation](../interfaces/explicit-interface-implementation.md).</span></span> <span data-ttu-id="97480-119">たとえば、`Employee` クラスが 2 つのインターフェイス `ICitizen` と `IEmployee` を実装し、両方のインターフェイスが同じ `Name` プロパティを持っている場合、明示的なインターフェイス メンバーの実装が必要です。</span><span class="sxs-lookup"><span data-stu-id="97480-119">For example, if the class `Employee` is implementing two interfaces `ICitizen` and `IEmployee` and both interfaces have the `Name` property, the explicit interface member implementation will be necessary.</span></span> <span data-ttu-id="97480-120">つまり、次のプロパティの宣言があります。</span><span class="sxs-lookup"><span data-stu-id="97480-120">That is, the following property declaration:</span></span>

[!code-csharp[ExplicitProperties](~/samples/snippets/csharp/interfaces/properties.cs#ExplicitImplementation)]

<span data-ttu-id="97480-121">これは、`IEmployee` インターフェイスで `Name` プロパティを実装します。次の宣言があります。</span><span class="sxs-lookup"><span data-stu-id="97480-121">implements the `Name` property on the `IEmployee` interface, while the following declaration:</span></span>

[!code-csharp[ExplicitProperties](~/samples/snippets/csharp/interfaces/properties.cs#CitizenImplementation)]

<span data-ttu-id="97480-122">これは、`ICitizen` インターフェイスで `Name` プロパティを実装します。</span><span class="sxs-lookup"><span data-stu-id="97480-122">implements the `Name` property on the `ICitizen` interface.</span></span>

[!code-csharp[Example](~/samples/snippets/csharp/interfaces/properties.cs#PropertyExample)]
[!code-csharp[Example](~/samples/snippets/csharp/interfaces/properties.cs#UseProperty)]

**`210 Hazem Abolrous`**

## <a name="sample-output"></a><span data-ttu-id="97480-123">サンプル出力</span><span class="sxs-lookup"><span data-stu-id="97480-123">Sample output</span></span>

```console
Enter number of employees: 210
Enter the name of the new employee: Hazem Abolrous
The employee information:
Employee number: 211
Employee name: Hazem Abolrous
```

## <a name="see-also"></a><span data-ttu-id="97480-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="97480-124">See also</span></span>

- [<span data-ttu-id="97480-125">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="97480-125">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="97480-126">プロパティ</span><span class="sxs-lookup"><span data-stu-id="97480-126">Properties</span></span>](./properties.md)
- [<span data-ttu-id="97480-127">プロパティの使用</span><span class="sxs-lookup"><span data-stu-id="97480-127">Using Properties</span></span>](./using-properties.md)
- [<span data-ttu-id="97480-128">プロパティとインデクサーの比較</span><span class="sxs-lookup"><span data-stu-id="97480-128">Comparison Between Properties and Indexers</span></span>](../indexers/comparison-between-properties-and-indexers.md)
- [<span data-ttu-id="97480-129">インデクサー</span><span class="sxs-lookup"><span data-stu-id="97480-129">Indexers</span></span>](../indexers/index.md)
- [<span data-ttu-id="97480-130">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="97480-130">Interfaces</span></span>](../interfaces/index.md)
