---
title: <paramref>
ms.date: 07/20/2015
helpviewer_keywords:
- paramref XML tag
- <paramref> XML tag
ms.assetid: 8979d53b-beb1-41b7-b41e-6bbea1c17a03
ms.openlocfilehash: 78227a17584271f91283198e95f5aa389b3ef14b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352280"
---
# <a name="paramref-visual-basic"></a><span data-ttu-id="027be-101">\<paramref > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="027be-101">\<paramref> (Visual Basic)</span></span>
<span data-ttu-id="027be-102">単語をパラメーターとして書式設定します。</span><span class="sxs-lookup"><span data-stu-id="027be-102">Formats a word as a parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="027be-103">構文</span><span class="sxs-lookup"><span data-stu-id="027be-103">Syntax</span></span>  
  
```xml  
<paramref name="name"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="027be-104">パラメーター</span><span class="sxs-lookup"><span data-stu-id="027be-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="027be-105">参照されるパラメーターの名前です。</span><span class="sxs-lookup"><span data-stu-id="027be-105">The name of the parameter to refer to.</span></span> <span data-ttu-id="027be-106">名前は二重引用符 (" ") で囲みます。</span><span class="sxs-lookup"><span data-stu-id="027be-106">Enclose the name in double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="027be-107">コメント</span><span class="sxs-lookup"><span data-stu-id="027be-107">Remarks</span></span>  
 <span data-ttu-id="027be-108">`<paramref>` タグを使用すると、単語がパラメーターであることを示すことができます。</span><span class="sxs-lookup"><span data-stu-id="027be-108">The `<paramref>` tag gives you a way to indicate that a word is a parameter.</span></span> <span data-ttu-id="027be-109">XML ファイルを処理して、このパラメーターを別の方法で書式設定することができます。</span><span class="sxs-lookup"><span data-stu-id="027be-109">The XML file can be processed to format this parameter in some distinct way.</span></span>  
  
 <span data-ttu-id="027be-110">コンパイル時に [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="027be-110">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="027be-111">例</span><span class="sxs-lookup"><span data-stu-id="027be-111">Example</span></span>  
 <span data-ttu-id="027be-112">この例では、`<paramref>` タグを使用して、`id` パラメーターを参照します。</span><span class="sxs-lookup"><span data-stu-id="027be-112">This example uses the `<paramref>` tag to refer to the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="027be-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="027be-113">See also</span></span>

- [<span data-ttu-id="027be-114">XML のコメント用タグ</span><span class="sxs-lookup"><span data-stu-id="027be-114">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
