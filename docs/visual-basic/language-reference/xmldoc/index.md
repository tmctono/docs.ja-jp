---
title: ドキュメント コメントとして推奨される XML タグ
ms.date: 07/20/2015
f1_keywords:
- vb.XmlDocComment
helpviewer_keywords:
- tags, XML
- XML comments, recommended tags [Visual Basic]
- comments, recommended XML tags
ms.assetid: 294e0736-ff1e-498e-af83-6db71ed41a72
ms.openlocfilehash: af57fc7d55c5cfda24a2fd9406b17dedee898760
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "85503787"
---
# <a name="recommended-xml-tags-for-documentation-comments-visual-basic"></a><span data-ttu-id="ca510-102">ドキュメント コメントとして推奨される XML タグ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ca510-102">Recommended XML Tags for Documentation Comments (Visual Basic)</span></span>
<span data-ttu-id="ca510-103">Visual Basic コンパイラでは、コード内のドキュメント コメントを処理し、XML ファイルに変換できます。</span><span class="sxs-lookup"><span data-stu-id="ca510-103">The Visual Basic compiler can process documentation comments in your code to an XML file.</span></span> <span data-ttu-id="ca510-104">追加のツールを利用すれば、XML ファイルを処理してドキュメントに変換できます。</span><span class="sxs-lookup"><span data-stu-id="ca510-104">You can use additional tools to process the XML file into documentation.</span></span>  
  
 <span data-ttu-id="ca510-105">XML コメントは、型や型メンバーなどのコード コンストラクターで許可されます。</span><span class="sxs-lookup"><span data-stu-id="ca510-105">XML comments are allowed on code constructs such as types and type members.</span></span> <span data-ttu-id="ca510-106">部分型の場合、そのメンバーに対するコメント作成に制限はありませんが、XML コメントを追加できる型の部分は 1 つだけです。</span><span class="sxs-lookup"><span data-stu-id="ca510-106">For partial types, only one part of the type can have XML comments, although there is no restriction on commenting its members.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ca510-107">ドキュメント コメントは、名前空間に適用できません。</span><span class="sxs-lookup"><span data-stu-id="ca510-107">Documentation comments cannot be applied to namespaces.</span></span> <span data-ttu-id="ca510-108">その理由は、1 つの名前空間は複数のアセンブリにまたがることができて、かつ、すべてのアセンブリを同時に読み込む必要はないということにあります。</span><span class="sxs-lookup"><span data-stu-id="ca510-108">The reason is that one namespace can span several assemblies, and not all assemblies have to be loaded at the same time.</span></span>  
  
 <span data-ttu-id="ca510-109">コンパイラは、有効な XML であるタグをすべて処理します。</span><span class="sxs-lookup"><span data-stu-id="ca510-109">The compiler processes any tag that is valid XML.</span></span> <span data-ttu-id="ca510-110">次のタグによって、ユーザー ドキュメントで一般的に使用される機能が与えられます。</span><span class="sxs-lookup"><span data-stu-id="ca510-110">The following tags provide commonly used functionality in user documentation.</span></span>  
  
||||  
|---|---|---|  
|[\<c>](c.md)|[\<code>](code.md)|[\<example>](example.md)|  
|<span data-ttu-id="ca510-111">[\<exception>](exception.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="ca510-111">[\<exception>](exception.md) <sup>1</sup></span></span>|<span data-ttu-id="ca510-112">[\<include>](include.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="ca510-112">[\<include>](include.md) <sup>1</sup></span></span>|[\<list>](list.md)|  
|[\<para>](para.md)|<span data-ttu-id="ca510-113">[\<param>](param.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="ca510-113">[\<param>](param.md) <sup>1</sup></span></span>|[\<paramref>](paramref.md)|  
|<span data-ttu-id="ca510-114">[\<permission>](permission.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="ca510-114">[\<permission>](permission.md) <sup>1</sup></span></span>|[\<remarks>](remarks.md)|[\<returns>](returns.md)|  
|<span data-ttu-id="ca510-115">[\<see>](see.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="ca510-115">[\<see>](see.md) <sup>1</sup></span></span>|<span data-ttu-id="ca510-116">[\<seealso>](seealso.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="ca510-116">[\<seealso>](seealso.md) <sup>1</sup></span></span>|[\<summary>](summary.md)|  
|<span data-ttu-id="ca510-117">[\<typeparam>](typeparam.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="ca510-117">[\<typeparam>](typeparam.md) <sup>1</sup></span></span>|[\<value>](value.md)||  
  
 <span data-ttu-id="ca510-118">(<sup>1</sup> コンパイラによって構文が検証されます。)</span><span class="sxs-lookup"><span data-stu-id="ca510-118">(<sup>1</sup> The compiler verifies syntax.)</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ca510-119">ドキュメント コメントのテキストに山かっこを表示する場合は、`&lt;` と `&gt;` を使用します。</span><span class="sxs-lookup"><span data-stu-id="ca510-119">If you want angle brackets to appear in the text of a documentation comment, use `&lt;` and `&gt;`.</span></span> <span data-ttu-id="ca510-120">たとえば、文字列 `"&lt;text in angle brackets&gt;"` は `<text in angle brackets>` として表示されます。</span><span class="sxs-lookup"><span data-stu-id="ca510-120">For example, the string `"&lt;text in angle brackets&gt;"` will appear as `<text in angle brackets>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca510-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="ca510-121">See also</span></span>

- [<span data-ttu-id="ca510-122">XML の使用によるコードのドキュメントの作成</span><span class="sxs-lookup"><span data-stu-id="ca510-122">Documenting Your Code with XML</span></span>](../../programming-guide/program-structure/documenting-your-code-with-xml.md)
- [<span data-ttu-id="ca510-123">-doc</span><span class="sxs-lookup"><span data-stu-id="ca510-123">-doc</span></span>](../../reference/command-line-compiler/doc.md)
- [<span data-ttu-id="ca510-124">方法: XML ドキュメントを作成する</span><span class="sxs-lookup"><span data-stu-id="ca510-124">How to: Create XML Documentation</span></span>](../../programming-guide/program-structure/how-to-create-xml-documentation.md)
