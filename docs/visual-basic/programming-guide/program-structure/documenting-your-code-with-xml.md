---
title: XML の使用によるコードのドキュメントの作成
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], documenting code
- XML comments, Visual Basic
- Visual Basic code, documenting with XML
ms.assetid: a0d35dc7-c5f9-4d74-92ff-a1c6f28d5235
ms.openlocfilehash: 324519248b90d4f61e67803a10b3cd6c566a2a04
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404863"
---
# <a name="documenting-your-code-with-xml-visual-basic"></a><span data-ttu-id="cd2cc-102">XML の使用によるコードのドキュメントの作成 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cd2cc-102">Documenting Your Code with XML (Visual Basic)</span></span>

<span data-ttu-id="cd2cc-103">Visual Basic では、XML を使用してコードを文書化できます。</span><span class="sxs-lookup"><span data-stu-id="cd2cc-103">In Visual Basic, you can document your code using XML</span></span>

## <a name="xml-documentation-comments"></a><span data-ttu-id="cd2cc-104">XML ドキュメントのコメント</span><span class="sxs-lookup"><span data-stu-id="cd2cc-104">XML Documentation Comments</span></span>

<span data-ttu-id="cd2cc-105">Visual Basic には、プロジェクトの XML ドキュメントを自動的に作成する簡単な方法が用意されています。</span><span class="sxs-lookup"><span data-stu-id="cd2cc-105">Visual Basic provides an easy way to automatically create XML documentation for projects.</span></span> <span data-ttu-id="cd2cc-106">型とメンバーの XML スケルトンを自動的に生成し、概要、各パラメーターの説明ドキュメント、その他の注釈を指定できます。</span><span class="sxs-lookup"><span data-stu-id="cd2cc-106">You can automatically generate an XML skeleton for your types and members, and then provide summaries, descriptive documentation for each parameter, and other remarks.</span></span> <span data-ttu-id="cd2cc-107">適切な設定により、XML ドキュメントは、プロジェクトと同じ名前で .xml 拡張子を使用した XML ファイルに自動的に出力されます。</span><span class="sxs-lookup"><span data-stu-id="cd2cc-107">With the appropriate setup, the XML documentation is automatically emitted into an XML file with the same name as your project and the .xml extension.</span></span> <span data-ttu-id="cd2cc-108">詳細については、「[-doc](../../reference/command-line-compiler/doc.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd2cc-108">For more information, see [-doc](../../reference/command-line-compiler/doc.md).</span></span>

<span data-ttu-id="cd2cc-109">XML ファイルは、XML として使用したり、操作したりできます。</span><span class="sxs-lookup"><span data-stu-id="cd2cc-109">The XML file can be consumed or otherwise manipulated as XML.</span></span> <span data-ttu-id="cd2cc-110">このファイルは、プロジェクトの出力 .exe または .dll ファイルと同じディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="cd2cc-110">This file is located in the same directory as the output .exe or .dll file of your project.</span></span>

<span data-ttu-id="cd2cc-111">XML ドキュメントは `'''` で始まります。</span><span class="sxs-lookup"><span data-stu-id="cd2cc-111">XML documentation starts with `'''`.</span></span> <span data-ttu-id="cd2cc-112">これらのコメントの処理にはいくつか制限があります。</span><span class="sxs-lookup"><span data-stu-id="cd2cc-112">The processing of these comments has some restrictions:</span></span>

- <span data-ttu-id="cd2cc-113">ドキュメントは整形式の XML である必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd2cc-113">The documentation must be well-formed XML.</span></span> <span data-ttu-id="cd2cc-114">XML が整形式ではない場合は、警告が生成され、エラーが発生したことを示すコメントがドキュメント ファイルに追加されます。</span><span class="sxs-lookup"><span data-stu-id="cd2cc-114">If the XML is not well formed, a warning is generated and the documentation file contains a comment saying that an error was encountered.</span></span>

- <span data-ttu-id="cd2cc-115">開発者は、独自のタグ セットを自由に作成できます。</span><span class="sxs-lookup"><span data-stu-id="cd2cc-115">Developers are free to create their own set of tags.</span></span> <span data-ttu-id="cd2cc-116">推奨されるタグ セットがあります (このトピックの「関連項目」をご覧ください)。</span><span class="sxs-lookup"><span data-stu-id="cd2cc-116">There is a recommended set of tags (see "Related Sections" in this topic).</span></span> <span data-ttu-id="cd2cc-117">推奨されるタグの一部には特別な意味があります。</span><span class="sxs-lookup"><span data-stu-id="cd2cc-117">Some of the recommended tags have special meanings:</span></span>

  - <span data-ttu-id="cd2cc-118">\<param> タグは、パラメーターの記述に使用します。</span><span class="sxs-lookup"><span data-stu-id="cd2cc-118">The \<param> tag is used to describe parameters.</span></span> <span data-ttu-id="cd2cc-119">このタグがあると、コンパイラは、パラメーターが存在すること、およびすべてのパラメーターがドキュメントで記述されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="cd2cc-119">If used, the compiler will verify that the parameter exists and that all parameters are described in the documentation.</span></span> <span data-ttu-id="cd2cc-120">検証が失敗すると、コンパイラは警告を発行します。</span><span class="sxs-lookup"><span data-stu-id="cd2cc-120">If the verification fails, the compiler issues a warning.</span></span>

  - <span data-ttu-id="cd2cc-121">`cref` 属性は任意のタグにアタッチでき、コード要素への参照を提供します。</span><span class="sxs-lookup"><span data-stu-id="cd2cc-121">The `cref` attribute can be attached to any tag to provide a reference to a code element.</span></span> <span data-ttu-id="cd2cc-122">コンパイラは、このコード要素が存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="cd2cc-122">The compiler verifies that this code element exists.</span></span> <span data-ttu-id="cd2cc-123">検証が失敗すると、コンパイラは警告を発行します。</span><span class="sxs-lookup"><span data-stu-id="cd2cc-123">If the verification fails, the compiler issues a warning.</span></span> <span data-ttu-id="cd2cc-124">また、コンパイラは、`cref` 属性で記述されている型を探すときに、`Imports` ステートメントを優先します。</span><span class="sxs-lookup"><span data-stu-id="cd2cc-124">The compiler also respects any `Imports` statements when looking for a type described in the `cref` attribute.</span></span>

  - <span data-ttu-id="cd2cc-125">\<summary> タグは、型またはメンバーに関する追加情報を表示するために、Visual Studio の IntelliSense によって使用されます。</span><span class="sxs-lookup"><span data-stu-id="cd2cc-125">The \<summary> tag is used by IntelliSense in Visual Studio to display additional information about a type or member.</span></span>

## <a name="related-sections"></a><span data-ttu-id="cd2cc-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="cd2cc-126">Related Sections</span></span>

<span data-ttu-id="cd2cc-127">ドキュメント コメントを含む XML ファイルの作成方法の詳細については、次のトピックをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="cd2cc-127">For details on creating an XML file with documentation comments, see the following topics:</span></span>

- [<span data-ttu-id="cd2cc-128">-doc</span><span class="sxs-lookup"><span data-stu-id="cd2cc-128">-doc</span></span>](../../reference/command-line-compiler/doc.md)

- [<span data-ttu-id="cd2cc-129">XML のコメント用タグ</span><span class="sxs-lookup"><span data-stu-id="cd2cc-129">XML Comment Tags</span></span>](../../language-reference/xmldoc/index.md)

- [<span data-ttu-id="cd2cc-130">XML ファイルの処理</span><span class="sxs-lookup"><span data-stu-id="cd2cc-130">Processing the XML File</span></span>](processing-the-xml-file.md)

- [<span data-ttu-id="cd2cc-131">方法: XML ドキュメントを作成する</span><span class="sxs-lookup"><span data-stu-id="cd2cc-131">How to: Create XML Documentation</span></span>](how-to-create-xml-documentation.md)

- [<span data-ttu-id="cd2cc-132">Visual Studio の XML ツール</span><span class="sxs-lookup"><span data-stu-id="cd2cc-132">XML Tools in Visual Studio</span></span>](/visualstudio/xml-tools/xml-tools-in-visual-studio)

## <a name="see-also"></a><span data-ttu-id="cd2cc-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="cd2cc-133">See also</span></span>

- [<span data-ttu-id="cd2cc-134">Visual Basic でのアプリケーションの開発</span><span class="sxs-lookup"><span data-stu-id="cd2cc-134">Developing Applications with Visual Basic</span></span>](../../developing-apps/index.md)
- [<span data-ttu-id="cd2cc-135">Visual Basic プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="cd2cc-135">Visual Basic Programming Guide</span></span>](../index.md)
