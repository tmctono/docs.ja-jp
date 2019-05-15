---
title: '方法: 抽象プロパティを定義する - C# プログラミング ガイド'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- properties [C#], abstract
- abstract properties [C#]
ms.assetid: 672a90eb-47b9-4ae0-9914-af53852fddcb
ms.openlocfilehash: ef19b80e7f4c32830aabfcf1ad595348c2107228
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64599981"
---
# <a name="how-to-define-abstract-properties-c-programming-guide"></a><span data-ttu-id="a9168-102">方法: 抽象プロパティを定義する (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="a9168-102">How to: Define Abstract Properties (C# Programming Guide)</span></span>
<span data-ttu-id="a9168-103">次の例では、[抽象](../../../csharp/language-reference/keywords/abstract.md)プロパティを定義する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a9168-103">The following example shows how to define [abstract](../../../csharp/language-reference/keywords/abstract.md) properties.</span></span> <span data-ttu-id="a9168-104">抽象プロパティの宣言では、プロパティ アクセサーは実装されません。クラスがプロパティをサポートしていることは宣言しますが、アクセサーの実装は派生クラスに委ねます。</span><span class="sxs-lookup"><span data-stu-id="a9168-104">An abstract property declaration does not provide an implementation of the property accessors -- it declares that the class supports properties, but leaves the accessor implementation to derived classes.</span></span> <span data-ttu-id="a9168-105">基本クラスから継承された抽象プロパティを実装する方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="a9168-105">The following example demonstrates how to implement the abstract properties inherited from a base class.</span></span>  
  
 <span data-ttu-id="a9168-106">このサンプルは 3 つのファイルで構成され、それぞれ個別にコンパイルされ、生成されたアセンブリが次のコンパイルで参照されます。</span><span class="sxs-lookup"><span data-stu-id="a9168-106">This sample consists of three files, each of which is compiled individually and its resulting assembly is referenced by the next compilation:</span></span>  
  
- <span data-ttu-id="a9168-107">abstractshape.cs: 抽象 `Shape` プロパティを含む `Area` クラス。</span><span class="sxs-lookup"><span data-stu-id="a9168-107">abstractshape.cs: the `Shape` class that contains an abstract `Area` property.</span></span>  
  
- <span data-ttu-id="a9168-108">shapes.cs:`Shape` クラスのサブクラス。</span><span class="sxs-lookup"><span data-stu-id="a9168-108">shapes.cs: The subclasses of the `Shape` class.</span></span>  
  
- <span data-ttu-id="a9168-109">shapetest.cs:`Shape` から派生したいくつかのオブジェクトの面積を表示するテスト プログラム。</span><span class="sxs-lookup"><span data-stu-id="a9168-109">shapetest.cs: A test program to display the areas of some `Shape`-derived objects.</span></span>  
  
 <span data-ttu-id="a9168-110">この例をコンパイルするには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="a9168-110">To compile the example, use the following command:</span></span>  
  
 `csc abstractshape.cs shapes.cs shapetest.cs`  
  
 <span data-ttu-id="a9168-111">これで、実行可能ファイル shapetest.exe が作成されます。</span><span class="sxs-lookup"><span data-stu-id="a9168-111">This will create the executable file shapetest.exe.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a9168-112">例</span><span class="sxs-lookup"><span data-stu-id="a9168-112">Example</span></span>  
 <span data-ttu-id="a9168-113">このファイルは、`double` 型の `Shape` プロパティを含む `Area` クラスを宣言します。</span><span class="sxs-lookup"><span data-stu-id="a9168-113">This file declares the `Shape` class that contains the `Area` property of the type `double`.</span></span>  
  
 [!code-csharp[csProgGuideInheritance#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#1)]  
  
- <span data-ttu-id="a9168-114">プロパティの修飾子は、プロパティ宣言自体に設定されます。</span><span class="sxs-lookup"><span data-stu-id="a9168-114">Modifiers on the property are placed on the property declaration itself.</span></span> <span data-ttu-id="a9168-115">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="a9168-115">For example:</span></span>  
  
    ```csharp  
    public abstract double Area  
    ```  
  
- <span data-ttu-id="a9168-116">抽象プロパティ (この例では `Area` など) を宣言する場合は、使用可能なアクセサーを示すだけで、実装はしません。</span><span class="sxs-lookup"><span data-stu-id="a9168-116">When declaring an abstract property (such as `Area` in this example), you simply indicate what property accessors are available, but do not implement them.</span></span> <span data-ttu-id="a9168-117">この例では、[get](../../../csharp/language-reference/keywords/get.md) アクセサーのみが使用可能であるため、プロパティは読み取り専用となります。</span><span class="sxs-lookup"><span data-stu-id="a9168-117">In this example, only a [get](../../../csharp/language-reference/keywords/get.md) accessor is available, so the property is read-only.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a9168-118">例</span><span class="sxs-lookup"><span data-stu-id="a9168-118">Example</span></span>  
 <span data-ttu-id="a9168-119">次のコードは、`Shape` の 3 つのサブクラスと、それらがどのように `Area` プロパティをオーバーライドして独自の実装を提供するかを示しています。</span><span class="sxs-lookup"><span data-stu-id="a9168-119">The following code shows three subclasses of `Shape` and how they override the `Area` property to provide their own implementation.</span></span>  
  
 [!code-csharp[csProgGuideInheritance#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#2)]  
  
## <a name="example"></a><span data-ttu-id="a9168-120">例</span><span class="sxs-lookup"><span data-stu-id="a9168-120">Example</span></span>  
 <span data-ttu-id="a9168-121">次のコードは、`Shape` から派生するオブジェクトをいくつか作成し、それらの面積を出力するテスト プログラムを示しています。</span><span class="sxs-lookup"><span data-stu-id="a9168-121">The following code shows a test program that creates a number of `Shape`-derived objects and prints out their areas.</span></span>  
  
 [!code-csharp[csProgGuideInheritance#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#3)]  
  
## <a name="see-also"></a><span data-ttu-id="a9168-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="a9168-122">See also</span></span>

- [<span data-ttu-id="a9168-123">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="a9168-123">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="a9168-124">クラスと構造体</span><span class="sxs-lookup"><span data-stu-id="a9168-124">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)
- [<span data-ttu-id="a9168-125">抽象クラスとシール クラス、およびクラス メンバー</span><span class="sxs-lookup"><span data-stu-id="a9168-125">Abstract and Sealed Classes and Class Members</span></span>](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md)
- [<span data-ttu-id="a9168-126">プロパティ</span><span class="sxs-lookup"><span data-stu-id="a9168-126">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/properties.md)
- [<span data-ttu-id="a9168-127">方法: コマンド ラインを使用してアセンブリを作成および使用する</span><span class="sxs-lookup"><span data-stu-id="a9168-127">How to: Create and Use Assemblies Using the Command Line</span></span>](../concepts/assemblies-gac/how-to-create-and-use-assemblies-using-the-command-line.md)
