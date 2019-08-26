---
title: '方法: COM 相互運用機能を使用したプログラミングでインデックス付きプロパティを使用する - C# プログラミング ガイド'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- indexed properties [C#]
- Office programming [C#], indexed properties
- properties [C#], indexed
ms.assetid: 756bfc1e-7c28-4d4d-b114-ac9288c73882
ms.openlocfilehash: c39b9a313d265187605d51a2c78c7d3d3dcdb056
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923912"
---
# <a name="how-to-use-indexed-properties-in-com-interop-programming-c-programming-guide"></a><span data-ttu-id="26aaa-102">方法: COM 相互運用機能を使用したプログラミングでインデックス付きプロパティを使用する (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="26aaa-102">How to: Use Indexed Properties in COM Interop Programming (C# Programming Guide)</span></span>
<span data-ttu-id="26aaa-103">"*インデックス付きプロパティ*" により、パラメーターを持つ COM プロパティが C# プログラミングでいっそう使いやすくなります。</span><span class="sxs-lookup"><span data-stu-id="26aaa-103">*Indexed properties* improve the way in which COM properties that have parameters are consumed in C# programming.</span></span> <span data-ttu-id="26aaa-104">インデックス付きプロパティは、[名前付き引数と省略可能な引数](../classes-and-structs/named-and-optional-arguments.md)、新しい型 ([dynamic](../../language-reference/keywords/dynamic.md))、[埋め込み型情報](../concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-visual-studio.md)などの Visual C# の他の機能と連携して、Microsoft Office プログラミングをいっそう強力なものにします。</span><span class="sxs-lookup"><span data-stu-id="26aaa-104">Indexed properties work together with other features in Visual C#, such as [named and optional arguments](../classes-and-structs/named-and-optional-arguments.md), a new type ([dynamic](../../language-reference/keywords/dynamic.md)), and [embedded type information](../concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-visual-studio.md), to enhance Microsoft Office programming.</span></span>  
  
 <span data-ttu-id="26aaa-105">以前のバージョンの C# では、プロパティとしてメソッドにアクセスできるのは、`get` メソッドがパラメーターを持たず、`set` メソッドが 1 つだけ値パラメーターを持つ場合に限られました。</span><span class="sxs-lookup"><span data-stu-id="26aaa-105">In earlier versions of C#, methods are accessible as properties only if the `get` method has no parameters and the `set` method has one and only one value parameter.</span></span> <span data-ttu-id="26aaa-106">しかし、すべての COM プロパティがこのような制限を満たしているわけではありません。</span><span class="sxs-lookup"><span data-stu-id="26aaa-106">However, not all COM properties meet those restrictions.</span></span> <span data-ttu-id="26aaa-107">たとえば、Excel の <xref:Microsoft.Office.Interop.Excel.Range.Range%2A> プロパティには、範囲の名前のパラメーターを必要とする `get` アクセサーがあります。</span><span class="sxs-lookup"><span data-stu-id="26aaa-107">For example, the Excel <xref:Microsoft.Office.Interop.Excel.Range.Range%2A> property has a `get` accessor that requires a parameter for the name of the range.</span></span> <span data-ttu-id="26aaa-108">これまでは、このような `Range` プロパティに直接アクセスすることはできず、次の例に示すように、`get_Range` メソッドを代わりに使う必要がありました。</span><span class="sxs-lookup"><span data-stu-id="26aaa-108">In the past, because you could not access the `Range` property directly, you had to use the `get_Range` method instead, as shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideIndexedProperties#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#1)]  
  
 <span data-ttu-id="26aaa-109">インデックス付きプロパティを使うと、次のようなコードを記述できます。</span><span class="sxs-lookup"><span data-stu-id="26aaa-109">Indexed properties enable you to write the following instead:</span></span>  
  
 [!code-csharp[csProgGuideIndexedProperties#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#2)]  
  
> [!NOTE]
> <span data-ttu-id="26aaa-110">また、前の例では、[省略可能な引数](../classes-and-structs/named-and-optional-arguments.md)機能も使われており、`Type.Missing` を省略できます。</span><span class="sxs-lookup"><span data-stu-id="26aaa-110">The previous example also uses the [optional arguments](../classes-and-structs/named-and-optional-arguments.md) feature, which enables you to omit `Type.Missing`.</span></span>  
  
 <span data-ttu-id="26aaa-111">C# 3.0 以前で <xref:Microsoft.Office.Interop.Excel.Range> オブジェクトの `Value` プロパティの値を設定する場合と同様に、2 つの引数が必要です。</span><span class="sxs-lookup"><span data-stu-id="26aaa-111">Similarly to set the value of the `Value` property of a <xref:Microsoft.Office.Interop.Excel.Range> object in C# 3.0 and earlier, two arguments are required.</span></span> <span data-ttu-id="26aaa-112">1 つのパラメーターでは、範囲の値の型を指定する省略可能なパラメーターの引数を渡します。</span><span class="sxs-lookup"><span data-stu-id="26aaa-112">One supplies an argument for an optional parameter that specifies the type of the range value.</span></span> <span data-ttu-id="26aaa-113">そしてもう 1 つのパラメーターで、`Value` プロパティの値を渡します。</span><span class="sxs-lookup"><span data-stu-id="26aaa-113">The other supplies the value for the `Value` property.</span></span> <span data-ttu-id="26aaa-114">次の例は、これらの方法を示したものです。</span><span class="sxs-lookup"><span data-stu-id="26aaa-114">The following examples illustrate these techniques.</span></span> <span data-ttu-id="26aaa-115">どちらも、セル A1 の値を `Name` に設定しています。</span><span class="sxs-lookup"><span data-stu-id="26aaa-115">Both set the value of the A1 cell to `Name`.</span></span>
  
 [!code-csharp[csProgGuideIndexedProperties#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#3)]  
  
 <span data-ttu-id="26aaa-116">インデックス付きプロパティを使うと、次のようなコードを記述できます。</span><span class="sxs-lookup"><span data-stu-id="26aaa-116">Indexed properties enable you to write the following code instead.</span></span>  
  
 [!code-csharp[csProgGuideIndexedProperties#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#4)]  
  
 <span data-ttu-id="26aaa-117">独自のインデックス付きプロパティを作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="26aaa-117">You cannot create indexed properties of your own.</span></span> <span data-ttu-id="26aaa-118">この機能では、既存のインデックス付きプロパティの使用のみがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="26aaa-118">The feature only supports consumption of existing indexed properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="26aaa-119">例</span><span class="sxs-lookup"><span data-stu-id="26aaa-119">Example</span></span>  
 <span data-ttu-id="26aaa-120">次に完全なコードの例を示します。</span><span class="sxs-lookup"><span data-stu-id="26aaa-120">The following code shows a complete example.</span></span> <span data-ttu-id="26aaa-121">Office API にアクセスするプロジェクトを設定する方法について詳しくは、「[方法: Visual C# の機能を使用して Office 相互運用オブジェクトにアクセスする](./how-to-access-office-onterop-objects.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="26aaa-121">For more information about how to set up a project that accesses the Office API, see [How to: Access Office Interop Objects by Using Visual C# Features](./how-to-access-office-onterop-objects.md).</span></span>  
  
 [!code-csharp[csProgGuideIndexedProperties#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#5)]  
  
## <a name="see-also"></a><span data-ttu-id="26aaa-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="26aaa-122">See also</span></span>

- [<span data-ttu-id="26aaa-123">名前付き引数と省略可能な引数</span><span class="sxs-lookup"><span data-stu-id="26aaa-123">Named and Optional Arguments</span></span>](../classes-and-structs/named-and-optional-arguments.md)
- [<span data-ttu-id="26aaa-124">dynamic</span><span class="sxs-lookup"><span data-stu-id="26aaa-124">dynamic</span></span>](../../language-reference/keywords/dynamic.md)
- [<span data-ttu-id="26aaa-125">dynamic 型の使用</span><span class="sxs-lookup"><span data-stu-id="26aaa-125">Using Type dynamic</span></span>](../types/using-type-dynamic.md)
- [<span data-ttu-id="26aaa-126">方法: Office プログラミングで名前付き引数と省略可能な引数を使用する</span><span class="sxs-lookup"><span data-stu-id="26aaa-126">How to: Use Named and Optional Arguments in Office Programming</span></span>](../classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md)
- [<span data-ttu-id="26aaa-127">方法: Visual C# の機能を使用して Office 相互運用オブジェクトにアクセスする</span><span class="sxs-lookup"><span data-stu-id="26aaa-127">How to: Access Office Interop Objects by Using Visual C# Features</span></span>](./how-to-access-office-onterop-objects.md)
- [<span data-ttu-id="26aaa-128">チュートリアル:Office プログラミング</span><span class="sxs-lookup"><span data-stu-id="26aaa-128">Walkthrough: Office Programming</span></span>](./walkthrough-office-programming.md)
