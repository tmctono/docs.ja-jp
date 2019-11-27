---
title: <example>
ms.date: 07/20/2015
helpviewer_keywords:
- example XML tag
- <example> XML tag
ms.assetid: 90eeda1c-3fc4-427c-879c-5046d265a97c
ms.openlocfilehash: 8f36ac1337dd0d1400180fbd3deae2bb24ad9c58
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348481"
---
# <a name="example-visual-basic"></a><span data-ttu-id="d22f2-101">\<の例 > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d22f2-101">\<example> (Visual Basic)</span></span>
<span data-ttu-id="d22f2-102">メンバーの例を指定します。</span><span class="sxs-lookup"><span data-stu-id="d22f2-102">Specifies an example for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d22f2-103">構文</span><span class="sxs-lookup"><span data-stu-id="d22f2-103">Syntax</span></span>  
  
```xml  
<example>description</example>  
```  
  
## <a name="parameters"></a><span data-ttu-id="d22f2-104">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d22f2-104">Parameters</span></span>  
 `description`  
 <span data-ttu-id="d22f2-105">コード例の説明です。</span><span class="sxs-lookup"><span data-stu-id="d22f2-105">A description of the code sample.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d22f2-106">コメント</span><span class="sxs-lookup"><span data-stu-id="d22f2-106">Remarks</span></span>  
 <span data-ttu-id="d22f2-107">`<example>` タグを使用すると、メソッドまたはその他のライブラリメンバーを使用する方法の例を指定できます。</span><span class="sxs-lookup"><span data-stu-id="d22f2-107">The `<example>` tag lets you specify an example of how to use a method or other library member.</span></span> <span data-ttu-id="d22f2-108">一般的に、[\<code>](../../../visual-basic/language-reference/xmldoc/code.md) タグが使用されます。</span><span class="sxs-lookup"><span data-stu-id="d22f2-108">This commonly involves using the [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) tag.</span></span>  
  
 <span data-ttu-id="d22f2-109">コンパイル時に [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="d22f2-109">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d22f2-110">例</span><span class="sxs-lookup"><span data-stu-id="d22f2-110">Example</span></span>  
 <span data-ttu-id="d22f2-111">この例では、`<example>` タグを使用して、`ID` フィールドを使用する例を含めます。</span><span class="sxs-lookup"><span data-stu-id="d22f2-111">This example uses the `<example>` tag to include an example for using the `ID` field.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="d22f2-112">参照</span><span class="sxs-lookup"><span data-stu-id="d22f2-112">See also</span></span>

- [<span data-ttu-id="d22f2-113">XML のコメント用タグ</span><span class="sxs-lookup"><span data-stu-id="d22f2-113">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
