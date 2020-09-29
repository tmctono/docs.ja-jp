---
title: <returns>
ms.date: 07/20/2015
helpviewer_keywords:
- returns XML tag
- <returns> XML tag
ms.assetid: a03a6469-d907-425d-882f-083187950e7e
ms.openlocfilehash: 37b110cc6e12f11196d2a1c5cc6026d87b453626
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90866401"
---
# <a name="returns-visual-basic"></a><span data-ttu-id="02c7d-101">\<returns> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="02c7d-101">\<returns> (Visual Basic)</span></span>

<span data-ttu-id="02c7d-102">プロパティまたは関数の戻り値を指定します。</span><span class="sxs-lookup"><span data-stu-id="02c7d-102">Specifies the return value of the property or function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02c7d-103">構文</span><span class="sxs-lookup"><span data-stu-id="02c7d-103">Syntax</span></span>  
  
```xml  
<returns>description</returns>  
```  
  
## <a name="parameters"></a><span data-ttu-id="02c7d-104">パラメーター</span><span class="sxs-lookup"><span data-stu-id="02c7d-104">Parameters</span></span>  

 `description`  
 <span data-ttu-id="02c7d-105">戻り値の説明。</span><span class="sxs-lookup"><span data-stu-id="02c7d-105">A description of the return value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="02c7d-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="02c7d-106">Remarks</span></span>  

 <span data-ttu-id="02c7d-107">メソッド宣言のコメントで `<returns>` タグを使用して、戻り値を記述します。</span><span class="sxs-lookup"><span data-stu-id="02c7d-107">Use the `<returns>` tag in the comment for a method declaration to describe the return value.</span></span>  
  
 <span data-ttu-id="02c7d-108">コンパイル時に [-doc](../../reference/command-line-compiler/doc.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="02c7d-108">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="02c7d-109">例</span><span class="sxs-lookup"><span data-stu-id="02c7d-109">Example</span></span>  

 <span data-ttu-id="02c7d-110">この例では、`<returns>` タグを使用して `DoesRecordExist` 関数が返す内容を説明します。</span><span class="sxs-lookup"><span data-stu-id="02c7d-110">This example uses the `<returns>` tag to explain what the `DoesRecordExist` function returns.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="02c7d-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="02c7d-111">See also</span></span>

- [<span data-ttu-id="02c7d-112">XML のコメント用タグ</span><span class="sxs-lookup"><span data-stu-id="02c7d-112">XML Comment Tags</span></span>](index.md)
