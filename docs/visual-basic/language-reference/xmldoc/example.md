---
title: <example> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- example XML tag
- <example> XML tag
ms.assetid: 90eeda1c-3fc4-427c-879c-5046d265a97c
ms.openlocfilehash: 8f28dbf19bc03cb9d91323e9fa43a7081c1990db
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524005"
---
# <a name="example-visual-basic"></a><span data-ttu-id="dd90d-102">\<example > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dd90d-102">\<example> (Visual Basic)</span></span>
<span data-ttu-id="dd90d-103">メンバーの例を指定します。</span><span class="sxs-lookup"><span data-stu-id="dd90d-103">Specifies an example for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd90d-104">構文</span><span class="sxs-lookup"><span data-stu-id="dd90d-104">Syntax</span></span>  
  
```xml  
<example>description</example>  
```  
  
## <a name="parameters"></a><span data-ttu-id="dd90d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="dd90d-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="dd90d-106">コード例の説明です。</span><span class="sxs-lookup"><span data-stu-id="dd90d-106">A description of the code sample.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dd90d-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="dd90d-107">Remarks</span></span>  
 <span data-ttu-id="dd90d-108">@No__t_0 タグを使用すると、メソッドまたはその他のライブラリメンバーを使用する方法の例を指定できます。</span><span class="sxs-lookup"><span data-stu-id="dd90d-108">The `<example>` tag lets you specify an example of how to use a method or other library member.</span></span> <span data-ttu-id="dd90d-109">一般的に、[\<code>](../../../visual-basic/language-reference/xmldoc/code.md) タグが使用されます。</span><span class="sxs-lookup"><span data-stu-id="dd90d-109">This commonly involves using the [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) tag.</span></span>  
  
 <span data-ttu-id="dd90d-110">コンパイル時に [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="dd90d-110">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dd90d-111">例</span><span class="sxs-lookup"><span data-stu-id="dd90d-111">Example</span></span>  
 <span data-ttu-id="dd90d-112">この例では、`<example>` タグを使用して、`ID` フィールドを使用する例を含めます。</span><span class="sxs-lookup"><span data-stu-id="dd90d-112">This example uses the `<example>` tag to include an example for using the `ID` field.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="dd90d-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="dd90d-113">See also</span></span>

- [<span data-ttu-id="dd90d-114">XML のコメント用タグ</span><span class="sxs-lookup"><span data-stu-id="dd90d-114">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
