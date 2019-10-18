---
title: <summary> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <summary> XML tag
- summary XML tag
ms.assetid: 861c847d-dd94-478a-aa23-bf4899cdc848
ms.openlocfilehash: 25a0b307756401bed4d4c77d3668c2af53ba8b42
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524632"
---
# <a name="summary-visual-basic"></a><span data-ttu-id="65586-102">\<summary > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="65586-102">\<summary> (Visual Basic)</span></span>
<span data-ttu-id="65586-103">メンバーの概要を指定します。</span><span class="sxs-lookup"><span data-stu-id="65586-103">Specifies the summary of the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65586-104">構文</span><span class="sxs-lookup"><span data-stu-id="65586-104">Syntax</span></span>  
  
```xml  
<summary>description</summary>  
```  
  
## <a name="parameters"></a><span data-ttu-id="65586-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="65586-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="65586-106">オブジェクトの概要。</span><span class="sxs-lookup"><span data-stu-id="65586-106">A summary of the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="65586-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="65586-107">Remarks</span></span>  
 <span data-ttu-id="65586-108">型または型のメンバーを記述するには、`<summary>` タグを使用します。</span><span class="sxs-lookup"><span data-stu-id="65586-108">Use the `<summary>` tag to describe a type or a type member.</span></span> <span data-ttu-id="65586-109">型の説明に補足情報を追加するには、[\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md) タグを使用します。</span><span class="sxs-lookup"><span data-stu-id="65586-109">Use [\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md) to add supplemental information to a type description.</span></span>  
  
 <span data-ttu-id="65586-110">@No__t_0 タグのテキストは、IntelliSense の型に関する唯一の情報源であり、オブジェクトブラウザーにも表示されます。</span><span class="sxs-lookup"><span data-stu-id="65586-110">The text for the `<summary>` tag is the only source of information about the type in IntelliSense, and is also displayed in the Object Browser.</span></span> <span data-ttu-id="65586-111">オブジェクトブラウザーの詳細については、「[コードの構造の表示](/visualstudio/ide/viewing-the-structure-of-code)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65586-111">For information about the Object Browser, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="65586-112">コンパイル時に [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="65586-112">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="65586-113">例</span><span class="sxs-lookup"><span data-stu-id="65586-113">Example</span></span>  
 <span data-ttu-id="65586-114">この例では、`<summary>` タグを使用して、`ResetCounter` メソッドと `Counter` プロパティを記述します。</span><span class="sxs-lookup"><span data-stu-id="65586-114">This example uses the `<summary>` tag to describe the `ResetCounter` method and `Counter` property.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="65586-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="65586-115">See also</span></span>

- [<span data-ttu-id="65586-116">XML のコメント用タグ</span><span class="sxs-lookup"><span data-stu-id="65586-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
