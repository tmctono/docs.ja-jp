---
title: <para> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <para> XML tag
- para XML tag
ms.assetid: a3a18b6c-6416-4358-94ec-37b22675fd37
ms.openlocfilehash: cbb8e3b1e67150473159835ba2cd58d9ddf0c1c1
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479011"
---
# <a name="para-visual-basic"></a><span data-ttu-id="d1814-102">\<para > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d1814-102">\<para> (Visual Basic)</span></span>
<span data-ttu-id="d1814-103">コンテンツが文章としてフォーマットされているを指定します。</span><span class="sxs-lookup"><span data-stu-id="d1814-103">Specifies that the content is formatted as a paragraph.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1814-104">構文</span><span class="sxs-lookup"><span data-stu-id="d1814-104">Syntax</span></span>  
  
```xml  
<para>content</para>  
```  
  
## <a name="parameters"></a><span data-ttu-id="d1814-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d1814-105">Parameters</span></span>  
 `content`  
 <span data-ttu-id="d1814-106">段落のテキストです。</span><span class="sxs-lookup"><span data-stu-id="d1814-106">The text of the paragraph.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d1814-107">コメント</span><span class="sxs-lookup"><span data-stu-id="d1814-107">Remarks</span></span>  
 <span data-ttu-id="d1814-108">`<para>`などは、タグの内側で使用するタグ[\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md)、 [\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md)、または[\<returns>](../../../visual-basic/language-reference/xmldoc/returns.md)、テキストに構造を追加することができます。  </span><span class="sxs-lookup"><span data-stu-id="d1814-108">The `<para>` tag is for use inside a tag, such as [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md), [\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md), or [\<returns>](../../../visual-basic/language-reference/xmldoc/returns.md), and lets you add structure to the text.</span></span>  
  
 <span data-ttu-id="d1814-109">コンパイル時に [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="d1814-109">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d1814-110">例</span><span class="sxs-lookup"><span data-stu-id="d1814-110">Example</span></span>  
 <span data-ttu-id="d1814-111">この例では、`<para>`の「解説」セクションに分割するタグ、`UpdateRecord`メソッドが 2 つの段落にします。</span><span class="sxs-lookup"><span data-stu-id="d1814-111">This example uses the `<para>` tag to split the remarks section for the `UpdateRecord` method into two paragraphs.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="d1814-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="d1814-112">See also</span></span>
- [<span data-ttu-id="d1814-113">XML のコメント用タグ</span><span class="sxs-lookup"><span data-stu-id="d1814-113">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
