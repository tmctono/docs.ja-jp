---
title: <remarks> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <remarks> XML tag
- remarks XML tag
ms.assetid: c6241773-a7ed-41c9-9a8b-9722a0c606a9
ms.openlocfilehash: 38549b2fcce0740b2b9cfd42d950e56b343e7a30
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524670"
---
# <a name="remarks-visual-basic"></a><span data-ttu-id="9ad6f-102">\<remarks > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9ad6f-102">\<remarks> (Visual Basic)</span></span>
<span data-ttu-id="9ad6f-103">メンバーの解説セクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="9ad6f-103">Specifies a remarks section for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ad6f-104">構文</span><span class="sxs-lookup"><span data-stu-id="9ad6f-104">Syntax</span></span>  
  
```xml  
<remarks>description</remarks>  
```  
  
## <a name="parameters"></a><span data-ttu-id="9ad6f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9ad6f-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="9ad6f-106">メンバーの説明。</span><span class="sxs-lookup"><span data-stu-id="9ad6f-106">A description of the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9ad6f-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="9ad6f-107">Remarks</span></span>  
 <span data-ttu-id="9ad6f-108">@No__t_0 タグを使用して、 [\<summary >](../../../visual-basic/language-reference/xmldoc/summary.md)で指定された情報を補足する、型に関する情報を追加します。</span><span class="sxs-lookup"><span data-stu-id="9ad6f-108">Use the `<remarks>` tag to add information about a type, supplementing the information specified with [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md).</span></span>  
  
 <span data-ttu-id="9ad6f-109">この情報はオブジェクトブラウザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="9ad6f-109">This information appears in the Object Browser.</span></span> <span data-ttu-id="9ad6f-110">オブジェクトブラウザーの詳細については、「[コードの構造の表示](/visualstudio/ide/viewing-the-structure-of-code)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ad6f-110">For information about the Object Browser, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="9ad6f-111">コンパイル時に [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="9ad6f-111">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9ad6f-112">例</span><span class="sxs-lookup"><span data-stu-id="9ad6f-112">Example</span></span>  
 <span data-ttu-id="9ad6f-113">この例では、`<remarks>` タグを使用して、`UpdateRecord` メソッドの動作を説明します。</span><span class="sxs-lookup"><span data-stu-id="9ad6f-113">This example uses the `<remarks>` tag to explain what the `UpdateRecord` method does.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="9ad6f-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="9ad6f-114">See also</span></span>

- [<span data-ttu-id="9ad6f-115">XML のコメント用タグ</span><span class="sxs-lookup"><span data-stu-id="9ad6f-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
