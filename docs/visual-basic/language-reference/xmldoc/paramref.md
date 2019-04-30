---
title: <paramref> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- paramref XML tag
- <paramref> XML tag
ms.assetid: 8979d53b-beb1-41b7-b41e-6bbea1c17a03
ms.openlocfilehash: 3e2bf7990343a325bbecc56f6d3754a77f1e08e2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940843"
---
# <a name="paramref-visual-basic"></a><span data-ttu-id="63078-102">\<paramref > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="63078-102">\<paramref> (Visual Basic)</span></span>
<span data-ttu-id="63078-103">単語をパラメーターとして書式設定します。</span><span class="sxs-lookup"><span data-stu-id="63078-103">Formats a word as a parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63078-104">構文</span><span class="sxs-lookup"><span data-stu-id="63078-104">Syntax</span></span>  
  
```xml  
<paramref name="name"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="63078-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="63078-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="63078-106">参照されるパラメーターの名前です。</span><span class="sxs-lookup"><span data-stu-id="63078-106">The name of the parameter to refer to.</span></span> <span data-ttu-id="63078-107">名前は二重引用符 (" ") で囲みます。</span><span class="sxs-lookup"><span data-stu-id="63078-107">Enclose the name in double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="63078-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="63078-108">Remarks</span></span>  
 <span data-ttu-id="63078-109">`<paramref>`タグを使用する単語がパラメーターであることを示します。</span><span class="sxs-lookup"><span data-stu-id="63078-109">The `<paramref>` tag gives you a way to indicate that a word is a parameter.</span></span> <span data-ttu-id="63078-110">XML ファイルを処理することで、何らかの方法でこのパラメーターの書式を設定します。</span><span class="sxs-lookup"><span data-stu-id="63078-110">The XML file can be processed to format this parameter in some distinct way.</span></span>  
  
 <span data-ttu-id="63078-111">コンパイル時に [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="63078-111">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="63078-112">例</span><span class="sxs-lookup"><span data-stu-id="63078-112">Example</span></span>  
 <span data-ttu-id="63078-113">この例では、`<paramref>`タグを参照する、`id`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="63078-113">This example uses the `<paramref>` tag to refer to the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="63078-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="63078-114">See also</span></span>

- [<span data-ttu-id="63078-115">XML のコメント用タグ</span><span class="sxs-lookup"><span data-stu-id="63078-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
