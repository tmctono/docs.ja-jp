---
title: <value> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <value> XML tag
- value XML tag
ms.assetid: 0b84b02e-9e6d-41b5-a926-0d5dc76dacb5
ms.openlocfilehash: 89a2daad1c47ea8e2a045b2e22a9569e54086e8a
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2019
ms.locfileid: "56970741"
---
# <a name="value-visual-basic"></a><span data-ttu-id="25f5c-102">\<値 > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="25f5c-102">\<value> (Visual Basic)</span></span>
<span data-ttu-id="25f5c-103">プロパティの説明を指定します。</span><span class="sxs-lookup"><span data-stu-id="25f5c-103">Specifies the description of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25f5c-104">構文</span><span class="sxs-lookup"><span data-stu-id="25f5c-104">Syntax</span></span>  
  
```xml  
<value>property-description</value>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="25f5c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="25f5c-105">Parameters</span></span>  
 `property-description`  
 <span data-ttu-id="25f5c-106">プロパティの説明。</span><span class="sxs-lookup"><span data-stu-id="25f5c-106">A description for the property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="25f5c-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="25f5c-107">Remarks</span></span>  
 <span data-ttu-id="25f5c-108">使用して、`<value>`プロパティを説明するタグ。</span><span class="sxs-lookup"><span data-stu-id="25f5c-108">Use the `<value>` tag to describe a property.</span></span> <span data-ttu-id="25f5c-109">Visual Studio 開発環境で、コード ウィザードを使用してプロパティを追加すると、追加されることに注意してください、 [\<概要 >](../../../visual-basic/language-reference/xmldoc/summary.md)新しいプロパティのタグ。</span><span class="sxs-lookup"><span data-stu-id="25f5c-109">Note that when you add a property using the code wizard in the Visual Studio development environment, it will add a [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md) tag for the new property.</span></span> <span data-ttu-id="25f5c-110">手動で追加する必要がありますし、`<value>`プロパティを表す値を記述するタグ。</span><span class="sxs-lookup"><span data-stu-id="25f5c-110">You should then manually add a `<value>` tag to describe the value that the property represents.</span></span>  
  
 <span data-ttu-id="25f5c-111">コンパイル時に [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="25f5c-111">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="25f5c-112">例</span><span class="sxs-lookup"><span data-stu-id="25f5c-112">Example</span></span>  
 <span data-ttu-id="25f5c-113">この例では、`<value>`どのような値を記述するタグ、`Counter`プロパティを保持します。</span><span class="sxs-lookup"><span data-stu-id="25f5c-113">This example uses the `<value>` tag to describe what value the `Counter` property holds.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="25f5c-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="25f5c-114">See also</span></span>
- [<span data-ttu-id="25f5c-115">XML のコメント用タグ</span><span class="sxs-lookup"><span data-stu-id="25f5c-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
