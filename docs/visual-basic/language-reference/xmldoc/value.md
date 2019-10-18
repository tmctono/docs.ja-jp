---
title: <value> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <value> XML tag
- value XML tag
ms.assetid: 0b84b02e-9e6d-41b5-a926-0d5dc76dacb5
ms.openlocfilehash: 516ff6ba534478d066b8ca06baee46bdd4b35265
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524609"
---
# <a name="value-visual-basic"></a><span data-ttu-id="4b7d9-102">\<value > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4b7d9-102">\<value> (Visual Basic)</span></span>
<span data-ttu-id="4b7d9-103">プロパティの説明を指定します。</span><span class="sxs-lookup"><span data-stu-id="4b7d9-103">Specifies the description of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b7d9-104">構文</span><span class="sxs-lookup"><span data-stu-id="4b7d9-104">Syntax</span></span>  
  
```xml  
<value>property-description</value>  
```  
  
## <a name="parameters"></a><span data-ttu-id="4b7d9-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4b7d9-105">Parameters</span></span>  
 `property-description`  
 <span data-ttu-id="4b7d9-106">プロパティの説明。</span><span class="sxs-lookup"><span data-stu-id="4b7d9-106">A description for the property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4b7d9-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="4b7d9-107">Remarks</span></span>  
 <span data-ttu-id="4b7d9-108">プロパティを記述するには、`<value>` タグを使用します。</span><span class="sxs-lookup"><span data-stu-id="4b7d9-108">Use the `<value>` tag to describe a property.</span></span> <span data-ttu-id="4b7d9-109">Visual Studio 開発環境でコードウィザードを使用してプロパティを追加すると、新しいプロパティの[\<summary >](../../../visual-basic/language-reference/xmldoc/summary.md)タグが追加されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="4b7d9-109">Note that when you add a property using the code wizard in the Visual Studio development environment, it will add a [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md) tag for the new property.</span></span> <span data-ttu-id="4b7d9-110">次に、プロパティが表す値を記述する `<value>` タグを手動で追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b7d9-110">You should then manually add a `<value>` tag to describe the value that the property represents.</span></span>  
  
 <span data-ttu-id="4b7d9-111">コンパイル時に [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="4b7d9-111">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4b7d9-112">例</span><span class="sxs-lookup"><span data-stu-id="4b7d9-112">Example</span></span>  
 <span data-ttu-id="4b7d9-113">この例では、`<value>` タグを使用して、`Counter` プロパティに保持されている値を記述します。</span><span class="sxs-lookup"><span data-stu-id="4b7d9-113">This example uses the `<value>` tag to describe what value the `Counter` property holds.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="4b7d9-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="4b7d9-114">See also</span></span>

- [<span data-ttu-id="4b7d9-115">XML のコメント用タグ</span><span class="sxs-lookup"><span data-stu-id="4b7d9-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
