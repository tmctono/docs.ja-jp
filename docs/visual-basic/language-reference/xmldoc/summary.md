---
title: <summary> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <summary> XML tag
- summary XML tag
ms.assetid: 861c847d-dd94-478a-aa23-bf4899cdc848
ms.openlocfilehash: 0fbe07884f55b7e6f460929e54520de5f718e1af
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2019
ms.locfileid: "58815006"
---
# <a name="summary-visual-basic"></a><span data-ttu-id="3763c-102">\<概要 > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3763c-102">\<summary> (Visual Basic)</span></span>
<span data-ttu-id="3763c-103">メンバーの概要を指定します。</span><span class="sxs-lookup"><span data-stu-id="3763c-103">Specifies the summary of the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3763c-104">構文</span><span class="sxs-lookup"><span data-stu-id="3763c-104">Syntax</span></span>  
  
```xml  
<summary>description</summary>  
```  
  
## <a name="parameters"></a><span data-ttu-id="3763c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3763c-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="3763c-106">オブジェクトの概要。</span><span class="sxs-lookup"><span data-stu-id="3763c-106">A summary of the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3763c-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="3763c-107">Remarks</span></span>  
 <span data-ttu-id="3763c-108">使用して、`<summary>`型または型のメンバーを記述するタグ。</span><span class="sxs-lookup"><span data-stu-id="3763c-108">Use the `<summary>` tag to describe a type or a type member.</span></span> <span data-ttu-id="3763c-109">型の説明に補足情報を追加するには、[\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md) タグを使用します。</span><span class="sxs-lookup"><span data-stu-id="3763c-109">Use [\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md) to add supplemental information to a type description.</span></span>  
  
 <span data-ttu-id="3763c-110">テキスト、`<summary>`タグは IntelliSense の型に関する情報の唯一のソースであり、オブジェクト ブラウザーにも表示されます。</span><span class="sxs-lookup"><span data-stu-id="3763c-110">The text for the `<summary>` tag is the only source of information about the type in IntelliSense, and is also displayed in the Object Browser.</span></span> <span data-ttu-id="3763c-111">オブジェクト ブラウザーの詳細については、次を参照してください。[コードの構造を表示する](/visualstudio/ide/viewing-the-structure-of-code)します。</span><span class="sxs-lookup"><span data-stu-id="3763c-111">For information about the Object Browser, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="3763c-112">コンパイル時に [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="3763c-112">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3763c-113">例</span><span class="sxs-lookup"><span data-stu-id="3763c-113">Example</span></span>  
 <span data-ttu-id="3763c-114">この例では、`<summary>`を記述するタグ、`ResetCounter`メソッドと`Counter`プロパティ。</span><span class="sxs-lookup"><span data-stu-id="3763c-114">This example uses the `<summary>` tag to describe the `ResetCounter` method and `Counter` property.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="3763c-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="3763c-115">See also</span></span>

- [<span data-ttu-id="3763c-116">XML のコメント用タグ</span><span class="sxs-lookup"><span data-stu-id="3763c-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
