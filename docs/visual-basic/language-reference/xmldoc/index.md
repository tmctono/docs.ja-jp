---
title: ドキュメント コメントとして推奨される XML タグ (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlDocComment
helpviewer_keywords:
- tags, XML
- XML comments, recommended tags [Visual Basic]
- comments, recommended XML tags
ms.assetid: 294e0736-ff1e-498e-af83-6db71ed41a72
ms.openlocfilehash: 2d6519af8ca1a0e2d59131eec4d63646dce7318b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69913505"
---
# <a name="recommended-xml-tags-for-documentation-comments-visual-basic"></a><span data-ttu-id="929be-102">ドキュメント コメントとして推奨される XML タグ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="929be-102">Recommended XML Tags for Documentation Comments (Visual Basic)</span></span>
<span data-ttu-id="929be-103">Visual Basic コンパイラは、コード内のドキュメントコメントを XML ファイルに処理できます。</span><span class="sxs-lookup"><span data-stu-id="929be-103">The Visual Basic compiler can process documentation comments in your code to an XML file.</span></span> <span data-ttu-id="929be-104">XML ファイルをドキュメントに処理するために、追加のツールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="929be-104">You can use additional tools to process the XML file into documentation.</span></span>  
  
 <span data-ttu-id="929be-105">XML コメントは、型や型のメンバーなどのコード構造で使用できます。</span><span class="sxs-lookup"><span data-stu-id="929be-105">XML comments are allowed on code constructs such as types and type members.</span></span> <span data-ttu-id="929be-106">部分型の場合、XML コメントを持つことができるのは型の1つの部分のみですが、そのメンバーのコメントには制限はありません。</span><span class="sxs-lookup"><span data-stu-id="929be-106">For partial types, only one part of the type can have XML comments, although there is no restriction on commenting its members.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="929be-107">ドキュメントコメントを名前空間に適用することはできません。</span><span class="sxs-lookup"><span data-stu-id="929be-107">Documentation comments cannot be applied to namespaces.</span></span> <span data-ttu-id="929be-108">これは、1つの名前空間が複数のアセンブリにまたがることができ、すべてのアセンブリを同時に読み込む必要がないためです。</span><span class="sxs-lookup"><span data-stu-id="929be-108">The reason is that one namespace can span several assemblies, and not all assemblies have to be loaded at the same time.</span></span>  
  
 <span data-ttu-id="929be-109">コンパイラは、有効な XML であるすべてのタグを処理します。</span><span class="sxs-lookup"><span data-stu-id="929be-109">The compiler processes any tag that is valid XML.</span></span> <span data-ttu-id="929be-110">次のタグは、ユーザードキュメントで一般的に使用される機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="929be-110">The following tags provide commonly used functionality in user documentation.</span></span>  
  
||||  
|---|---|---|  
|[<span data-ttu-id="929be-111">\<c></span><span class="sxs-lookup"><span data-stu-id="929be-111">\<c></span></span>](../../../visual-basic/language-reference/xmldoc/c.md)|[<span data-ttu-id="929be-112">\<code></span><span class="sxs-lookup"><span data-stu-id="929be-112">\<code></span></span>](../../../visual-basic/language-reference/xmldoc/code.md)|[<span data-ttu-id="929be-113">\<example></span><span class="sxs-lookup"><span data-stu-id="929be-113">\<example></span></span>](../../../visual-basic/language-reference/xmldoc/example.md)|  
|<span data-ttu-id="929be-114">[\<exception>](../../../visual-basic/language-reference/xmldoc/exception.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="929be-114">[\<exception>](../../../visual-basic/language-reference/xmldoc/exception.md) <sup>1</sup></span></span>|<span data-ttu-id="929be-115">[\<include>](../../../visual-basic/language-reference/xmldoc/include.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="929be-115">[\<include>](../../../visual-basic/language-reference/xmldoc/include.md) <sup>1</sup></span></span>|[<span data-ttu-id="929be-116">\<list></span><span class="sxs-lookup"><span data-stu-id="929be-116">\<list></span></span>](../../../visual-basic/language-reference/xmldoc/list.md)|  
|[<span data-ttu-id="929be-117">\<para></span><span class="sxs-lookup"><span data-stu-id="929be-117">\<para></span></span>](../../../visual-basic/language-reference/xmldoc/para.md)|<span data-ttu-id="929be-118">param > <sup>1</sup> [ \<](../../../visual-basic/language-reference/xmldoc/param.md)</span><span class="sxs-lookup"><span data-stu-id="929be-118">[\<param>](../../../visual-basic/language-reference/xmldoc/param.md) <sup>1</sup></span></span>|[<span data-ttu-id="929be-119">\<paramref></span><span class="sxs-lookup"><span data-stu-id="929be-119">\<paramref></span></span>](../../../visual-basic/language-reference/xmldoc/paramref.md)|  
|<span data-ttu-id="929be-120">アクセス許可 > <sup>1</sup> [ \<](../../../visual-basic/language-reference/xmldoc/permission.md)</span><span class="sxs-lookup"><span data-stu-id="929be-120">[\<permission>](../../../visual-basic/language-reference/xmldoc/permission.md) <sup>1</sup></span></span>|[<span data-ttu-id="929be-121">\<remarks></span><span class="sxs-lookup"><span data-stu-id="929be-121">\<remarks></span></span>](../../../visual-basic/language-reference/xmldoc/remarks.md)|[<span data-ttu-id="929be-122">\<returns></span><span class="sxs-lookup"><span data-stu-id="929be-122">\<returns></span></span>](../../../visual-basic/language-reference/xmldoc/returns.md)|  
|<span data-ttu-id="929be-123">> を<sup></sup> [参照して\<ください](../../../visual-basic/language-reference/xmldoc/see.md)1</span><span class="sxs-lookup"><span data-stu-id="929be-123">[\<see>](../../../visual-basic/language-reference/xmldoc/see.md) <sup>1</sup></span></span>|<span data-ttu-id="929be-124">seealso > <sup>1</sup> [ \<](../../../visual-basic/language-reference/xmldoc/seealso.md)</span><span class="sxs-lookup"><span data-stu-id="929be-124">[\<seealso>](../../../visual-basic/language-reference/xmldoc/seealso.md) <sup>1</sup></span></span>|[<span data-ttu-id="929be-125">\<summary></span><span class="sxs-lookup"><span data-stu-id="929be-125">\<summary></span></span>](../../../visual-basic/language-reference/xmldoc/summary.md)|  
|<span data-ttu-id="929be-126">[\<typeparam>](../../../visual-basic/language-reference/xmldoc/typeparam.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="929be-126">[\<typeparam>](../../../visual-basic/language-reference/xmldoc/typeparam.md) <sup>1</sup></span></span>|[<span data-ttu-id="929be-127">\<value></span><span class="sxs-lookup"><span data-stu-id="929be-127">\<value></span></span>](../../../visual-basic/language-reference/xmldoc/value.md)||  
  
 <span data-ttu-id="929be-128">(<sup>1</sup>コンパイラは構文を検証します)。</span><span class="sxs-lookup"><span data-stu-id="929be-128">(<sup>1</sup> The compiler verifies syntax.)</span></span>  
  
> [!NOTE]
> <span data-ttu-id="929be-129">ドキュメントコメントのテキストに山かっこを表示する場合は、および`&lt;` `&gt;`を使用します。</span><span class="sxs-lookup"><span data-stu-id="929be-129">If you want angle brackets to appear in the text of a documentation comment, use `&lt;` and `&gt;`.</span></span> <span data-ttu-id="929be-130">たとえば、文字列`"&lt;text in angle brackets&gt;"`はとして`<text in angle brackets>`表示されます。</span><span class="sxs-lookup"><span data-stu-id="929be-130">For example, the string `"&lt;text in angle brackets&gt;"` will appear as `<text in angle brackets>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="929be-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="929be-131">See also</span></span>

- [<span data-ttu-id="929be-132">XML の使用によるコードのドキュメントの作成</span><span class="sxs-lookup"><span data-stu-id="929be-132">Documenting Your Code with XML</span></span>](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)
- [<span data-ttu-id="929be-133">/doc</span><span class="sxs-lookup"><span data-stu-id="929be-133">/doc</span></span>](../../../visual-basic/reference/command-line-compiler/doc.md)
- [<span data-ttu-id="929be-134">方法: XML ドキュメントの作成</span><span class="sxs-lookup"><span data-stu-id="929be-134">How to: Create XML Documentation</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
