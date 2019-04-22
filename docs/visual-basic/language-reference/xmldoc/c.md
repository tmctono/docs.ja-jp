---
title: <c> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- c XML tag
- <c> XML tag
ms.assetid: 36ad5d1b-11f7-4012-8932-41962ac327d1
ms.openlocfilehash: 9be9f9e96fc1b79ea97d54c54352da63b93ef264
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "58838041"
---
# <a name="c-visual-basic"></a><span data-ttu-id="eb0b6-102">\<c> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="eb0b6-102">\<c> (Visual Basic)</span></span>
<span data-ttu-id="eb0b6-103">説明内のテキストがコードであることを示します。</span><span class="sxs-lookup"><span data-stu-id="eb0b6-103">Indicates that text within a description is code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb0b6-104">構文</span><span class="sxs-lookup"><span data-stu-id="eb0b6-104">Syntax</span></span>  
  
```xml  
<c>text</c>  
```  
  
## <a name="parameters"></a><span data-ttu-id="eb0b6-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="eb0b6-105">Parameters</span></span>  
  
|<span data-ttu-id="eb0b6-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="eb0b6-106">Parameter</span></span>|<span data-ttu-id="eb0b6-107">説明</span><span class="sxs-lookup"><span data-stu-id="eb0b6-107">Description</span></span>|  
|---|---|  
|`text`|<span data-ttu-id="eb0b6-108">コードとして指定するテキストです。</span><span class="sxs-lookup"><span data-stu-id="eb0b6-108">The text you would like to indicate as code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eb0b6-109">コメント</span><span class="sxs-lookup"><span data-stu-id="eb0b6-109">Remarks</span></span>  
 <span data-ttu-id="eb0b6-110">`<c>`タグを使用する方法を示す説明内のテキストをコードとしてマークする必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb0b6-110">The `<c>` tag gives you a way to indicate that text within a description should be marked as code.</span></span> <span data-ttu-id="eb0b6-111">複数行をコードとして指定する場合は、[\<code>](../../../visual-basic/language-reference/xmldoc/code.md) タグを使用します。</span><span class="sxs-lookup"><span data-stu-id="eb0b6-111">Use [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) to indicate multiple lines as code.</span></span>  
  
 <span data-ttu-id="eb0b6-112">コンパイル時に [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="eb0b6-112">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eb0b6-113">例</span><span class="sxs-lookup"><span data-stu-id="eb0b6-113">Example</span></span>  
 <span data-ttu-id="eb0b6-114">この例では、`<c>`ことを示す [概要] セクションでタグ`Counter`コードに示します。</span><span class="sxs-lookup"><span data-stu-id="eb0b6-114">This example uses the `<c>` tag in the summary section to indicate that `Counter` is code.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="eb0b6-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="eb0b6-115">See also</span></span>

- [<span data-ttu-id="eb0b6-116">XML のコメント用タグ</span><span class="sxs-lookup"><span data-stu-id="eb0b6-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
