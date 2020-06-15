---
title: <code>
ms.date: 07/20/2015
helpviewer_keywords:
- code XML tag
- <code> XML tag
ms.assetid: 925e5342-be05-45f2-bf66-7398bbd6710e
ms.openlocfilehash: aa65fed863718f1f00b510f82051a13e764e1b23
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400146"
---
# <a name="code-visual-basic"></a><span data-ttu-id="bcad8-101">\<code> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bcad8-101">\<code> (Visual Basic)</span></span>
<span data-ttu-id="bcad8-102">テキストが複数コード行であることを示します。</span><span class="sxs-lookup"><span data-stu-id="bcad8-102">Indicates that the text is multiple lines of code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bcad8-103">構文</span><span class="sxs-lookup"><span data-stu-id="bcad8-103">Syntax</span></span>  
  
```xml  
<code>content</code>  
```  
  
## <a name="parameters"></a><span data-ttu-id="bcad8-104">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bcad8-104">Parameters</span></span>  
 `content`  
 <span data-ttu-id="bcad8-105">コードとしてマークするテキスト。</span><span class="sxs-lookup"><span data-stu-id="bcad8-105">The text to mark as code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bcad8-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="bcad8-106">Remarks</span></span>  
 <span data-ttu-id="bcad8-107">`<code>` タグを使用して、複数行をコードとして指定します。</span><span class="sxs-lookup"><span data-stu-id="bcad8-107">Use the `<code>` tag to indicate multiple lines as code.</span></span> <span data-ttu-id="bcad8-108">説明内のテキストをコードとしてマークする場合は、[\<c>](c.md) を使用します。</span><span class="sxs-lookup"><span data-stu-id="bcad8-108">Use [\<c>](c.md) to indicate that text within a description should be marked as code.</span></span>  
  
 <span data-ttu-id="bcad8-109">コンパイル時に [-doc](../../reference/command-line-compiler/doc.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="bcad8-109">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bcad8-110">例</span><span class="sxs-lookup"><span data-stu-id="bcad8-110">Example</span></span>  
 <span data-ttu-id="bcad8-111">この例では、\<code> タグを使用して、`ID` フィールドを使用するためのコード例を追加します。</span><span class="sxs-lookup"><span data-stu-id="bcad8-111">This example uses the \<code> tag to include example code for using the `ID` field.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="bcad8-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="bcad8-112">See also</span></span>

- [<span data-ttu-id="bcad8-113">XML のコメント用タグ</span><span class="sxs-lookup"><span data-stu-id="bcad8-113">XML Comment Tags</span></span>](index.md)
