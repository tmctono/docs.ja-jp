---
title: XML ファイルの処理
ms.date: 07/20/2015
helpviewer_keywords:
- XML comments [Visual Basic], parsing [Visual Basic]
ms.assetid: 78a15cd0-7708-4e79-85d1-c154b7a14a8c
ms.openlocfilehash: 4230fd88b4b60c631135f5b7fb15f4b6272b5351
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347299"
---
# <a name="processing-the-xml-file-visual-basic"></a><span data-ttu-id="18dd7-102">XML ファイルの処理 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="18dd7-102">Processing the XML File (Visual Basic)</span></span>
<span data-ttu-id="18dd7-103">コンパイラは、ドキュメントを生成するためにタグ付けされたコードのコンストラクトごとに、ID 文字列を生成します。</span><span class="sxs-lookup"><span data-stu-id="18dd7-103">The compiler generates an ID string for each construct in your code that is tagged to generate documentation.</span></span> <span data-ttu-id="18dd7-104">(コードにタグを付ける方法については、「 [XML コメントタグ](../../../visual-basic/language-reference/xmldoc/index.md)」を参照してください)。ID 文字列は、コンストラクトを一意に識別します。</span><span class="sxs-lookup"><span data-stu-id="18dd7-104">(For information on how to tag your code, see [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/index.md).) The ID string uniquely identifies the construct.</span></span> <span data-ttu-id="18dd7-105">XML ファイルを処理するプログラムでは、ID 文字列を使用して、対応する .NET Framework メタデータ/リフレクション項目を識別できます。</span><span class="sxs-lookup"><span data-stu-id="18dd7-105">Programs that process the XML file can use the ID string to identify the corresponding .NET Framework metadata/reflection item.</span></span>  
  
 <span data-ttu-id="18dd7-106">XML ファイルは、コードの階層的な表現ではありません。これは、要素ごとに生成された ID を持つ単純なリストです。</span><span class="sxs-lookup"><span data-stu-id="18dd7-106">The XML file is not a hierarchical representation of your code; it is a flat list with a generated ID for each element.</span></span>  
  
 <span data-ttu-id="18dd7-107">コンパイラは、次の規則に基づいて ID 文字列を生成します。</span><span class="sxs-lookup"><span data-stu-id="18dd7-107">The compiler observes the following rules when it generates the ID strings:</span></span>  
  
- <span data-ttu-id="18dd7-108">文字列に空白は配置されません。</span><span class="sxs-lookup"><span data-stu-id="18dd7-108">No white space is placed in the string.</span></span>  
  
- <span data-ttu-id="18dd7-109">ID 文字列の最初の部分は、単一の文字とそれに続くコロンで識別されるメンバーの種類を示します。</span><span class="sxs-lookup"><span data-stu-id="18dd7-109">The first part of the ID string identifies the kind of member being identified, with a single character followed by a colon.</span></span> <span data-ttu-id="18dd7-110">次のメンバーの種類が使用されます。</span><span class="sxs-lookup"><span data-stu-id="18dd7-110">The following member types are used.</span></span>  
  
|<span data-ttu-id="18dd7-111">文字</span><span class="sxs-lookup"><span data-stu-id="18dd7-111">Character</span></span>|<span data-ttu-id="18dd7-112">説明</span><span class="sxs-lookup"><span data-stu-id="18dd7-112">Description</span></span>|  
|---|---|  
|<span data-ttu-id="18dd7-113">N</span><span class="sxs-lookup"><span data-stu-id="18dd7-113">N</span></span>|<span data-ttu-id="18dd7-114">namespace</span><span class="sxs-lookup"><span data-stu-id="18dd7-114">namespace</span></span><br /><br /> <span data-ttu-id="18dd7-115">ドキュメントのコメントを名前空間に追加することはできませんが、サポートされている場合には CREF 参照を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="18dd7-115">You cannot add documentation comments to a namespace, but you can make CREF references to them, where supported.</span></span>|  
|<span data-ttu-id="18dd7-116">T</span><span class="sxs-lookup"><span data-stu-id="18dd7-116">T</span></span>|<span data-ttu-id="18dd7-117">種類: `Class`、`Module`、`Interface`、`Structure`、`Enum`、`Delegate`</span><span class="sxs-lookup"><span data-stu-id="18dd7-117">type: `Class`, `Module`, `Interface`, `Structure`, `Enum`, `Delegate`</span></span>|  
|<span data-ttu-id="18dd7-118">F</span><span class="sxs-lookup"><span data-stu-id="18dd7-118">F</span></span>|<span data-ttu-id="18dd7-119">フィールド: `Dim`</span><span class="sxs-lookup"><span data-stu-id="18dd7-119">field: `Dim`</span></span>|  
|<span data-ttu-id="18dd7-120">P</span><span class="sxs-lookup"><span data-stu-id="18dd7-120">P</span></span>|<span data-ttu-id="18dd7-121">プロパティ: `Property` (既定のプロパティを含む)</span><span class="sxs-lookup"><span data-stu-id="18dd7-121">property: `Property` (including default properties)</span></span>|  
|<span data-ttu-id="18dd7-122">M</span><span class="sxs-lookup"><span data-stu-id="18dd7-122">M</span></span>|<span data-ttu-id="18dd7-123">方法: `Sub`、`Function`、`Declare`、`Operator`</span><span class="sxs-lookup"><span data-stu-id="18dd7-123">method: `Sub`, `Function`, `Declare`, `Operator`</span></span>|  
|<span data-ttu-id="18dd7-124">E</span><span class="sxs-lookup"><span data-stu-id="18dd7-124">E</span></span>|<span data-ttu-id="18dd7-125">イベント: `Event`</span><span class="sxs-lookup"><span data-stu-id="18dd7-125">event: `Event`</span></span>|  
|<span data-ttu-id="18dd7-126">!</span><span class="sxs-lookup"><span data-stu-id="18dd7-126">!</span></span>|<span data-ttu-id="18dd7-127">エラー文字列</span><span class="sxs-lookup"><span data-stu-id="18dd7-127">error string</span></span><br /><br /> <span data-ttu-id="18dd7-128">あとに続く文字列で、エラーの情報を示します。</span><span class="sxs-lookup"><span data-stu-id="18dd7-128">The rest of the string provides information about the error.</span></span> <span data-ttu-id="18dd7-129">Visual Basic コンパイラは、解決できないリンクのエラー情報を生成します。</span><span class="sxs-lookup"><span data-stu-id="18dd7-129">The Visual Basic compiler generates error information for links that cannot be resolved.</span></span>|  
  
- <span data-ttu-id="18dd7-130">`String` の2番目の部分は、名前空間のルートから開始する項目の完全修飾名です。</span><span class="sxs-lookup"><span data-stu-id="18dd7-130">The second part of the `String` is the fully qualified name of the item, starting at the root of the namespace.</span></span> <span data-ttu-id="18dd7-131">項目の名前、それを囲む型、および名前空間は、ピリオドで区切られます。</span><span class="sxs-lookup"><span data-stu-id="18dd7-131">The name of the item, its enclosing type(s), and the namespace are separated by periods.</span></span> <span data-ttu-id="18dd7-132">アイテム自体の名前にピリオドが含まれている場合、それらはシャープ記号 (#) で置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="18dd7-132">If the name of the item itself contains periods, they are replaced by the number sign (#).</span></span> <span data-ttu-id="18dd7-133">名前に番号記号が付いている項目がないことを前提としています。</span><span class="sxs-lookup"><span data-stu-id="18dd7-133">It is assumed that no item has a number sign directly in its name.</span></span> <span data-ttu-id="18dd7-134">たとえば、`String` コンストラクターの完全修飾名は `System.String.#ctor`ます。</span><span class="sxs-lookup"><span data-stu-id="18dd7-134">For example, the fully qualified name of the `String` constructor would be `System.String.#ctor`.</span></span>  
  
- <span data-ttu-id="18dd7-135">プロパティおよびメソッドについては、メソッドに引数がある場合は、引数のリストをかっこで囲み、メソッドに続けて指定します。</span><span class="sxs-lookup"><span data-stu-id="18dd7-135">For properties and methods, if there are arguments to the method, the argument list enclosed in parentheses follows.</span></span> <span data-ttu-id="18dd7-136">引数がない場合は、かっこはありません。</span><span class="sxs-lookup"><span data-stu-id="18dd7-136">If there are no arguments, no parentheses are present.</span></span> <span data-ttu-id="18dd7-137">引数はコンマで区切られます。</span><span class="sxs-lookup"><span data-stu-id="18dd7-137">The arguments are separated by commas.</span></span> <span data-ttu-id="18dd7-138">各引数のエンコーディングは、.NET Framework シグネチャでのエンコード方法に直接従います。</span><span class="sxs-lookup"><span data-stu-id="18dd7-138">The encoding of each argument follows directly how it is encoded in a .NET Framework signature.</span></span>  
  
## <a name="example"></a><span data-ttu-id="18dd7-139">例</span><span class="sxs-lookup"><span data-stu-id="18dd7-139">Example</span></span>  
 <span data-ttu-id="18dd7-140">次のコードは、クラスとそのメンバーの ID 文字列が生成される方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="18dd7-140">The following code shows how the ID strings for a class and its members are generated.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="18dd7-141">参照</span><span class="sxs-lookup"><span data-stu-id="18dd7-141">See also</span></span>

- [<span data-ttu-id="18dd7-142">-doc</span><span class="sxs-lookup"><span data-stu-id="18dd7-142">-doc</span></span>](../../../visual-basic/reference/command-line-compiler/doc.md)
- [<span data-ttu-id="18dd7-143">方法: XML ドキュメントを作成する</span><span class="sxs-lookup"><span data-stu-id="18dd7-143">How to: Create XML Documentation</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
