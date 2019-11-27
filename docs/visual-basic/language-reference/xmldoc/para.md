---
title: <para>
ms.date: 07/20/2015
helpviewer_keywords:
- <para> XML tag
- para XML tag
ms.assetid: a3a18b6c-6416-4358-94ec-37b22675fd37
ms.openlocfilehash: 8f28ecc33eea99150509bb4bade047489b4b826b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352300"
---
# <a name="para-visual-basic"></a><span data-ttu-id="cd83e-101">\<の段落 > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cd83e-101">\<para> (Visual Basic)</span></span>
<span data-ttu-id="cd83e-102">コンテンツが段落として書式設定されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="cd83e-102">Specifies that the content is formatted as a paragraph.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd83e-103">構文</span><span class="sxs-lookup"><span data-stu-id="cd83e-103">Syntax</span></span>  
  
```xml  
<para>content</para>  
```  
  
## <a name="parameters"></a><span data-ttu-id="cd83e-104">パラメーター</span><span class="sxs-lookup"><span data-stu-id="cd83e-104">Parameters</span></span>  
 `content`  
 <span data-ttu-id="cd83e-105">段落のテキストです。</span><span class="sxs-lookup"><span data-stu-id="cd83e-105">The text of the paragraph.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cd83e-106">コメント</span><span class="sxs-lookup"><span data-stu-id="cd83e-106">Remarks</span></span>  
 <span data-ttu-id="cd83e-107">`<para>` タグは、 [\<概要 >](../../../visual-basic/language-reference/xmldoc/summary.md)、 [\<解説 >](../../../visual-basic/language-reference/xmldoc/remarks.md)、 [\<返す](../../../visual-basic/language-reference/xmldoc/returns.md)> など、タグ内で使用するためのものであり、テキストに構造を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="cd83e-107">The `<para>` tag is for use inside a tag, such as [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md), [\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md), or [\<returns>](../../../visual-basic/language-reference/xmldoc/returns.md), and lets you add structure to the text.</span></span>  
  
 <span data-ttu-id="cd83e-108">コンパイル時に [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="cd83e-108">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cd83e-109">例</span><span class="sxs-lookup"><span data-stu-id="cd83e-109">Example</span></span>  
 <span data-ttu-id="cd83e-110">この例では、`<para>` タグを使用して、`UpdateRecord` メソッドの解説セクションを2つの段落に分割します。</span><span class="sxs-lookup"><span data-stu-id="cd83e-110">This example uses the `<para>` tag to split the remarks section for the `UpdateRecord` method into two paragraphs.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="cd83e-111">参照</span><span class="sxs-lookup"><span data-stu-id="cd83e-111">See also</span></span>

- [<span data-ttu-id="cd83e-112">XML のコメント用タグ</span><span class="sxs-lookup"><span data-stu-id="cd83e-112">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
