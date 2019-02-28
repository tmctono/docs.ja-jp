---
title: <returns> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- returns XML tag
- <returns> XML tag
ms.assetid: a03a6469-d907-425d-882f-083187950e7e
ms.openlocfilehash: 96b9754332b7b9c6c7823aecab6a93b0aa7ffd21
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2019
ms.locfileid: "56975460"
---
# <a name="returns-visual-basic"></a><span data-ttu-id="1212c-102">\<返します > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1212c-102">\<returns> (Visual Basic)</span></span>
<span data-ttu-id="1212c-103">プロパティまたは関数の戻り値を指定します。</span><span class="sxs-lookup"><span data-stu-id="1212c-103">Specifies the return value of the property or function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1212c-104">構文</span><span class="sxs-lookup"><span data-stu-id="1212c-104">Syntax</span></span>  
  
```xml  
<returns>description</returns>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1212c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1212c-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="1212c-106">戻り値の説明。</span><span class="sxs-lookup"><span data-stu-id="1212c-106">A description of the return value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1212c-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="1212c-107">Remarks</span></span>  
 <span data-ttu-id="1212c-108">使用して、`<returns>`戻り値を記述するメソッド宣言のコメント内のタグ。</span><span class="sxs-lookup"><span data-stu-id="1212c-108">Use the `<returns>` tag in the comment for a method declaration to describe the return value.</span></span>  
  
 <span data-ttu-id="1212c-109">コンパイル時に [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="1212c-109">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1212c-110">例</span><span class="sxs-lookup"><span data-stu-id="1212c-110">Example</span></span>  
 <span data-ttu-id="1212c-111">この例では、`<returns>`何かを説明するタグ、`DoesRecordExist`関数が返される。</span><span class="sxs-lookup"><span data-stu-id="1212c-111">This example uses the `<returns>` tag to explain what the `DoesRecordExist` function returns.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="1212c-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="1212c-112">See also</span></span>
- [<span data-ttu-id="1212c-113">XML のコメント用タグ</span><span class="sxs-lookup"><span data-stu-id="1212c-113">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
