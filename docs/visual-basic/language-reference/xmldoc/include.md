---
title: <include>
ms.date: 07/20/2015
helpviewer_keywords:
- include XML tag
- <include> XML tag
ms.assetid: ba8e9173-82cd-460b-8938-a075a2dfb36d
ms.openlocfilehash: 2f2bebfd06d4614f05cb66834cc5bef40524ce3b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348457"
---
# <a name="include-visual-basic"></a><span data-ttu-id="b7575-101">\<include> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b7575-101">\<include> (Visual Basic)</span></span>
<span data-ttu-id="b7575-102">ソース コード内の型とメンバーを記述する別のファイルを参照します。</span><span class="sxs-lookup"><span data-stu-id="b7575-102">Refers to another file that describes the types and members in your source code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7575-103">構文</span><span class="sxs-lookup"><span data-stu-id="b7575-103">Syntax</span></span>  
  
```xml  
<include file="filename" path="tagpath[@name='id']" />  
```  
  
## <a name="parameters"></a><span data-ttu-id="b7575-104">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b7575-104">Parameters</span></span>  
 `filename`  
 <span data-ttu-id="b7575-105">必須です。</span><span class="sxs-lookup"><span data-stu-id="b7575-105">Required.</span></span> <span data-ttu-id="b7575-106">文書を含むファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="b7575-106">The name of the file containing the documentation.</span></span> <span data-ttu-id="b7575-107">ファイル名をパスで修飾することができます。</span><span class="sxs-lookup"><span data-stu-id="b7575-107">The file name can be qualified with a path.</span></span> <span data-ttu-id="b7575-108">`filename` は二重引用符 (" ") で囲みます。</span><span class="sxs-lookup"><span data-stu-id="b7575-108">Enclose `filename` in double quotation marks (" ").</span></span>  
  
 `tagpath`  
 <span data-ttu-id="b7575-109">必須です。</span><span class="sxs-lookup"><span data-stu-id="b7575-109">Required.</span></span> <span data-ttu-id="b7575-110">タグ `name` につながる `filename` 内のタグのパス。</span><span class="sxs-lookup"><span data-stu-id="b7575-110">The path of the tags in `filename` that leads to the tag `name`.</span></span> <span data-ttu-id="b7575-111">パスは二重引用符 (" ") で囲みます。</span><span class="sxs-lookup"><span data-stu-id="b7575-111">Enclose the path in double quotation marks (" ").</span></span>  
  
 `name`  
 <span data-ttu-id="b7575-112">必須です。</span><span class="sxs-lookup"><span data-stu-id="b7575-112">Required.</span></span> <span data-ttu-id="b7575-113">コメントの前に配置するタグの名前指定子。</span><span class="sxs-lookup"><span data-stu-id="b7575-113">The name specifier in the tag that precedes the comments.</span></span> <span data-ttu-id="b7575-114">`Name` には `id` が指定されます。</span><span class="sxs-lookup"><span data-stu-id="b7575-114">`Name` will have an `id`.</span></span>  
  
 `id`  
 <span data-ttu-id="b7575-115">必須です。</span><span class="sxs-lookup"><span data-stu-id="b7575-115">Required.</span></span> <span data-ttu-id="b7575-116">コメントの前に配置するタグの ID。</span><span class="sxs-lookup"><span data-stu-id="b7575-116">The ID for the tag that precedes the comments.</span></span> <span data-ttu-id="b7575-117">ID は単一引用符 (' ') で囲みます。</span><span class="sxs-lookup"><span data-stu-id="b7575-117">Enclose the ID in single quotation marks (' ').</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b7575-118">Remarks</span><span class="sxs-lookup"><span data-stu-id="b7575-118">Remarks</span></span>  
 <span data-ttu-id="b7575-119">`<include>` タグを使用して、ソース コード内の型とメンバーを記述する別のファイル内のコメントを参照します。</span><span class="sxs-lookup"><span data-stu-id="b7575-119">Use the `<include>` tag to refer to comments in another file that describe the types and members in your source code.</span></span> <span data-ttu-id="b7575-120">これは文書化のコメントをソース コード ファイル内に直接配置する方法の代替です。</span><span class="sxs-lookup"><span data-stu-id="b7575-120">This is an alternative to placing documentation comments directly in your source code file.</span></span>  
  
 <span data-ttu-id="b7575-121">`<include>` タグでは、W3C XML Path Language (XPath) Version 1.0 勧告が使用されています。</span><span class="sxs-lookup"><span data-stu-id="b7575-121">The `<include>` tag uses the W3C XML Path Language (XPath) Version 1.0 Recommendation.</span></span> <span data-ttu-id="b7575-122">`<include>` の使用をカスタマイズする方法の詳細については、「<https://www.w3.org/TR/xpath>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b7575-122">For more information about ways to customize your `<include>` use, see <https://www.w3.org/TR/xpath>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b7575-123">例</span><span class="sxs-lookup"><span data-stu-id="b7575-123">Example</span></span>  
 <span data-ttu-id="b7575-124">この例では、`<include>` タグを使用して、`commentFile.xml` というファイルからメンバー ドキュメント コメントをインポートします。</span><span class="sxs-lookup"><span data-stu-id="b7575-124">This example uses the `<include>` tag to import member documentation comments from a file called `commentFile.xml`.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#4)]  
  
 <span data-ttu-id="b7575-125">`commentFile.xml` の形式を次に示します。</span><span class="sxs-lookup"><span data-stu-id="b7575-125">The format of the `commentFile.xml` is as follows.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b7575-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="b7575-126">See also</span></span>

- [<span data-ttu-id="b7575-127">XML のコメント用タグ</span><span class="sxs-lookup"><span data-stu-id="b7575-127">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
