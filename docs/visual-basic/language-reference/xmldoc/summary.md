---
title: <summary>
ms.date: 07/20/2015
helpviewer_keywords:
- <summary> XML tag
- summary XML tag
ms.assetid: 861c847d-dd94-478a-aa23-bf4899cdc848
ms.openlocfilehash: 893ed299b46bd6255ca0e87d008ac53265698614
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84411500"
---
# <a name="summary-visual-basic"></a><span data-ttu-id="945d0-101">\<summary> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="945d0-101">\<summary> (Visual Basic)</span></span>
<span data-ttu-id="945d0-102">メンバーの概要を指定します。</span><span class="sxs-lookup"><span data-stu-id="945d0-102">Specifies the summary of the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="945d0-103">構文</span><span class="sxs-lookup"><span data-stu-id="945d0-103">Syntax</span></span>  
  
```xml  
<summary>description</summary>  
```  
  
## <a name="parameters"></a><span data-ttu-id="945d0-104">パラメーター</span><span class="sxs-lookup"><span data-stu-id="945d0-104">Parameters</span></span>  
 `description`  
 <span data-ttu-id="945d0-105">オブジェクトの概要。</span><span class="sxs-lookup"><span data-stu-id="945d0-105">A summary of the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="945d0-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="945d0-106">Remarks</span></span>  
 <span data-ttu-id="945d0-107">`<summary>` タグを使用して、型または型メンバーを記述します。</span><span class="sxs-lookup"><span data-stu-id="945d0-107">Use the `<summary>` tag to describe a type or a type member.</span></span> <span data-ttu-id="945d0-108">型の説明に補足情報を追加するには、[\<remarks>](remarks.md) を使用します。</span><span class="sxs-lookup"><span data-stu-id="945d0-108">Use [\<remarks>](remarks.md) to add supplemental information to a type description.</span></span>  
  
 <span data-ttu-id="945d0-109">`<summary>` タグのテキストは、IntelliSense での型に関する唯一のソースで、オブジェクト ブラウザーにも表示されます。</span><span class="sxs-lookup"><span data-stu-id="945d0-109">The text for the `<summary>` tag is the only source of information about the type in IntelliSense, and is also displayed in the Object Browser.</span></span> <span data-ttu-id="945d0-110">オブジェクト ブラウザーについては、「[コードの構造の表示](/visualstudio/ide/viewing-the-structure-of-code)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="945d0-110">For information about the Object Browser, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="945d0-111">コンパイル時に [-doc](../../reference/command-line-compiler/doc.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="945d0-111">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="945d0-112">例</span><span class="sxs-lookup"><span data-stu-id="945d0-112">Example</span></span>  
 <span data-ttu-id="945d0-113">この例では、`<summary>` タグを使用して `ResetCounter` メソッドと `Counter` プロパティを記述します。</span><span class="sxs-lookup"><span data-stu-id="945d0-113">This example uses the `<summary>` tag to describe the `ResetCounter` method and `Counter` property.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="945d0-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="945d0-114">See also</span></span>

- [<span data-ttu-id="945d0-115">XML のコメント用タグ</span><span class="sxs-lookup"><span data-stu-id="945d0-115">XML Comment Tags</span></span>](index.md)
