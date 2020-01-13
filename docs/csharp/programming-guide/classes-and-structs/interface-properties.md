---
title: インターフェイスのプロパティ - C# プログラミング ガイド
ms.date: 07/20/2015
helpviewer_keywords:
- properties [C#], on interfaces
- interfaces [C#], properties
ms.assetid: 6503e9ed-33d7-44ec-b4c1-cc16c084b795
ms.openlocfilehash: ff892a35f4be6600c00bc0c72c2f789ef6eb4408
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705536"
---
# <a name="interface-properties-c-programming-guide"></a><span data-ttu-id="49b8b-102">インターフェイスのプロパティ (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="49b8b-102">Interface Properties (C# Programming Guide)</span></span>

<span data-ttu-id="49b8b-103">[interface](../../language-reference/keywords/interface.md) でプロパティを宣言することができます。</span><span class="sxs-lookup"><span data-stu-id="49b8b-103">Properties can be declared on an [interface](../../language-reference/keywords/interface.md).</span></span> <span data-ttu-id="49b8b-104">インターフェイスのプロパティ アクセサーの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="49b8b-104">The following is an example of an interface property accessor:</span></span>

[!code-csharp[csProgGuideProperties#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#14)]

<span data-ttu-id="49b8b-105">インターフェイス プロパティのアクセサーには、本文はありません。</span><span class="sxs-lookup"><span data-stu-id="49b8b-105">The accessor of an interface property does not have a body.</span></span> <span data-ttu-id="49b8b-106">したがって、アクセサーの目的は、プロパティが読み取り/書き込み、読み取り専用、または書き込み専用のどれかを示すことです。</span><span class="sxs-lookup"><span data-stu-id="49b8b-106">Thus, the purpose of the accessors is to indicate whether the property is read-write, read-only, or write-only.</span></span>

## <a name="example"></a><span data-ttu-id="49b8b-107">例</span><span class="sxs-lookup"><span data-stu-id="49b8b-107">Example</span></span>

<span data-ttu-id="49b8b-108">この例では、インターフェイス `IEmployee` に読み取り/書き込み専用のプロパティ `Name` および読み取り専用のプロパティ `Counter` があります。</span><span class="sxs-lookup"><span data-stu-id="49b8b-108">In this example, the interface `IEmployee` has a read-write property, `Name`, and a read-only property, `Counter`.</span></span> <span data-ttu-id="49b8b-109">クラス `Employee` は `IEmployee` インターフェイスを実装し、これら 2 つのプロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="49b8b-109">The class `Employee` implements the `IEmployee` interface and uses these two properties.</span></span> <span data-ttu-id="49b8b-110">プログラムは、新しい従業員の名前と現在の従業員の数を読み込んで、従業員の名前と計算した従業員番号を表示します。</span><span class="sxs-lookup"><span data-stu-id="49b8b-110">The program reads the name of a new employee and the current number of employees and displays the employee name and the computed employee number.</span></span>

<span data-ttu-id="49b8b-111">メンバーが宣言されているインターフェイスを参照するプロパティの完全修飾名を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="49b8b-111">You could use the fully qualified name of the property, which references the interface in which the member is declared.</span></span> <span data-ttu-id="49b8b-112">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="49b8b-112">For example:</span></span>

[!code-csharp[csProgGuideProperties#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#16)]

<span data-ttu-id="49b8b-113">これは、[明示的なインターフェイスの実装](../interfaces/explicit-interface-implementation.md)で呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="49b8b-113">This is called [Explicit Interface Implementation](../interfaces/explicit-interface-implementation.md).</span></span> <span data-ttu-id="49b8b-114">たとえば、`Employee` クラスが 2 つのインターフェイス `ICitizen` と `IEmployee` を実装し、両方のインターフェイスが同じ `Name` プロパティを持っている場合、明示的なインターフェイス メンバーの実装が必要です。</span><span class="sxs-lookup"><span data-stu-id="49b8b-114">For example, if the class `Employee` is implementing two interfaces `ICitizen` and `IEmployee` and both interfaces have the `Name` property, the explicit interface member implementation will be necessary.</span></span> <span data-ttu-id="49b8b-115">つまり、次のプロパティの宣言があります。</span><span class="sxs-lookup"><span data-stu-id="49b8b-115">That is, the following property declaration:</span></span>

[!code-csharp[csProgGuideProperties#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#16)]

<span data-ttu-id="49b8b-116">これは、`IEmployee` インターフェイスで `Name` プロパティを実装します。次の宣言があります。</span><span class="sxs-lookup"><span data-stu-id="49b8b-116">implements the `Name` property on the `IEmployee` interface, while the following declaration:</span></span>

[!code-csharp[csProgGuideProperties#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#17)]

<span data-ttu-id="49b8b-117">これは、`ICitizen` インターフェイスで `Name` プロパティを実装します。</span><span class="sxs-lookup"><span data-stu-id="49b8b-117">implements the `Name` property on the `ICitizen` interface.</span></span>

[!code-csharp[csProgGuideProperties#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#15)]

**`210 Hazem Abolrous`**

## <a name="sample-output"></a><span data-ttu-id="49b8b-118">出力例</span><span class="sxs-lookup"><span data-stu-id="49b8b-118">Sample output</span></span>

```console
Enter number of employees: 210
Enter the name of the new employee: Hazem Abolrous
The employee information:
Employee number: 211
Employee name: Hazem Abolrous
```

## <a name="see-also"></a><span data-ttu-id="49b8b-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="49b8b-119">See also</span></span>

- [<span data-ttu-id="49b8b-120">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="49b8b-120">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="49b8b-121">プロパティ</span><span class="sxs-lookup"><span data-stu-id="49b8b-121">Properties</span></span>](./properties.md)
- [<span data-ttu-id="49b8b-122">プロパティの使用</span><span class="sxs-lookup"><span data-stu-id="49b8b-122">Using Properties</span></span>](./using-properties.md)
- [<span data-ttu-id="49b8b-123">プロパティとインデクサーの比較</span><span class="sxs-lookup"><span data-stu-id="49b8b-123">Comparison Between Properties and Indexers</span></span>](../indexers/comparison-between-properties-and-indexers.md)
- [<span data-ttu-id="49b8b-124">インデクサー</span><span class="sxs-lookup"><span data-stu-id="49b8b-124">Indexers</span></span>](../indexers/index.md)
- [<span data-ttu-id="49b8b-125">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="49b8b-125">Interfaces</span></span>](../interfaces/index.md)
