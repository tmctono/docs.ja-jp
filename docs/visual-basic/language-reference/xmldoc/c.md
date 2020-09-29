---
title: <c>
ms.date: 07/20/2015
helpviewer_keywords:
- c XML tag
- <c> XML tag
ms.assetid: 36ad5d1b-11f7-4012-8932-41962ac327d1
ms.openlocfilehash: 969df339eb766d2edb444ab5626af4e69accddba
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871701"
---
# <a name="c-visual-basic"></a><span data-ttu-id="83c80-101">\<c> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="83c80-101">\<c> (Visual Basic)</span></span>

<span data-ttu-id="83c80-102">説明内のテキストがコードであることを示します。</span><span class="sxs-lookup"><span data-stu-id="83c80-102">Indicates that text within a description is code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83c80-103">構文</span><span class="sxs-lookup"><span data-stu-id="83c80-103">Syntax</span></span>  
  
```xml  
<c>text</c>  
```  
  
## <a name="parameters"></a><span data-ttu-id="83c80-104">パラメーター</span><span class="sxs-lookup"><span data-stu-id="83c80-104">Parameters</span></span>  
  
|<span data-ttu-id="83c80-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="83c80-105">Parameter</span></span>|<span data-ttu-id="83c80-106">説明</span><span class="sxs-lookup"><span data-stu-id="83c80-106">Description</span></span>|  
|---|---|  
|`text`|<span data-ttu-id="83c80-107">コードとして指定するテキストです。</span><span class="sxs-lookup"><span data-stu-id="83c80-107">The text you would like to indicate as code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="83c80-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="83c80-108">Remarks</span></span>  

 <span data-ttu-id="83c80-109">`<c>` タグを使用すると、説明内のテキストをコードとしてマークする必要があることを指定できます。</span><span class="sxs-lookup"><span data-stu-id="83c80-109">The `<c>` tag gives you a way to indicate that text within a description should be marked as code.</span></span> <span data-ttu-id="83c80-110">複数行をコードとして示す場合は、[\<code>](code.md) を使用します。</span><span class="sxs-lookup"><span data-stu-id="83c80-110">Use [\<code>](code.md) to indicate multiple lines as code.</span></span>  
  
 <span data-ttu-id="83c80-111">コンパイル時に [-doc](../../reference/command-line-compiler/doc.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="83c80-111">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="83c80-112">例</span><span class="sxs-lookup"><span data-stu-id="83c80-112">Example</span></span>  

 <span data-ttu-id="83c80-113">この例では、summary セクションで `<c>` タグを使用して、`Counter` がコードであることを示します。</span><span class="sxs-lookup"><span data-stu-id="83c80-113">This example uses the `<c>` tag in the summary section to indicate that `Counter` is code.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="83c80-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="83c80-114">See also</span></span>

- [<span data-ttu-id="83c80-115">XML のコメント用タグ</span><span class="sxs-lookup"><span data-stu-id="83c80-115">XML Comment Tags</span></span>](index.md)
