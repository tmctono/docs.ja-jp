---
title: COM 相互運用機能を使用したプログラミングでインデックス付きプロパティを使用する方法 - C# プログラミング ガイド
description: この C# の例では、インデックス付きプロパティを使用して、パラメーターを持つ COM プロパティを使用しやすくする方法について説明します。
ms.date: 07/20/2015
helpviewer_keywords:
- indexed properties [C#]
- Office programming [C#], indexed properties
- properties [C#], indexed
ms.assetid: 756bfc1e-7c28-4d4d-b114-ac9288c73882
ms.openlocfilehash: abd785864bd79d455024cb4501c76a21b349aa91
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303011"
---
# <a name="how-to-use-indexed-properties-in-com-interop-programming-c-programming-guide"></a><span data-ttu-id="b4f43-103">COM 相互運用機能を使用したプログラミングでインデックス付きプロパティを使用する方法 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="b4f43-103">How to use indexed properties in COM interop programming (C# Programming Guide)</span></span>
<span data-ttu-id="b4f43-104">"*インデックス付きプロパティ*" により、パラメーターを持つ COM プロパティが C# プログラミングでいっそう使いやすくなります。</span><span class="sxs-lookup"><span data-stu-id="b4f43-104">*Indexed properties* improve the way in which COM properties that have parameters are consumed in C# programming.</span></span> <span data-ttu-id="b4f43-105">インデックス付きプロパティは、[名前付き引数と省略可能な引数](../classes-and-structs/named-and-optional-arguments.md)、新しい型 ([dynamic](../../language-reference/builtin-types/reference-types.md))、[埋め込み型情報](../../../standard/assembly/embed-types-visual-studio.md)などの Visual C# の他の機能と連携して、Microsoft Office プログラミングをいっそう強力なものにします。</span><span class="sxs-lookup"><span data-stu-id="b4f43-105">Indexed properties work together with other features in Visual C#, such as [named and optional arguments](../classes-and-structs/named-and-optional-arguments.md), a new type ([dynamic](../../language-reference/builtin-types/reference-types.md)), and [embedded type information](../../../standard/assembly/embed-types-visual-studio.md), to enhance Microsoft Office programming.</span></span>  
  
 <span data-ttu-id="b4f43-106">以前のバージョンの C# では、プロパティとしてメソッドにアクセスできるのは、`get` メソッドがパラメーターを持たず、`set` メソッドが 1 つだけ値パラメーターを持つ場合に限られました。</span><span class="sxs-lookup"><span data-stu-id="b4f43-106">In earlier versions of C#, methods are accessible as properties only if the `get` method has no parameters and the `set` method has one and only one value parameter.</span></span> <span data-ttu-id="b4f43-107">しかし、すべての COM プロパティがこのような制限を満たしているわけではありません。</span><span class="sxs-lookup"><span data-stu-id="b4f43-107">However, not all COM properties meet those restrictions.</span></span> <span data-ttu-id="b4f43-108">たとえば、Excel の <xref:Microsoft.Office.Interop.Excel.Range.Range%2A> プロパティには、範囲の名前のパラメーターを必要とする `get` アクセサーがあります。</span><span class="sxs-lookup"><span data-stu-id="b4f43-108">For example, the Excel <xref:Microsoft.Office.Interop.Excel.Range.Range%2A> property has a `get` accessor that requires a parameter for the name of the range.</span></span> <span data-ttu-id="b4f43-109">これまでは、このような `Range` プロパティに直接アクセスすることはできず、次の例に示すように、`get_Range` メソッドを代わりに使う必要がありました。</span><span class="sxs-lookup"><span data-stu-id="b4f43-109">In the past, because you could not access the `Range` property directly, you had to use the `get_Range` method instead, as shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideIndexedProperties#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#1)]  
  
 <span data-ttu-id="b4f43-110">インデックス付きプロパティを使うと、次のようなコードを記述できます。</span><span class="sxs-lookup"><span data-stu-id="b4f43-110">Indexed properties enable you to write the following instead:</span></span>  
  
 [!code-csharp[csProgGuideIndexedProperties#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#2)]  
  
> [!NOTE]
> <span data-ttu-id="b4f43-111">また、前の例では、[省略可能な引数](../classes-and-structs/named-and-optional-arguments.md)機能も使われており、`Type.Missing` を省略できます。</span><span class="sxs-lookup"><span data-stu-id="b4f43-111">The previous example also uses the [optional arguments](../classes-and-structs/named-and-optional-arguments.md) feature, which enables you to omit `Type.Missing`.</span></span>  
  
 <span data-ttu-id="b4f43-112">C# 3.0 以前で <xref:Microsoft.Office.Interop.Excel.Range> オブジェクトの `Value` プロパティの値を設定する場合と同様に、2 つの引数が必要です。</span><span class="sxs-lookup"><span data-stu-id="b4f43-112">Similarly to set the value of the `Value` property of a <xref:Microsoft.Office.Interop.Excel.Range> object in C# 3.0 and earlier, two arguments are required.</span></span> <span data-ttu-id="b4f43-113">1 つのパラメーターでは、範囲の値の型を指定する省略可能なパラメーターの引数を渡します。</span><span class="sxs-lookup"><span data-stu-id="b4f43-113">One supplies an argument for an optional parameter that specifies the type of the range value.</span></span> <span data-ttu-id="b4f43-114">そしてもう 1 つのパラメーターで、`Value` プロパティの値を渡します。</span><span class="sxs-lookup"><span data-stu-id="b4f43-114">The other supplies the value for the `Value` property.</span></span> <span data-ttu-id="b4f43-115">次の例は、これらの方法を示したものです。</span><span class="sxs-lookup"><span data-stu-id="b4f43-115">The following examples illustrate these techniques.</span></span> <span data-ttu-id="b4f43-116">どちらも、セル A1 の値を `Name` に設定しています。</span><span class="sxs-lookup"><span data-stu-id="b4f43-116">Both set the value of the A1 cell to `Name`.</span></span>
  
 [!code-csharp[csProgGuideIndexedProperties#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#3)]  
  
 <span data-ttu-id="b4f43-117">インデックス付きプロパティを使うと、次のようなコードを記述できます。</span><span class="sxs-lookup"><span data-stu-id="b4f43-117">Indexed properties enable you to write the following code instead.</span></span>  
  
 [!code-csharp[csProgGuideIndexedProperties#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#4)]  
  
 <span data-ttu-id="b4f43-118">独自のインデックス付きプロパティを作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="b4f43-118">You cannot create indexed properties of your own.</span></span> <span data-ttu-id="b4f43-119">この機能では、既存のインデックス付きプロパティの使用のみがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="b4f43-119">The feature only supports consumption of existing indexed properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b4f43-120">例</span><span class="sxs-lookup"><span data-stu-id="b4f43-120">Example</span></span>  
 <span data-ttu-id="b4f43-121">次に完全なコードの例を示します。</span><span class="sxs-lookup"><span data-stu-id="b4f43-121">The following code shows a complete example.</span></span> <span data-ttu-id="b4f43-122">Office API にアクセスするプロジェクトを設定する方法の詳細については、「[C# の機能を使用して Office 相互運用オブジェクトにアクセスする方法](./how-to-access-office-onterop-objects.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b4f43-122">For more information about how to set up a project that accesses the Office API, see [How to access Office interop objects by using C# features](./how-to-access-office-onterop-objects.md).</span></span>
  
 [!code-csharp[csProgGuideIndexedProperties#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#5)]  
  
## <a name="see-also"></a><span data-ttu-id="b4f43-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="b4f43-123">See also</span></span>

- [<span data-ttu-id="b4f43-124">名前付き引数と省略可能な引数</span><span class="sxs-lookup"><span data-stu-id="b4f43-124">Named and Optional Arguments</span></span>](../classes-and-structs/named-and-optional-arguments.md)
- [<span data-ttu-id="b4f43-125">dynamic</span><span class="sxs-lookup"><span data-stu-id="b4f43-125">dynamic</span></span>](../../language-reference/builtin-types/reference-types.md)
- [<span data-ttu-id="b4f43-126">dynamic 型の使用</span><span class="sxs-lookup"><span data-stu-id="b4f43-126">Using Type dynamic</span></span>](../types/using-type-dynamic.md)
- [<span data-ttu-id="b4f43-127">Office プログラミングで名前付き引数と省略可能な引数を使用する方法</span><span class="sxs-lookup"><span data-stu-id="b4f43-127">How to use named and optional arguments in Office programming</span></span>](../classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md)
- [<span data-ttu-id="b4f43-128">C# の機能を使用して Office 相互運用オブジェクトにアクセスする方法</span><span class="sxs-lookup"><span data-stu-id="b4f43-128">How to access Office interop objects by using C# features</span></span>](./how-to-access-office-onterop-objects.md)
- [<span data-ttu-id="b4f43-129">チュートリアル: Office プログラミング</span><span class="sxs-lookup"><span data-stu-id="b4f43-129">Walkthrough: Office Programming</span></span>](./walkthrough-office-programming.md)
