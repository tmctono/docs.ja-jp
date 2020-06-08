---
title: <returns>
ms.date: 07/20/2015
helpviewer_keywords:
- returns XML tag
- <returns> XML tag
ms.assetid: a03a6469-d907-425d-882f-083187950e7e
ms.openlocfilehash: edbc374332bdcd67b385ac3d061045664e942460
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84399996"
---
# <a name="returns-visual-basic"></a><span data-ttu-id="2a1d9-101">\<returns> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2a1d9-101">\<returns> (Visual Basic)</span></span>
<span data-ttu-id="2a1d9-102">プロパティまたは関数の戻り値を指定します。</span><span class="sxs-lookup"><span data-stu-id="2a1d9-102">Specifies the return value of the property or function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a1d9-103">構文</span><span class="sxs-lookup"><span data-stu-id="2a1d9-103">Syntax</span></span>  
  
```xml  
<returns>description</returns>  
```  
  
## <a name="parameters"></a><span data-ttu-id="2a1d9-104">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2a1d9-104">Parameters</span></span>  
 `description`  
 <span data-ttu-id="2a1d9-105">戻り値の説明。</span><span class="sxs-lookup"><span data-stu-id="2a1d9-105">A description of the return value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2a1d9-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="2a1d9-106">Remarks</span></span>  
 <span data-ttu-id="2a1d9-107">メソッド宣言のコメントで `<returns>` タグを使用して、戻り値を記述します。</span><span class="sxs-lookup"><span data-stu-id="2a1d9-107">Use the `<returns>` tag in the comment for a method declaration to describe the return value.</span></span>  
  
 <span data-ttu-id="2a1d9-108">コンパイル時に [-doc](../../reference/command-line-compiler/doc.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="2a1d9-108">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2a1d9-109">例</span><span class="sxs-lookup"><span data-stu-id="2a1d9-109">Example</span></span>  
 <span data-ttu-id="2a1d9-110">この例では、`<returns>` タグを使用して `DoesRecordExist` 関数が返す内容を説明します。</span><span class="sxs-lookup"><span data-stu-id="2a1d9-110">This example uses the `<returns>` tag to explain what the `DoesRecordExist` function returns.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="2a1d9-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="2a1d9-111">See also</span></span>

- [<span data-ttu-id="2a1d9-112">XML のコメント用タグ</span><span class="sxs-lookup"><span data-stu-id="2a1d9-112">XML Comment Tags</span></span>](index.md)
