---
title: <para> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <para> XML tag
- para XML tag
ms.assetid: a3a18b6c-6416-4358-94ec-37b22675fd37
ms.openlocfilehash: 16d10b2f955a4d9a02075ee4cc40dfa2b18c3541
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940873"
---
# <a name="para-visual-basic"></a><span data-ttu-id="1711d-102">\<para > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1711d-102">\<para> (Visual Basic)</span></span>
<span data-ttu-id="1711d-103">コンテンツが文章としてフォーマットされているを指定します。</span><span class="sxs-lookup"><span data-stu-id="1711d-103">Specifies that the content is formatted as a paragraph.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1711d-104">構文</span><span class="sxs-lookup"><span data-stu-id="1711d-104">Syntax</span></span>  
  
```xml  
<para>content</para>  
```  
  
## <a name="parameters"></a><span data-ttu-id="1711d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1711d-105">Parameters</span></span>  
 `content`  
 <span data-ttu-id="1711d-106">段落のテキストです。</span><span class="sxs-lookup"><span data-stu-id="1711d-106">The text of the paragraph.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1711d-107">コメント</span><span class="sxs-lookup"><span data-stu-id="1711d-107">Remarks</span></span>  
 <span data-ttu-id="1711d-108">`<para>`などは、タグの内側で使用するタグ[\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md)、 [\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md)、または[\<returns>](../../../visual-basic/language-reference/xmldoc/returns.md)、テキストに構造を追加することができます。  </span><span class="sxs-lookup"><span data-stu-id="1711d-108">The `<para>` tag is for use inside a tag, such as [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md), [\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md), or [\<returns>](../../../visual-basic/language-reference/xmldoc/returns.md), and lets you add structure to the text.</span></span>  
  
 <span data-ttu-id="1711d-109">コンパイル時に [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="1711d-109">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1711d-110">例</span><span class="sxs-lookup"><span data-stu-id="1711d-110">Example</span></span>  
 <span data-ttu-id="1711d-111">この例では、`<para>`の「解説」セクションに分割するタグ、`UpdateRecord`メソッドが 2 つの段落にします。</span><span class="sxs-lookup"><span data-stu-id="1711d-111">This example uses the `<para>` tag to split the remarks section for the `UpdateRecord` method into two paragraphs.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="1711d-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="1711d-112">See also</span></span>

- [<span data-ttu-id="1711d-113">XML のコメント用タグ</span><span class="sxs-lookup"><span data-stu-id="1711d-113">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
