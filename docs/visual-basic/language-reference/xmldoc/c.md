---
title: <c>
ms.date: 07/20/2015
helpviewer_keywords:
- c XML tag
- <c> XML tag
ms.assetid: 36ad5d1b-11f7-4012-8932-41962ac327d1
ms.openlocfilehash: c8ba03d9cc01c4751d15c01530c6cbf7d499dc3b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400164"
---
# <a name="c-visual-basic"></a><span data-ttu-id="6aab0-101">\<c> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6aab0-101">\<c> (Visual Basic)</span></span>
<span data-ttu-id="6aab0-102">説明内のテキストがコードであることを示します。</span><span class="sxs-lookup"><span data-stu-id="6aab0-102">Indicates that text within a description is code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6aab0-103">構文</span><span class="sxs-lookup"><span data-stu-id="6aab0-103">Syntax</span></span>  
  
```xml  
<c>text</c>  
```  
  
## <a name="parameters"></a><span data-ttu-id="6aab0-104">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6aab0-104">Parameters</span></span>  
  
|<span data-ttu-id="6aab0-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6aab0-105">Parameter</span></span>|<span data-ttu-id="6aab0-106">説明</span><span class="sxs-lookup"><span data-stu-id="6aab0-106">Description</span></span>|  
|---|---|  
|`text`|<span data-ttu-id="6aab0-107">コードとして指定するテキストです。</span><span class="sxs-lookup"><span data-stu-id="6aab0-107">The text you would like to indicate as code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6aab0-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="6aab0-108">Remarks</span></span>  
 <span data-ttu-id="6aab0-109">`<c>` タグを使用すると、説明内のテキストをコードとしてマークする必要があることを指定できます。</span><span class="sxs-lookup"><span data-stu-id="6aab0-109">The `<c>` tag gives you a way to indicate that text within a description should be marked as code.</span></span> <span data-ttu-id="6aab0-110">複数行をコードとして示す場合は、[\<code>](code.md) を使用します。</span><span class="sxs-lookup"><span data-stu-id="6aab0-110">Use [\<code>](code.md) to indicate multiple lines as code.</span></span>  
  
 <span data-ttu-id="6aab0-111">コンパイル時に [-doc](../../reference/command-line-compiler/doc.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="6aab0-111">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6aab0-112">例</span><span class="sxs-lookup"><span data-stu-id="6aab0-112">Example</span></span>  
 <span data-ttu-id="6aab0-113">この例では、summary セクションで `<c>` タグを使用して、`Counter` がコードであることを示します。</span><span class="sxs-lookup"><span data-stu-id="6aab0-113">This example uses the `<c>` tag in the summary section to indicate that `Counter` is code.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="6aab0-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="6aab0-114">See also</span></span>

- [<span data-ttu-id="6aab0-115">XML のコメント用タグ</span><span class="sxs-lookup"><span data-stu-id="6aab0-115">XML Comment Tags</span></span>](index.md)
