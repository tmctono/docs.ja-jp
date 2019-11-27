---
title: 参照と Imports ステートメント
ms.date: 07/20/2015
helpviewer_keywords:
- assemblies [Visual Basic], namespaces
- references [Visual Basic], assembly
- namespaces [Visual Basic], assemblies
- referencing assemblies
- Imports statement [Visual Basic], referencing assemblies
- assemblies [Visual Basic], references
ms.assetid: 38149bd4-0a6f-4b31-b5f8-94a8c33f1600
ms.openlocfilehash: 31b4fe001f2b8a62ac30488053c57cd186020421
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347273"
---
# <a name="references-and-the-imports-statement-visual-basic"></a><span data-ttu-id="e58a6-102">参照と Imports ステートメント (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e58a6-102">References and the Imports Statement (Visual Basic)</span></span>
<span data-ttu-id="e58a6-103">**[プロジェクト]** メニューの **[参照の追加]** をクリックして、プロジェクトで外部オブジェクトを使用できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="e58a6-103">You can make external objects available to your project by choosing the **Add Reference** command on the **Project** menu.</span></span> <span data-ttu-id="e58a6-104">Visual Basic の参照は、タイプライブラリのようなアセンブリを指すことができますが、さらに多くの情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e58a6-104">References in Visual Basic can point to assemblies, which are like type libraries but contain more information.</span></span>  
  
## <a name="the-imports-statement"></a><span data-ttu-id="e58a6-105">Imports ステートメント</span><span class="sxs-lookup"><span data-stu-id="e58a6-105">The Imports Statement</span></span>  
 <span data-ttu-id="e58a6-106">アセンブリには、1つまたは複数の名前空間が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e58a6-106">Assemblies include one or more namespaces.</span></span> <span data-ttu-id="e58a6-107">アセンブリへの参照を追加するときに、モジュール内のアセンブリの名前空間の表示を制御するモジュールに `Imports` ステートメントを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="e58a6-107">When you add a reference to an assembly, you can also add an `Imports` statement to a module that controls the visibility of that assembly's namespaces within the module.</span></span> <span data-ttu-id="e58a6-108">`Imports` ステートメントは、一意の参照を指定するために必要な名前空間の部分のみを使用できるようにするスコープコンテキストを提供します。</span><span class="sxs-lookup"><span data-stu-id="e58a6-108">The `Imports` statement provides a scoping context that lets you use only the portion of the namespace necessary to supply a unique reference.</span></span>  
  
 <span data-ttu-id="e58a6-109">`Imports` ステートメントには、次の構文があります。</span><span class="sxs-lookup"><span data-stu-id="e58a6-109">The `Imports` statement has the following syntax:</span></span>  
  
 `Imports [Aliasname =] Namespace`  
  
 <span data-ttu-id="e58a6-110">`Aliasname` は、インポートされた名前空間を参照するためにコード内で使用できる短い名前を表します。</span><span class="sxs-lookup"><span data-stu-id="e58a6-110">`Aliasname` refers to a short name you can use within code to refer to an imported namespace.</span></span> <span data-ttu-id="e58a6-111">`Namespace` は、プロジェクト参照、プロジェクト内の定義、または前の `Imports` ステートメントを通じて使用できる名前空間です。</span><span class="sxs-lookup"><span data-stu-id="e58a6-111">`Namespace` is a namespace available through either a project reference, through a definition within the project, or through a previous `Imports` statement.</span></span>  
  
 <span data-ttu-id="e58a6-112">モジュールには、任意の数の `Imports` ステートメントを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="e58a6-112">A module may contain any number of `Imports` statements.</span></span> <span data-ttu-id="e58a6-113">これらは、任意の `Option` ステートメント (存在する場合) の後、他のコードの前に記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e58a6-113">They must appear after any `Option` statements, if present, but before any other code.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e58a6-114">プロジェクト参照を `Imports` ステートメントまたは `Declare` ステートメントと混同しないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="e58a6-114">Do not confuse project references with the `Imports` statement or the `Declare` statement.</span></span> <span data-ttu-id="e58a6-115">プロジェクト参照は、アセンブリ内のオブジェクトなどの外部オブジェクトを、Visual Basic プロジェクトで使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="e58a6-115">Project references make external objects, such as objects in assemblies, available to Visual Basic projects.</span></span> <span data-ttu-id="e58a6-116">`Imports` ステートメントは、プロジェクト参照へのアクセスを簡略化するために使用されますが、これらのオブジェクトへのアクセスは提供されません。</span><span class="sxs-lookup"><span data-stu-id="e58a6-116">The `Imports` statement is used to simplify access to project references, but does not provide access to these objects.</span></span> <span data-ttu-id="e58a6-117">`Declare` ステートメントは、ダイナミックリンクライブラリ (DLL) 内の外部プロシージャへの参照を宣言するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="e58a6-117">The `Declare` statement is used to declare a reference to an external procedure in a dynamic-link library (DLL).</span></span>  
  
## <a name="using-aliases-with-the-imports-statement"></a><span data-ttu-id="e58a6-118">Imports ステートメントでの別名の使用</span><span class="sxs-lookup"><span data-stu-id="e58a6-118">Using Aliases with the Imports Statement</span></span>  
 <span data-ttu-id="e58a6-119">`Imports` ステートメントを使用すると、参照の完全修飾名を明示的に入力する必要がなくなるため、クラスのメソッドに簡単にアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="e58a6-119">The `Imports` statement makes it easier to access methods of classes by eliminating the need to explicitly type the fully qualified names of references.</span></span> <span data-ttu-id="e58a6-120">エイリアスを使用すると、名前空間の1つの部分のみにわかりやすい名前を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="e58a6-120">Aliases let you assign a friendlier name to just one part of a namespace.</span></span> <span data-ttu-id="e58a6-121">たとえば、1つのテキストが複数行に表示されるキャリッジリターン/ラインフィードシーケンスは、<xref:Microsoft.VisualBasic?displayProperty=nameWithType> 名前空間の <xref:Microsoft.VisualBasic.ControlChars> モジュールの一部として使用されます。</span><span class="sxs-lookup"><span data-stu-id="e58a6-121">For example, the carriage return/line feed sequence that causes a single piece of text to be displayed on multiple lines is part of the <xref:Microsoft.VisualBasic.ControlChars> module in the <xref:Microsoft.VisualBasic?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="e58a6-122">エイリアスのないプログラムでこの定数を使用するには、次のコードを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e58a6-122">To use this constant in a program without an alias, you would need to type the following code:</span></span>  
  
 [!code-vb[VbVbalrApplication#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#3)]  
  
 <span data-ttu-id="e58a6-123">`Imports` ステートメントは、常にモジュール内の `Option` ステートメントの直後の最初の行である必要があります。</span><span class="sxs-lookup"><span data-stu-id="e58a6-123">`Imports` statements must always be the first lines immediately following any `Option` statements in a module.</span></span> <span data-ttu-id="e58a6-124">次のコードフラグメントは、エイリアスをインポートして <xref:Microsoft.VisualBasic.ControlChars?displayProperty=nameWithType> モジュールに割り当てる方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="e58a6-124">The following code fragment shows how to import and assign an alias to the <xref:Microsoft.VisualBasic.ControlChars?displayProperty=nameWithType> module:</span></span>  
  
 [!code-vb[VbVbalrApplication#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#4)]  
  
 <span data-ttu-id="e58a6-125">この名前空間への今後の参照は、大幅に短縮される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e58a6-125">Future references to this namespace can be considerably shorter:</span></span>  
  
 [!code-vb[VbVbalrApplication#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#5)]  
  
 <span data-ttu-id="e58a6-126">`Imports` ステートメントにエイリアス名が含まれていない場合、インポートされた名前空間内で定義された要素は、修飾なしでモジュールで使用できます。</span><span class="sxs-lookup"><span data-stu-id="e58a6-126">If an `Imports` statement does not include an alias name, elements defined within the imported namespace can be used in the module without qualification.</span></span> <span data-ttu-id="e58a6-127">エイリアス名を指定する場合は、その名前空間内に含まれる名前の修飾子として使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e58a6-127">If the alias name is specified, it must be used as a qualifier for names contained within that namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e58a6-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="e58a6-128">See also</span></span>

- <xref:Microsoft.VisualBasic.ControlChars>
- <xref:Microsoft.VisualBasic>
- [<span data-ttu-id="e58a6-129">Visual Basic 内の名前空間</span><span class="sxs-lookup"><span data-stu-id="e58a6-129">Namespaces in Visual Basic</span></span>](namespaces.md)
- [<span data-ttu-id="e58a6-130">.NET のアセンブリ</span><span class="sxs-lookup"><span data-stu-id="e58a6-130">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
- [<span data-ttu-id="e58a6-131">Imports ステートメント (.NET 名前空間および型)</span><span class="sxs-lookup"><span data-stu-id="e58a6-131">Imports Statement (.NET Namespace and Type)</span></span>](../../language-reference/statements/imports-statement-net-namespace-and-type.md)
