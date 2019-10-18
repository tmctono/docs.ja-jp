---
title: XML の使用によるコードのドキュメントの作成 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], documenting code
- XML comments, Visual Basic
- Visual Basic code, documenting with XML
ms.assetid: a0d35dc7-c5f9-4d74-92ff-a1c6f28d5235
ms.openlocfilehash: 58c8716450fd8310b81050c86dc297c5b7527761
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524507"
---
# <a name="documenting-your-code-with-xml-visual-basic"></a><span data-ttu-id="7f230-102">XML の使用によるコードのドキュメントの作成 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7f230-102">Documenting Your Code with XML (Visual Basic)</span></span>

<span data-ttu-id="7f230-103">Visual Basic では、XML を使用してコードをドキュメント化できます。</span><span class="sxs-lookup"><span data-stu-id="7f230-103">In Visual Basic, you can document your code using XML</span></span>

## <a name="xml-documentation-comments"></a><span data-ttu-id="7f230-104">XML ドキュメントのコメント</span><span class="sxs-lookup"><span data-stu-id="7f230-104">XML Documentation Comments</span></span>

<span data-ttu-id="7f230-105">Visual Basic は、プロジェクトの XML ドキュメントを自動的に作成する簡単な方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="7f230-105">Visual Basic provides an easy way to automatically create XML documentation for projects.</span></span> <span data-ttu-id="7f230-106">型とメンバーの XML スケルトンを自動的に生成し、各パラメーターの概要、説明ドキュメント、およびその他の解説を提供できます。</span><span class="sxs-lookup"><span data-stu-id="7f230-106">You can automatically generate an XML skeleton for your types and members, and then provide summaries, descriptive documentation for each parameter, and other remarks.</span></span> <span data-ttu-id="7f230-107">適切な設定を使用すると、XML ドキュメントはプロジェクトと同じ名前の xml ファイルに自動的に出力され、.xml 拡張子が付けられます。</span><span class="sxs-lookup"><span data-stu-id="7f230-107">With the appropriate setup, the XML documentation is automatically emitted into an XML file with the same name as your project and the .xml extension.</span></span> <span data-ttu-id="7f230-108">詳細については、「[-doc](../../../visual-basic/reference/command-line-compiler/doc.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7f230-108">For more information, see [-doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span></span>

<span data-ttu-id="7f230-109">XML ファイルは、XML として使用することも、それ以外の方法で操作することもできます。</span><span class="sxs-lookup"><span data-stu-id="7f230-109">The XML file can be consumed or otherwise manipulated as XML.</span></span> <span data-ttu-id="7f230-110">このファイルは、プロジェクトの出力 .exe ファイルまたは .dll ファイルと同じディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="7f230-110">This file is located in the same directory as the output .exe or .dll file of your project.</span></span>

<span data-ttu-id="7f230-111">XML ドキュメントは `'''` から始まります。</span><span class="sxs-lookup"><span data-stu-id="7f230-111">XML documentation starts with `'''`.</span></span> <span data-ttu-id="7f230-112">これらのコメントの処理にはいくつか制限があります。</span><span class="sxs-lookup"><span data-stu-id="7f230-112">The processing of these comments has some restrictions:</span></span>

- <span data-ttu-id="7f230-113">ドキュメントは整形式の XML である必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f230-113">The documentation must be well-formed XML.</span></span> <span data-ttu-id="7f230-114">XML が整形式でない場合は、警告が生成され、ドキュメントファイルにはエラーが発生したことを示すコメントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="7f230-114">If the XML is not well formed, a warning is generated and the documentation file contains a comment saying that an error was encountered.</span></span>

- <span data-ttu-id="7f230-115">開発者は、独自のタグ セットを自由に作成できます。</span><span class="sxs-lookup"><span data-stu-id="7f230-115">Developers are free to create their own set of tags.</span></span> <span data-ttu-id="7f230-116">推奨される一連のタグがあります (このトピックの「関連セクション」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="7f230-116">There is a recommended set of tags (see "Related Sections" in this topic).</span></span> <span data-ttu-id="7f230-117">推奨されるタグの一部には特別な意味があります。</span><span class="sxs-lookup"><span data-stu-id="7f230-117">Some of the recommended tags have special meanings:</span></span>

  - <span data-ttu-id="7f230-118">\<param> タグは、パラメーターの記述に使われます。</span><span class="sxs-lookup"><span data-stu-id="7f230-118">The \<param> tag is used to describe parameters.</span></span> <span data-ttu-id="7f230-119">このタグがあると、コンパイラは、パラメーターが存在すること、およびすべてのパラメーターがドキュメントで記述されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7f230-119">If used, the compiler will verify that the parameter exists and that all parameters are described in the documentation.</span></span> <span data-ttu-id="7f230-120">検証が失敗した場合、コンパイラは警告を発行します。</span><span class="sxs-lookup"><span data-stu-id="7f230-120">If the verification fails, the compiler issues a warning.</span></span>

  - <span data-ttu-id="7f230-121">`cref` 属性は任意のタグにアタッチでき、コード要素への参照を提供します。</span><span class="sxs-lookup"><span data-stu-id="7f230-121">The `cref` attribute can be attached to any tag to provide a reference to a code element.</span></span> <span data-ttu-id="7f230-122">コンパイラは、このコード要素が存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="7f230-122">The compiler verifies that this code element exists.</span></span> <span data-ttu-id="7f230-123">検証が失敗した場合、コンパイラは警告を発行します。</span><span class="sxs-lookup"><span data-stu-id="7f230-123">If the verification fails, the compiler issues a warning.</span></span> <span data-ttu-id="7f230-124">また、コンパイラは、`cref` 属性で記述されている型を検索するときに、`Imports` のすべてのステートメントを尊重します。</span><span class="sxs-lookup"><span data-stu-id="7f230-124">The compiler also respects any `Imports` statements when looking for a type described in the `cref` attribute.</span></span>

  - <span data-ttu-id="7f230-125">@No__t_0summary > タグは、型またはメンバーに関する追加情報を表示するために Visual Studio の IntelliSense によって使用されます。</span><span class="sxs-lookup"><span data-stu-id="7f230-125">The \<summary> tag is used by IntelliSense in Visual Studio to display additional information about a type or member.</span></span>

## <a name="related-sections"></a><span data-ttu-id="7f230-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="7f230-126">Related Sections</span></span>

<span data-ttu-id="7f230-127">ドキュメントコメントを含む XML ファイルの作成の詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7f230-127">For details on creating an XML file with documentation comments, see the following topics:</span></span>

- [<span data-ttu-id="7f230-128">-doc</span><span class="sxs-lookup"><span data-stu-id="7f230-128">-doc</span></span>](../../../visual-basic/reference/command-line-compiler/doc.md)

- [<span data-ttu-id="7f230-129">XML のコメント用タグ</span><span class="sxs-lookup"><span data-stu-id="7f230-129">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)

- [<span data-ttu-id="7f230-130">XML ファイルの処理</span><span class="sxs-lookup"><span data-stu-id="7f230-130">Processing the XML File</span></span>](../../../visual-basic/programming-guide/program-structure/processing-the-xml-file.md)

- [<span data-ttu-id="7f230-131">方法: XML ドキュメントを作成する</span><span class="sxs-lookup"><span data-stu-id="7f230-131">How to: Create XML Documentation</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)

- [<span data-ttu-id="7f230-132">Visual Studio の XML ツール</span><span class="sxs-lookup"><span data-stu-id="7f230-132">XML Tools in Visual Studio</span></span>](/visualstudio/xml-tools/xml-tools-in-visual-studio)

## <a name="see-also"></a><span data-ttu-id="7f230-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="7f230-133">See also</span></span>

- [<span data-ttu-id="7f230-134">Visual Basic でのアプリケーションの開発</span><span class="sxs-lookup"><span data-stu-id="7f230-134">Developing Applications with Visual Basic</span></span>](../../../visual-basic/developing-apps/index.md)
- [<span data-ttu-id="7f230-135">Visual Basic のプログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="7f230-135">Visual Basic Programming Guide</span></span>](../../../visual-basic/programming-guide/index.md)
