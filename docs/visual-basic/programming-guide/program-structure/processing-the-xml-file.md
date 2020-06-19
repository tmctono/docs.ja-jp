---
title: XML ファイルの処理
ms.date: 07/20/2015
helpviewer_keywords:
- XML comments [Visual Basic], parsing [Visual Basic]
ms.assetid: 78a15cd0-7708-4e79-85d1-c154b7a14a8c
ms.openlocfilehash: 81d2c8d305e828b2963a0af9d97ec35b1745197a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84398332"
---
# <a name="processing-the-xml-file-visual-basic"></a><span data-ttu-id="8eb93-102">XML ファイルの処理 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8eb93-102">Processing the XML File (Visual Basic)</span></span>
<span data-ttu-id="8eb93-103">コンパイラは、ドキュメントを生成するためにタグ付けされたコードのコンストラクトごとに、ID 文字列を生成します。</span><span class="sxs-lookup"><span data-stu-id="8eb93-103">The compiler generates an ID string for each construct in your code that is tagged to generate documentation.</span></span> <span data-ttu-id="8eb93-104">(コードをタグ付けする方法については、[XML ドキュメント コメントのタグ](../../language-reference/xmldoc/index.md)に関する記事をご覧ください。)ID 文字列によって、コンストラクトは一意に識別されます。</span><span class="sxs-lookup"><span data-stu-id="8eb93-104">(For information on how to tag your code, see [XML Comment Tags](../../language-reference/xmldoc/index.md).) The ID string uniquely identifies the construct.</span></span> <span data-ttu-id="8eb93-105">XML ファイルを処理するプログラムでは、ID 文字列を使用して、対応する .NET Framework のメタデータまたはリフレクション項目を識別できます。</span><span class="sxs-lookup"><span data-stu-id="8eb93-105">Programs that process the XML file can use the ID string to identify the corresponding .NET Framework metadata/reflection item.</span></span>  
  
 <span data-ttu-id="8eb93-106">XML ファイルは、コードの階層表現ではなく、要素ごとに生成された ID を持つフラット リストです。</span><span class="sxs-lookup"><span data-stu-id="8eb93-106">The XML file is not a hierarchical representation of your code; it is a flat list with a generated ID for each element.</span></span>  
  
 <span data-ttu-id="8eb93-107">コンパイラは、次の規則に基づいて ID 文字列を生成します。</span><span class="sxs-lookup"><span data-stu-id="8eb93-107">The compiler observes the following rules when it generates the ID strings:</span></span>  
  
- <span data-ttu-id="8eb93-108">文字列に空白は配置されません。</span><span class="sxs-lookup"><span data-stu-id="8eb93-108">No white space is placed in the string.</span></span>  
  
- <span data-ttu-id="8eb93-109">ID 文字列の最初の部分は、単一の文字とそれに続くコロンで識別されるメンバーの種類を示します。</span><span class="sxs-lookup"><span data-stu-id="8eb93-109">The first part of the ID string identifies the kind of member being identified, with a single character followed by a colon.</span></span> <span data-ttu-id="8eb93-110">次のメンバー型が使用されます。</span><span class="sxs-lookup"><span data-stu-id="8eb93-110">The following member types are used.</span></span>  
  
|<span data-ttu-id="8eb93-111">文字</span><span class="sxs-lookup"><span data-stu-id="8eb93-111">Character</span></span>|<span data-ttu-id="8eb93-112">説明</span><span class="sxs-lookup"><span data-stu-id="8eb93-112">Description</span></span>|  
|---|---|  
|<span data-ttu-id="8eb93-113">N</span><span class="sxs-lookup"><span data-stu-id="8eb93-113">N</span></span>|<span data-ttu-id="8eb93-114">namespace</span><span class="sxs-lookup"><span data-stu-id="8eb93-114">namespace</span></span><br /><br /> <span data-ttu-id="8eb93-115">ドキュメント コメントを名前空間に追加することはできませんが、名前空間への CREF 参照は作成できます (サポートされている場合)。</span><span class="sxs-lookup"><span data-stu-id="8eb93-115">You cannot add documentation comments to a namespace, but you can make CREF references to them, where supported.</span></span>|  
|<span data-ttu-id="8eb93-116">T</span><span class="sxs-lookup"><span data-stu-id="8eb93-116">T</span></span>|<span data-ttu-id="8eb93-117">型: `Class`、`Module`、`Interface`、`Structure`、`Enum`、`Delegate`</span><span class="sxs-lookup"><span data-stu-id="8eb93-117">type: `Class`, `Module`, `Interface`, `Structure`, `Enum`, `Delegate`</span></span>|  
|<span data-ttu-id="8eb93-118">F</span><span class="sxs-lookup"><span data-stu-id="8eb93-118">F</span></span>|<span data-ttu-id="8eb93-119">フィールド: `Dim`</span><span class="sxs-lookup"><span data-stu-id="8eb93-119">field: `Dim`</span></span>|  
|<span data-ttu-id="8eb93-120">P</span><span class="sxs-lookup"><span data-stu-id="8eb93-120">P</span></span>|<span data-ttu-id="8eb93-121">プロパティ: `Property` (既定のプロパティを含む)</span><span class="sxs-lookup"><span data-stu-id="8eb93-121">property: `Property` (including default properties)</span></span>|  
|<span data-ttu-id="8eb93-122">M</span><span class="sxs-lookup"><span data-stu-id="8eb93-122">M</span></span>|<span data-ttu-id="8eb93-123">メソッド: `Sub`、`Function`、`Declare`、`Operator`</span><span class="sxs-lookup"><span data-stu-id="8eb93-123">method: `Sub`, `Function`, `Declare`, `Operator`</span></span>|  
|<span data-ttu-id="8eb93-124">E</span><span class="sxs-lookup"><span data-stu-id="8eb93-124">E</span></span>|<span data-ttu-id="8eb93-125">イベント: `Event`</span><span class="sxs-lookup"><span data-stu-id="8eb93-125">event: `Event`</span></span>|  
|<span data-ttu-id="8eb93-126">!</span><span class="sxs-lookup"><span data-stu-id="8eb93-126">!</span></span>|<span data-ttu-id="8eb93-127">エラー文字列</span><span class="sxs-lookup"><span data-stu-id="8eb93-127">error string</span></span><br /><br /> <span data-ttu-id="8eb93-128">あとに続く文字列で、エラーの情報を示します。</span><span class="sxs-lookup"><span data-stu-id="8eb93-128">The rest of the string provides information about the error.</span></span> <span data-ttu-id="8eb93-129">Visual Basic コンパイラは、解決できないリンクのエラー情報を生成します。</span><span class="sxs-lookup"><span data-stu-id="8eb93-129">The Visual Basic compiler generates error information for links that cannot be resolved.</span></span>|  
  
- <span data-ttu-id="8eb93-130">`String` の 2 番目の部分は、名前空間のルートから始まる、項目の完全修飾名です。</span><span class="sxs-lookup"><span data-stu-id="8eb93-130">The second part of the `String` is the fully qualified name of the item, starting at the root of the namespace.</span></span> <span data-ttu-id="8eb93-131">項目の名前、それを囲む型、名前空間は、ピリオドで区切られます。</span><span class="sxs-lookup"><span data-stu-id="8eb93-131">The name of the item, its enclosing type(s), and the namespace are separated by periods.</span></span> <span data-ttu-id="8eb93-132">項目自体の名前にピリオドが含まれている場合、それらは番号記号 (#) に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="8eb93-132">If the name of the item itself contains periods, they are replaced by the number sign (#).</span></span> <span data-ttu-id="8eb93-133">項目の名前に番号記号がないことが前提です。</span><span class="sxs-lookup"><span data-stu-id="8eb93-133">It is assumed that no item has a number sign directly in its name.</span></span> <span data-ttu-id="8eb93-134">たとえば、`String` コンストラクターの完全修飾名は `System.String.#ctor` になります。</span><span class="sxs-lookup"><span data-stu-id="8eb93-134">For example, the fully qualified name of the `String` constructor would be `System.String.#ctor`.</span></span>  
  
- <span data-ttu-id="8eb93-135">プロパティおよびメソッドについては、メソッドに引数がある場合は、引数のリストをかっこで囲み、メソッドに続けて指定します。</span><span class="sxs-lookup"><span data-stu-id="8eb93-135">For properties and methods, if there are arguments to the method, the argument list enclosed in parentheses follows.</span></span> <span data-ttu-id="8eb93-136">引数がない場合は、かっこはありません。</span><span class="sxs-lookup"><span data-stu-id="8eb93-136">If there are no arguments, no parentheses are present.</span></span> <span data-ttu-id="8eb93-137">引数はコンマで区切られます。</span><span class="sxs-lookup"><span data-stu-id="8eb93-137">The arguments are separated by commas.</span></span> <span data-ttu-id="8eb93-138">各引数のエンコードは、.NET Framework のシグネチャでのエンコード方法にそのまま従います。</span><span class="sxs-lookup"><span data-stu-id="8eb93-138">The encoding of each argument follows directly how it is encoded in a .NET Framework signature.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8eb93-139">例</span><span class="sxs-lookup"><span data-stu-id="8eb93-139">Example</span></span>  
 <span data-ttu-id="8eb93-140">次のコードは、クラスとそのメンバーの ID 文字列を生成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="8eb93-140">The following code shows how the ID strings for a class and its members are generated.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="8eb93-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="8eb93-141">See also</span></span>

- [<span data-ttu-id="8eb93-142">-doc</span><span class="sxs-lookup"><span data-stu-id="8eb93-142">-doc</span></span>](../../reference/command-line-compiler/doc.md)
- [<span data-ttu-id="8eb93-143">方法: XML ドキュメントを作成する</span><span class="sxs-lookup"><span data-stu-id="8eb93-143">How to: Create XML Documentation</span></span>](how-to-create-xml-documentation.md)
