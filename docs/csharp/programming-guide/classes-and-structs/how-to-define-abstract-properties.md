---
title: 抽象プロパティを定義する方法 - C# プログラミング ガイド
ms.date: 07/20/2015
helpviewer_keywords:
- properties [C#], abstract
- abstract properties [C#]
ms.assetid: 672a90eb-47b9-4ae0-9914-af53852fddcb
ms.openlocfilehash: c46f36133b68a550a17cf882844fd2481eee8851
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705614"
---
# <a name="how-to-define-abstract-properties-c-programming-guide"></a><span data-ttu-id="19ccd-102">抽象プロパティを定義する方法 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="19ccd-102">How to define abstract properties (C# Programming Guide)</span></span>
<span data-ttu-id="19ccd-103">次の例では、[抽象](../../language-reference/keywords/abstract.md)プロパティを定義する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="19ccd-103">The following example shows how to define [abstract](../../language-reference/keywords/abstract.md) properties.</span></span> <span data-ttu-id="19ccd-104">抽象プロパティの宣言では、プロパティ アクセサーは実装されません。クラスがプロパティをサポートしていることは宣言しますが、アクセサーの実装は派生クラスに委ねます。</span><span class="sxs-lookup"><span data-stu-id="19ccd-104">An abstract property declaration does not provide an implementation of the property accessors -- it declares that the class supports properties, but leaves the accessor implementation to derived classes.</span></span> <span data-ttu-id="19ccd-105">基本クラスから継承された抽象プロパティを実装する方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="19ccd-105">The following example demonstrates how to implement the abstract properties inherited from a base class.</span></span>  
  
 <span data-ttu-id="19ccd-106">このサンプルは 3 つのファイルで構成され、それぞれ個別にコンパイルされ、生成されたアセンブリが次のコンパイルで参照されます。</span><span class="sxs-lookup"><span data-stu-id="19ccd-106">This sample consists of three files, each of which is compiled individually and its resulting assembly is referenced by the next compilation:</span></span>  
  
- <span data-ttu-id="19ccd-107">abstractshape.cs: 抽象 `Shape` プロパティを含む `Area` クラス。</span><span class="sxs-lookup"><span data-stu-id="19ccd-107">abstractshape.cs: the `Shape` class that contains an abstract `Area` property.</span></span>  
  
- <span data-ttu-id="19ccd-108">shapes.cs:`Shape` クラスのサブクラス。</span><span class="sxs-lookup"><span data-stu-id="19ccd-108">shapes.cs: The subclasses of the `Shape` class.</span></span>  
  
- <span data-ttu-id="19ccd-109">shapetest.cs:`Shape` から派生したいくつかのオブジェクトの面積を表示するテスト プログラム。</span><span class="sxs-lookup"><span data-stu-id="19ccd-109">shapetest.cs: A test program to display the areas of some `Shape`-derived objects.</span></span>  
  
 <span data-ttu-id="19ccd-110">この例をコンパイルするには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="19ccd-110">To compile the example, use the following command:</span></span>  
  
 `csc abstractshape.cs shapes.cs shapetest.cs`  
  
 <span data-ttu-id="19ccd-111">これで、実行可能ファイル shapetest.exe が作成されます。</span><span class="sxs-lookup"><span data-stu-id="19ccd-111">This will create the executable file shapetest.exe.</span></span>  
  
## <a name="example"></a><span data-ttu-id="19ccd-112">例</span><span class="sxs-lookup"><span data-stu-id="19ccd-112">Example</span></span>  
 <span data-ttu-id="19ccd-113">このファイルは、`double` 型の `Shape` プロパティを含む `Area` クラスを宣言します。</span><span class="sxs-lookup"><span data-stu-id="19ccd-113">This file declares the `Shape` class that contains the `Area` property of the type `double`.</span></span>  
  
 [!code-csharp[csProgGuideInheritance#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#1)]  
  
- <span data-ttu-id="19ccd-114">プロパティの修飾子は、プロパティ宣言自体に設定されます。</span><span class="sxs-lookup"><span data-stu-id="19ccd-114">Modifiers on the property are placed on the property declaration itself.</span></span> <span data-ttu-id="19ccd-115">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="19ccd-115">For example:</span></span>  
  
    ```csharp  
    public abstract double Area  
    ```  
  
- <span data-ttu-id="19ccd-116">抽象プロパティ (この例では `Area` など) を宣言する場合は、使用可能なアクセサーを示すだけで、実装はしません。</span><span class="sxs-lookup"><span data-stu-id="19ccd-116">When declaring an abstract property (such as `Area` in this example), you simply indicate what property accessors are available, but do not implement them.</span></span> <span data-ttu-id="19ccd-117">この例では、[get](../../language-reference/keywords/get.md) アクセサーのみが使用可能であるため、プロパティは読み取り専用となります。</span><span class="sxs-lookup"><span data-stu-id="19ccd-117">In this example, only a [get](../../language-reference/keywords/get.md) accessor is available, so the property is read-only.</span></span>  
  
## <a name="example"></a><span data-ttu-id="19ccd-118">例</span><span class="sxs-lookup"><span data-stu-id="19ccd-118">Example</span></span>  
 <span data-ttu-id="19ccd-119">次のコードは、`Shape` の 3 つのサブクラスと、それらがどのように `Area` プロパティをオーバーライドして独自の実装を提供するかを示しています。</span><span class="sxs-lookup"><span data-stu-id="19ccd-119">The following code shows three subclasses of `Shape` and how they override the `Area` property to provide their own implementation.</span></span>  
  
 [!code-csharp[csProgGuideInheritance#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#2)]  
  
## <a name="example"></a><span data-ttu-id="19ccd-120">例</span><span class="sxs-lookup"><span data-stu-id="19ccd-120">Example</span></span>  
 <span data-ttu-id="19ccd-121">次のコードは、`Shape` から派生するオブジェクトをいくつか作成し、それらの面積を出力するテスト プログラムを示しています。</span><span class="sxs-lookup"><span data-stu-id="19ccd-121">The following code shows a test program that creates a number of `Shape`-derived objects and prints out their areas.</span></span>  
  
 [!code-csharp[csProgGuideInheritance#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#3)]  
  
## <a name="see-also"></a><span data-ttu-id="19ccd-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="19ccd-122">See also</span></span>

- [<span data-ttu-id="19ccd-123">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="19ccd-123">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="19ccd-124">クラスと構造体</span><span class="sxs-lookup"><span data-stu-id="19ccd-124">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="19ccd-125">抽象クラスとシール クラス、およびクラス メンバー</span><span class="sxs-lookup"><span data-stu-id="19ccd-125">Abstract and Sealed Classes and Class Members</span></span>](./abstract-and-sealed-classes-and-class-members.md)
- [<span data-ttu-id="19ccd-126">プロパティ</span><span class="sxs-lookup"><span data-stu-id="19ccd-126">Properties</span></span>](./properties.md)
