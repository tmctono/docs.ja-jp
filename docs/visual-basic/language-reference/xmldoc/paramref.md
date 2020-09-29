---
title: <paramref>
ms.date: 07/20/2015
helpviewer_keywords:
- paramref XML tag
- <paramref> XML tag
ms.assetid: 8979d53b-beb1-41b7-b41e-6bbea1c17a03
ms.openlocfilehash: d7aacc5faea22f9c5a4b865a32c832154fe624c5
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90872607"
---
# <a name="paramref-visual-basic"></a><span data-ttu-id="10f68-101">\<paramref> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="10f68-101">\<paramref> (Visual Basic)</span></span>

<span data-ttu-id="10f68-102">ワードをパラメーターとして書式設定します。</span><span class="sxs-lookup"><span data-stu-id="10f68-102">Formats a word as a parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10f68-103">構文</span><span class="sxs-lookup"><span data-stu-id="10f68-103">Syntax</span></span>  
  
```xml  
<paramref name="name"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="10f68-104">パラメーター</span><span class="sxs-lookup"><span data-stu-id="10f68-104">Parameters</span></span>  

 `name`  
 <span data-ttu-id="10f68-105">参照されるパラメーターの名前です。</span><span class="sxs-lookup"><span data-stu-id="10f68-105">The name of the parameter to refer to.</span></span> <span data-ttu-id="10f68-106">名前は二重引用符 (" ") で囲みます。</span><span class="sxs-lookup"><span data-stu-id="10f68-106">Enclose the name in double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="10f68-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="10f68-107">Remarks</span></span>  

 <span data-ttu-id="10f68-108">`<paramref>` タグは、単語がパラメーターであることを示す方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="10f68-108">The `<paramref>` tag gives you a way to indicate that a word is a parameter.</span></span> <span data-ttu-id="10f68-109">XML ファイルを処理することで、いくつかの独自の方法でこのパラメーターの書式設定を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="10f68-109">The XML file can be processed to format this parameter in some distinct way.</span></span>  
  
 <span data-ttu-id="10f68-110">コンパイル時に [-doc](../../reference/command-line-compiler/doc.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="10f68-110">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="10f68-111">例</span><span class="sxs-lookup"><span data-stu-id="10f68-111">Example</span></span>  

 <span data-ttu-id="10f68-112">この例では、`<paramref>` タグを使用して `id` パラメーターを参照します。</span><span class="sxs-lookup"><span data-stu-id="10f68-112">This example uses the `<paramref>` tag to refer to the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="10f68-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="10f68-113">See also</span></span>

- [<span data-ttu-id="10f68-114">XML のコメント用タグ</span><span class="sxs-lookup"><span data-stu-id="10f68-114">XML Comment Tags</span></span>](index.md)
