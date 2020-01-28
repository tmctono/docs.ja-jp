---
title: <remarks>
ms.date: 07/20/2015
helpviewer_keywords:
- <remarks> XML tag
- remarks XML tag
ms.assetid: c6241773-a7ed-41c9-9a8b-9722a0c606a9
ms.openlocfilehash: b327e548bcdce1522a888855bd88e3150695147b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352260"
---
# <a name="remarks-visual-basic"></a><span data-ttu-id="29b12-101">\<remarks> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="29b12-101">\<remarks> (Visual Basic)</span></span>
<span data-ttu-id="29b12-102">メンバーの解説セクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="29b12-102">Specifies a remarks section for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29b12-103">構文</span><span class="sxs-lookup"><span data-stu-id="29b12-103">Syntax</span></span>  
  
```xml  
<remarks>description</remarks>  
```  
  
## <a name="parameters"></a><span data-ttu-id="29b12-104">パラメーター</span><span class="sxs-lookup"><span data-stu-id="29b12-104">Parameters</span></span>  
 `description`  
 <span data-ttu-id="29b12-105">メンバーの説明。</span><span class="sxs-lookup"><span data-stu-id="29b12-105">A description of the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="29b12-106">コメント</span><span class="sxs-lookup"><span data-stu-id="29b12-106">Remarks</span></span>  
 <span data-ttu-id="29b12-107">`<remarks>` タグを使用して、 [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md)で指定された情報を補足する、型に関する情報を追加します。</span><span class="sxs-lookup"><span data-stu-id="29b12-107">Use the `<remarks>` tag to add information about a type, supplementing the information specified with [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md).</span></span>  
  
 <span data-ttu-id="29b12-108">この情報はオブジェクトブラウザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="29b12-108">This information appears in the Object Browser.</span></span> <span data-ttu-id="29b12-109">オブジェクトブラウザーの詳細については、「[コードの構造の表示](/visualstudio/ide/viewing-the-structure-of-code)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29b12-109">For information about the Object Browser, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="29b12-110">コンパイル時に [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="29b12-110">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="29b12-111">例</span><span class="sxs-lookup"><span data-stu-id="29b12-111">Example</span></span>  
 <span data-ttu-id="29b12-112">この例では、`<remarks>` タグを使用して、`UpdateRecord` メソッドの動作を説明します。</span><span class="sxs-lookup"><span data-stu-id="29b12-112">This example uses the `<remarks>` tag to explain what the `UpdateRecord` method does.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="29b12-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="29b12-113">See also</span></span>

- [<span data-ttu-id="29b12-114">XML のコメント用タグ</span><span class="sxs-lookup"><span data-stu-id="29b12-114">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
