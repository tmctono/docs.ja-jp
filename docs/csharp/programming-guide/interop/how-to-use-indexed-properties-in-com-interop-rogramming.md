---
title: COM 相互運用機能を使用したプログラミングでインデックス付きプロパティを使用する方法 - C# プログラミング ガイド
ms.date: 07/20/2015
helpviewer_keywords:
- indexed properties [C#]
- Office programming [C#], indexed properties
- properties [C#], indexed
ms.assetid: 756bfc1e-7c28-4d4d-b114-ac9288c73882
ms.openlocfilehash: 864e2274f0e0e79b4843e0bb67b5c4384eac8588
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712066"
---
# <a name="how-to-use-indexed-properties-in-com-interop-programming-c-programming-guide"></a><span data-ttu-id="89793-102">COM 相互運用機能を使用したプログラミングでインデックス付きプロパティを使用する方法 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="89793-102">How to use indexed properties in COM interop programming (C# Programming Guide)</span></span>
<span data-ttu-id="89793-103">"*インデックス付きプロパティ*" により、パラメーターを持つ COM プロパティが C# プログラミングでいっそう使いやすくなります。</span><span class="sxs-lookup"><span data-stu-id="89793-103">*Indexed properties* improve the way in which COM properties that have parameters are consumed in C# programming.</span></span> <span data-ttu-id="89793-104">インデックス付きプロパティは、[名前付き引数と省略可能な引数](../classes-and-structs/named-and-optional-arguments.md)、新しい型 ([dynamic](../../language-reference/builtin-types/reference-types.md))、[埋め込み型情報](../../../standard/assembly/embed-types-visual-studio.md)などの Visual C# の他の機能と連携して、Microsoft Office プログラミングをいっそう強力なものにします。</span><span class="sxs-lookup"><span data-stu-id="89793-104">Indexed properties work together with other features in Visual C#, such as [named and optional arguments](../classes-and-structs/named-and-optional-arguments.md), a new type ([dynamic](../../language-reference/builtin-types/reference-types.md)), and [embedded type information](../../../standard/assembly/embed-types-visual-studio.md), to enhance Microsoft Office programming.</span></span>  
  
 <span data-ttu-id="89793-105">以前のバージョンの C# では、プロパティとしてメソッドにアクセスできるのは、`get` メソッドがパラメーターを持たず、`set` メソッドが 1 つだけ値パラメーターを持つ場合に限られました。</span><span class="sxs-lookup"><span data-stu-id="89793-105">In earlier versions of C#, methods are accessible as properties only if the `get` method has no parameters and the `set` method has one and only one value parameter.</span></span> <span data-ttu-id="89793-106">しかし、すべての COM プロパティがこのような制限を満たしているわけではありません。</span><span class="sxs-lookup"><span data-stu-id="89793-106">However, not all COM properties meet those restrictions.</span></span> <span data-ttu-id="89793-107">たとえば、Excel の <xref:Microsoft.Office.Interop.Excel.Range.Range%2A> プロパティには、範囲の名前のパラメーターを必要とする `get` アクセサーがあります。</span><span class="sxs-lookup"><span data-stu-id="89793-107">For example, the Excel <xref:Microsoft.Office.Interop.Excel.Range.Range%2A> property has a `get` accessor that requires a parameter for the name of the range.</span></span> <span data-ttu-id="89793-108">これまでは、このような `Range` プロパティに直接アクセスすることはできず、次の例に示すように、`get_Range` メソッドを代わりに使う必要がありました。</span><span class="sxs-lookup"><span data-stu-id="89793-108">In the past, because you could not access the `Range` property directly, you had to use the `get_Range` method instead, as shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideIndexedProperties#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#1)]  
  
 <span data-ttu-id="89793-109">インデックス付きプロパティを使うと、次のようなコードを記述できます。</span><span class="sxs-lookup"><span data-stu-id="89793-109">Indexed properties enable you to write the following instead:</span></span>  
  
 [!code-csharp[csProgGuideIndexedProperties#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#2)]  
  
> [!NOTE]
> <span data-ttu-id="89793-110">また、前の例では、[省略可能な引数](../classes-and-structs/named-and-optional-arguments.md)機能も使われており、`Type.Missing` を省略できます。</span><span class="sxs-lookup"><span data-stu-id="89793-110">The previous example also uses the [optional arguments](../classes-and-structs/named-and-optional-arguments.md) feature, which enables you to omit `Type.Missing`.</span></span>  
  
 <span data-ttu-id="89793-111">C# 3.0 以前で <xref:Microsoft.Office.Interop.Excel.Range> オブジェクトの `Value` プロパティの値を設定する場合と同様に、2 つの引数が必要です。</span><span class="sxs-lookup"><span data-stu-id="89793-111">Similarly to set the value of the `Value` property of a <xref:Microsoft.Office.Interop.Excel.Range> object in C# 3.0 and earlier, two arguments are required.</span></span> <span data-ttu-id="89793-112">1 つのパラメーターでは、範囲の値の型を指定する省略可能なパラメーターの引数を渡します。</span><span class="sxs-lookup"><span data-stu-id="89793-112">One supplies an argument for an optional parameter that specifies the type of the range value.</span></span> <span data-ttu-id="89793-113">そしてもう 1 つのパラメーターで、`Value` プロパティの値を渡します。</span><span class="sxs-lookup"><span data-stu-id="89793-113">The other supplies the value for the `Value` property.</span></span> <span data-ttu-id="89793-114">次の例は、これらの方法を示したものです。</span><span class="sxs-lookup"><span data-stu-id="89793-114">The following examples illustrate these techniques.</span></span> <span data-ttu-id="89793-115">どちらも、セル A1 の値を `Name` に設定しています。</span><span class="sxs-lookup"><span data-stu-id="89793-115">Both set the value of the A1 cell to `Name`.</span></span>
  
 [!code-csharp[csProgGuideIndexedProperties#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#3)]  
  
 <span data-ttu-id="89793-116">インデックス付きプロパティを使うと、次のようなコードを記述できます。</span><span class="sxs-lookup"><span data-stu-id="89793-116">Indexed properties enable you to write the following code instead.</span></span>  
  
 [!code-csharp[csProgGuideIndexedProperties#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#4)]  
  
 <span data-ttu-id="89793-117">独自のインデックス付きプロパティを作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="89793-117">You cannot create indexed properties of your own.</span></span> <span data-ttu-id="89793-118">この機能では、既存のインデックス付きプロパティの使用のみがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="89793-118">The feature only supports consumption of existing indexed properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="89793-119">例</span><span class="sxs-lookup"><span data-stu-id="89793-119">Example</span></span>  
 <span data-ttu-id="89793-120">次に完全なコードの例を示します。</span><span class="sxs-lookup"><span data-stu-id="89793-120">The following code shows a complete example.</span></span> <span data-ttu-id="89793-121">Office API にアクセスするプロジェクトを設定する方法の詳細については、「[C# の機能を使用して Office 相互運用オブジェクトにアクセスする方法](./how-to-access-office-onterop-objects.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="89793-121">For more information about how to set up a project that accesses the Office API, see [How to access Office interop objects by using C# features](./how-to-access-office-onterop-objects.md).</span></span>
  
 [!code-csharp[csProgGuideIndexedProperties#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#5)]  
  
## <a name="see-also"></a><span data-ttu-id="89793-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="89793-122">See also</span></span>

- [<span data-ttu-id="89793-123">名前付き引数と省略可能な引数</span><span class="sxs-lookup"><span data-stu-id="89793-123">Named and Optional Arguments</span></span>](../classes-and-structs/named-and-optional-arguments.md)
- [<span data-ttu-id="89793-124">dynamic</span><span class="sxs-lookup"><span data-stu-id="89793-124">dynamic</span></span>](../../language-reference/builtin-types/reference-types.md)
- [<span data-ttu-id="89793-125">dynamic 型の使用</span><span class="sxs-lookup"><span data-stu-id="89793-125">Using Type dynamic</span></span>](../types/using-type-dynamic.md)
- [<span data-ttu-id="89793-126">Office プログラミングで名前付き引数と省略可能な引数を使用する方法</span><span class="sxs-lookup"><span data-stu-id="89793-126">How to use named and optional arguments in Office programming</span></span>](../classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md)
- [<span data-ttu-id="89793-127">C# の機能を使用して Office 相互運用オブジェクトにアクセスする方法</span><span class="sxs-lookup"><span data-stu-id="89793-127">How to access Office interop objects by using C# features</span></span>](./how-to-access-office-onterop-objects.md)
- [<span data-ttu-id="89793-128">チュートリアル: Office プログラミング</span><span class="sxs-lookup"><span data-stu-id="89793-128">Walkthrough: Office Programming</span></span>](./walkthrough-office-programming.md)
