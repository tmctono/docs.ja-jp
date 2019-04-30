---
title: <include> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- include XML tag
- <include> XML tag
ms.assetid: ba8e9173-82cd-460b-8938-a075a2dfb36d
ms.openlocfilehash: d9c1c1a50f0e3530c842a6058e288b8d2be15f95
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940908"
---
# <a name="include-visual-basic"></a><span data-ttu-id="b3d76-102">\<含める > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b3d76-102">\<include> (Visual Basic)</span></span>
<span data-ttu-id="b3d76-103">型と、ソース コード内のメンバーを記述する別のファイルを参照します。</span><span class="sxs-lookup"><span data-stu-id="b3d76-103">Refers to another file that describes the types and members in your source code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3d76-104">構文</span><span class="sxs-lookup"><span data-stu-id="b3d76-104">Syntax</span></span>  
  
```xml  
<include file="filename" path="tagpath[@name='id']" />  
```  
  
## <a name="parameters"></a><span data-ttu-id="b3d76-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b3d76-105">Parameters</span></span>  
 `filename`  
 <span data-ttu-id="b3d76-106">必須。</span><span class="sxs-lookup"><span data-stu-id="b3d76-106">Required.</span></span> <span data-ttu-id="b3d76-107">文書を含むファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="b3d76-107">The name of the file containing the documentation.</span></span> <span data-ttu-id="b3d76-108">ファイル名をパスで修飾することができます。</span><span class="sxs-lookup"><span data-stu-id="b3d76-108">The file name can be qualified with a path.</span></span> <span data-ttu-id="b3d76-109">囲む`filename`で二重引用符 ("")。</span><span class="sxs-lookup"><span data-stu-id="b3d76-109">Enclose `filename` in double quotation marks (" ").</span></span>  
  
 `tagpath`  
 <span data-ttu-id="b3d76-110">必須。</span><span class="sxs-lookup"><span data-stu-id="b3d76-110">Required.</span></span> <span data-ttu-id="b3d76-111">タグ `name` につながる `filename` 内のタグのパス。</span><span class="sxs-lookup"><span data-stu-id="b3d76-111">The path of the tags in `filename` that leads to the tag `name`.</span></span> <span data-ttu-id="b3d76-112">パスを二重引用符で囲みます ("")。</span><span class="sxs-lookup"><span data-stu-id="b3d76-112">Enclose the path in double quotation marks (" ").</span></span>  
  
 `name`  
 <span data-ttu-id="b3d76-113">必須。</span><span class="sxs-lookup"><span data-stu-id="b3d76-113">Required.</span></span> <span data-ttu-id="b3d76-114">コメントの前にあるタグの名前指定子。</span><span class="sxs-lookup"><span data-stu-id="b3d76-114">The name specifier in the tag that precedes the comments.</span></span> <span data-ttu-id="b3d76-115">`Name` 必要があります、`id`します。</span><span class="sxs-lookup"><span data-stu-id="b3d76-115">`Name` will have an `id`.</span></span>  
  
 `id`  
 <span data-ttu-id="b3d76-116">必須。</span><span class="sxs-lookup"><span data-stu-id="b3d76-116">Required.</span></span> <span data-ttu-id="b3d76-117">コメントの前に配置するタグの ID。</span><span class="sxs-lookup"><span data-stu-id="b3d76-117">The ID for the tag that precedes the comments.</span></span> <span data-ttu-id="b3d76-118">ID を単一引用符で囲みます (' ')。</span><span class="sxs-lookup"><span data-stu-id="b3d76-118">Enclose the ID in single quotation marks (' ').</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b3d76-119">Remarks</span><span class="sxs-lookup"><span data-stu-id="b3d76-119">Remarks</span></span>  
 <span data-ttu-id="b3d76-120">使用して、`<include>`タグをソース コード内のメンバーと型を記述する別のファイル内のコメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3d76-120">Use the `<include>` tag to refer to comments in another file that describe the types and members in your source code.</span></span> <span data-ttu-id="b3d76-121">これは文書化のコメントをソース コード ファイル内に直接配置する方法の代替です。</span><span class="sxs-lookup"><span data-stu-id="b3d76-121">This is an alternative to placing documentation comments directly in your source code file.</span></span>  
  
 <span data-ttu-id="b3d76-122">`<include>`タグは、W3C XML Path Language (XPath) Version 1.0 』 を使用します。</span><span class="sxs-lookup"><span data-stu-id="b3d76-122">The `<include>` tag uses the W3C XML Path Language (XPath) Version 1.0 Recommendation.</span></span> <span data-ttu-id="b3d76-123">カスタマイズする方法の詳細については、`<include>`を使用して、参照してください<https://www.w3.org/TR/xpath>します。</span><span class="sxs-lookup"><span data-stu-id="b3d76-123">For more information about ways to customize your `<include>` use, see <https://www.w3.org/TR/xpath>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b3d76-124">例</span><span class="sxs-lookup"><span data-stu-id="b3d76-124">Example</span></span>  
 <span data-ttu-id="b3d76-125">この例では、`<include>`メンバー ドキュメントのコメントをという名前のファイルからインポートするタグ`commentFile.xml`します。</span><span class="sxs-lookup"><span data-stu-id="b3d76-125">This example uses the `<include>` tag to import member documentation comments from a file called `commentFile.xml`.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#4)]  
  
 <span data-ttu-id="b3d76-126">形式、`commentFile.xml`のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b3d76-126">The format of the `commentFile.xml` is as follows.</span></span>  
  
```xml  
<Docs>  
<Members name="Open">  
<summary>Opens a file.</summary>  
<param name="filename">File name to open.</param>  
</Members>  
<Members name="Close">  
<summary>Closes a file.</summary>  
<param name="filename">File name to close.</param>  
</Members>  
</Docs>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b3d76-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="b3d76-127">See also</span></span>

- [<span data-ttu-id="b3d76-128">XML のコメント用タグ</span><span class="sxs-lookup"><span data-stu-id="b3d76-128">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
