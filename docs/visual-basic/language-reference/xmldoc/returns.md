---
title: <returns>
ms.date: 07/20/2015
helpviewer_keywords:
- returns XML tag
- <returns> XML tag
ms.assetid: a03a6469-d907-425d-882f-083187950e7e
ms.openlocfilehash: 62f70ae7f40fa3cde9492563b7bd14dfa5940a5f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352242"
---
# <a name="returns-visual-basic"></a><span data-ttu-id="bfbe7-101">\<returns> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bfbe7-101">\<returns> (Visual Basic)</span></span>
<span data-ttu-id="bfbe7-102">プロパティまたは関数の戻り値を指定します。</span><span class="sxs-lookup"><span data-stu-id="bfbe7-102">Specifies the return value of the property or function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfbe7-103">構文</span><span class="sxs-lookup"><span data-stu-id="bfbe7-103">Syntax</span></span>  
  
```xml  
<returns>description</returns>  
```  
  
## <a name="parameters"></a><span data-ttu-id="bfbe7-104">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bfbe7-104">Parameters</span></span>  
 `description`  
 <span data-ttu-id="bfbe7-105">戻り値の説明。</span><span class="sxs-lookup"><span data-stu-id="bfbe7-105">A description of the return value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bfbe7-106">コメント</span><span class="sxs-lookup"><span data-stu-id="bfbe7-106">Remarks</span></span>  
 <span data-ttu-id="bfbe7-107">メソッド宣言のコメントにある `<returns>` タグを使用して、戻り値を記述します。</span><span class="sxs-lookup"><span data-stu-id="bfbe7-107">Use the `<returns>` tag in the comment for a method declaration to describe the return value.</span></span>  
  
 <span data-ttu-id="bfbe7-108">コンパイル時に [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="bfbe7-108">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bfbe7-109">例</span><span class="sxs-lookup"><span data-stu-id="bfbe7-109">Example</span></span>  
 <span data-ttu-id="bfbe7-110">この例では、`<returns>` タグを使用して、`DoesRecordExist` 関数が返す内容を説明します。</span><span class="sxs-lookup"><span data-stu-id="bfbe7-110">This example uses the `<returns>` tag to explain what the `DoesRecordExist` function returns.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="bfbe7-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="bfbe7-111">See also</span></span>

- [<span data-ttu-id="bfbe7-112">XML のコメント用タグ</span><span class="sxs-lookup"><span data-stu-id="bfbe7-112">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
