---
title: XML の使用によるコードのドキュメントの作成
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], documenting code
- XML comments, Visual Basic
- Visual Basic code, documenting with XML
ms.assetid: a0d35dc7-c5f9-4d74-92ff-a1c6f28d5235
ms.openlocfilehash: bdf0da7a8acc919e4a1d66b81e30c9ed912dd321
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347441"
---
# <a name="documenting-your-code-with-xml-visual-basic"></a><span data-ttu-id="adda5-102">XML の使用によるコードのドキュメントの作成 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="adda5-102">Documenting Your Code with XML (Visual Basic)</span></span>

<span data-ttu-id="adda5-103">In Visual Basic, you can document your code using XML</span><span class="sxs-lookup"><span data-stu-id="adda5-103">In Visual Basic, you can document your code using XML</span></span>

## <a name="xml-documentation-comments"></a><span data-ttu-id="adda5-104">XML ドキュメントのコメント</span><span class="sxs-lookup"><span data-stu-id="adda5-104">XML Documentation Comments</span></span>

<span data-ttu-id="adda5-105">Visual Basic provides an easy way to automatically create XML documentation for projects.</span><span class="sxs-lookup"><span data-stu-id="adda5-105">Visual Basic provides an easy way to automatically create XML documentation for projects.</span></span> <span data-ttu-id="adda5-106">You can automatically generate an XML skeleton for your types and members, and then provide summaries, descriptive documentation for each parameter, and other remarks.</span><span class="sxs-lookup"><span data-stu-id="adda5-106">You can automatically generate an XML skeleton for your types and members, and then provide summaries, descriptive documentation for each parameter, and other remarks.</span></span> <span data-ttu-id="adda5-107">With the appropriate setup, the XML documentation is automatically emitted into an XML file with the same name as your project and the .xml extension.</span><span class="sxs-lookup"><span data-stu-id="adda5-107">With the appropriate setup, the XML documentation is automatically emitted into an XML file with the same name as your project and the .xml extension.</span></span> <span data-ttu-id="adda5-108">詳細については、「[-doc](../../../visual-basic/reference/command-line-compiler/doc.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="adda5-108">For more information, see [-doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span></span>

<span data-ttu-id="adda5-109">The XML file can be consumed or otherwise manipulated as XML.</span><span class="sxs-lookup"><span data-stu-id="adda5-109">The XML file can be consumed or otherwise manipulated as XML.</span></span> <span data-ttu-id="adda5-110">This file is located in the same directory as the output .exe or .dll file of your project.</span><span class="sxs-lookup"><span data-stu-id="adda5-110">This file is located in the same directory as the output .exe or .dll file of your project.</span></span>

<span data-ttu-id="adda5-111">XML documentation starts with `'''`.</span><span class="sxs-lookup"><span data-stu-id="adda5-111">XML documentation starts with `'''`.</span></span> <span data-ttu-id="adda5-112">これらのコメントの処理にはいくつか制限があります。</span><span class="sxs-lookup"><span data-stu-id="adda5-112">The processing of these comments has some restrictions:</span></span>

- <span data-ttu-id="adda5-113">ドキュメントは整形式の XML である必要があります。</span><span class="sxs-lookup"><span data-stu-id="adda5-113">The documentation must be well-formed XML.</span></span> <span data-ttu-id="adda5-114">If the XML is not well formed, a warning is generated and the documentation file contains a comment saying that an error was encountered.</span><span class="sxs-lookup"><span data-stu-id="adda5-114">If the XML is not well formed, a warning is generated and the documentation file contains a comment saying that an error was encountered.</span></span>

- <span data-ttu-id="adda5-115">開発者は、独自のタグ セットを自由に作成できます。</span><span class="sxs-lookup"><span data-stu-id="adda5-115">Developers are free to create their own set of tags.</span></span> <span data-ttu-id="adda5-116">There is a recommended set of tags (see "Related Sections" in this topic).</span><span class="sxs-lookup"><span data-stu-id="adda5-116">There is a recommended set of tags (see "Related Sections" in this topic).</span></span> <span data-ttu-id="adda5-117">推奨されるタグの一部には特別な意味があります。</span><span class="sxs-lookup"><span data-stu-id="adda5-117">Some of the recommended tags have special meanings:</span></span>

  - <span data-ttu-id="adda5-118">\<param> タグは、パラメーターの記述に使われます。</span><span class="sxs-lookup"><span data-stu-id="adda5-118">The \<param> tag is used to describe parameters.</span></span> <span data-ttu-id="adda5-119">このタグがあると、コンパイラは、パラメーターが存在すること、およびすべてのパラメーターがドキュメントで記述されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="adda5-119">If used, the compiler will verify that the parameter exists and that all parameters are described in the documentation.</span></span> <span data-ttu-id="adda5-120">If the verification fails, the compiler issues a warning.</span><span class="sxs-lookup"><span data-stu-id="adda5-120">If the verification fails, the compiler issues a warning.</span></span>

  - <span data-ttu-id="adda5-121">`cref` 属性は任意のタグにアタッチでき、コード要素への参照を提供します。</span><span class="sxs-lookup"><span data-stu-id="adda5-121">The `cref` attribute can be attached to any tag to provide a reference to a code element.</span></span> <span data-ttu-id="adda5-122">コンパイラは、このコード要素が存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="adda5-122">The compiler verifies that this code element exists.</span></span> <span data-ttu-id="adda5-123">If the verification fails, the compiler issues a warning.</span><span class="sxs-lookup"><span data-stu-id="adda5-123">If the verification fails, the compiler issues a warning.</span></span> <span data-ttu-id="adda5-124">The compiler also respects any `Imports` statements when looking for a type described in the `cref` attribute.</span><span class="sxs-lookup"><span data-stu-id="adda5-124">The compiler also respects any `Imports` statements when looking for a type described in the `cref` attribute.</span></span>

  - <span data-ttu-id="adda5-125">The \<summary> tag is used by IntelliSense in Visual Studio to display additional information about a type or member.</span><span class="sxs-lookup"><span data-stu-id="adda5-125">The \<summary> tag is used by IntelliSense in Visual Studio to display additional information about a type or member.</span></span>

## <a name="related-sections"></a><span data-ttu-id="adda5-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="adda5-126">Related Sections</span></span>

<span data-ttu-id="adda5-127">For details on creating an XML file with documentation comments, see the following topics:</span><span class="sxs-lookup"><span data-stu-id="adda5-127">For details on creating an XML file with documentation comments, see the following topics:</span></span>

- [<span data-ttu-id="adda5-128">-doc</span><span class="sxs-lookup"><span data-stu-id="adda5-128">-doc</span></span>](../../../visual-basic/reference/command-line-compiler/doc.md)

- [<span data-ttu-id="adda5-129">XML のコメント用タグ</span><span class="sxs-lookup"><span data-stu-id="adda5-129">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)

- [<span data-ttu-id="adda5-130">XML ファイルの処理</span><span class="sxs-lookup"><span data-stu-id="adda5-130">Processing the XML File</span></span>](../../../visual-basic/programming-guide/program-structure/processing-the-xml-file.md)

- [<span data-ttu-id="adda5-131">方法: XML ドキュメントを作成する</span><span class="sxs-lookup"><span data-stu-id="adda5-131">How to: Create XML Documentation</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)

- [<span data-ttu-id="adda5-132">Visual Studio の XML ツール</span><span class="sxs-lookup"><span data-stu-id="adda5-132">XML Tools in Visual Studio</span></span>](/visualstudio/xml-tools/xml-tools-in-visual-studio)

## <a name="see-also"></a><span data-ttu-id="adda5-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="adda5-133">See also</span></span>

- [<span data-ttu-id="adda5-134">Visual Basic でのアプリケーションの開発</span><span class="sxs-lookup"><span data-stu-id="adda5-134">Developing Applications with Visual Basic</span></span>](../../../visual-basic/developing-apps/index.md)
- [<span data-ttu-id="adda5-135">Visual Basic のプログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="adda5-135">Visual Basic Programming Guide</span></span>](../../../visual-basic/programming-guide/index.md)
