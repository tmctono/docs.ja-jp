---
title: <c> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- c XML tag
- <c> XML tag
ms.assetid: 36ad5d1b-11f7-4012-8932-41962ac327d1
ms.openlocfilehash: 4ea19ed5330dcbb8fcd84708d1546a81d909b04e
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2019
ms.locfileid: "72523941"
---
# <a name="c-visual-basic"></a><span data-ttu-id="6d937-102">\<c > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6d937-102">\<c> (Visual Basic)</span></span>
<span data-ttu-id="6d937-103">説明内のテキストがコードであることを示します。</span><span class="sxs-lookup"><span data-stu-id="6d937-103">Indicates that text within a description is code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d937-104">構文</span><span class="sxs-lookup"><span data-stu-id="6d937-104">Syntax</span></span>  
  
```xml  
<c>text</c>  
```  
  
## <a name="parameters"></a><span data-ttu-id="6d937-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6d937-105">Parameters</span></span>  
  
|<span data-ttu-id="6d937-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6d937-106">Parameter</span></span>|<span data-ttu-id="6d937-107">説明</span><span class="sxs-lookup"><span data-stu-id="6d937-107">Description</span></span>|  
|---|---|  
|`text`|<span data-ttu-id="6d937-108">コードとして指定するテキストです。</span><span class="sxs-lookup"><span data-stu-id="6d937-108">The text you would like to indicate as code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6d937-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="6d937-109">Remarks</span></span>  
 <span data-ttu-id="6d937-110">@No__t_0 タグを使用すると、説明内のテキストをコードとしてマークする必要があることを示すことができます。</span><span class="sxs-lookup"><span data-stu-id="6d937-110">The `<c>` tag gives you a way to indicate that text within a description should be marked as code.</span></span> <span data-ttu-id="6d937-111">複数行をコードとして指定する場合は、[\<code>](../../../visual-basic/language-reference/xmldoc/code.md) タグを使用します。</span><span class="sxs-lookup"><span data-stu-id="6d937-111">Use [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) to indicate multiple lines as code.</span></span>  
  
 <span data-ttu-id="6d937-112">コンパイル時に [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="6d937-112">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6d937-113">例</span><span class="sxs-lookup"><span data-stu-id="6d937-113">Example</span></span>  
 <span data-ttu-id="6d937-114">この例では、summary セクションの `<c>` タグを使用して、`Counter` がコードであることを示します。</span><span class="sxs-lookup"><span data-stu-id="6d937-114">This example uses the `<c>` tag in the summary section to indicate that `Counter` is code.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="6d937-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="6d937-115">See also</span></span>

- [<span data-ttu-id="6d937-116">XML のコメント用タグ</span><span class="sxs-lookup"><span data-stu-id="6d937-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
