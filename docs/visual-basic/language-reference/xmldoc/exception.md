---
title: <exception>
ms.date: 07/20/2015
helpviewer_keywords:
- <exception> XML tag
- exception XML tag
ms.assetid: c0517549-171e-4dae-ab88-a9c1700b6eee
ms.openlocfilehash: 3a2452ec60a2182adfee365777d9824001ff006a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400125"
---
# <a name="exception-visual-basic"></a><span data-ttu-id="723ef-101">\<exception> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="723ef-101">\<exception> (Visual Basic)</span></span>
<span data-ttu-id="723ef-102">スローできる例外を指定します。</span><span class="sxs-lookup"><span data-stu-id="723ef-102">Specifies which exceptions can be thrown.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="723ef-103">構文</span><span class="sxs-lookup"><span data-stu-id="723ef-103">Syntax</span></span>  
  
```xml  
<exception cref="member">description</exception>  
```  
  
## <a name="parameters"></a><span data-ttu-id="723ef-104">パラメーター</span><span class="sxs-lookup"><span data-stu-id="723ef-104">Parameters</span></span>  
 `member`  
 <span data-ttu-id="723ef-105">現在のコンパイル環境から使用できる例外の参照。</span><span class="sxs-lookup"><span data-stu-id="723ef-105">A reference to an exception that is available from the current compilation environment.</span></span> <span data-ttu-id="723ef-106">コンパイラは、指定された例外が存在し、出力の XML で `member` が正規要素名に変換されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="723ef-106">The compiler checks that the given exception exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="723ef-107">`member` は、二重引用符 (" ") で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="723ef-107">`member` must appear within double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="723ef-108">説明です。</span><span class="sxs-lookup"><span data-stu-id="723ef-108">A description.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="723ef-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="723ef-109">Remarks</span></span>  
 <span data-ttu-id="723ef-110">`<exception>` タグを使用して、スローできる例外を指定します。</span><span class="sxs-lookup"><span data-stu-id="723ef-110">Use the `<exception>` tag to specify which exceptions can be thrown.</span></span> <span data-ttu-id="723ef-111">このタグは、メソッドの定義に適用されます。</span><span class="sxs-lookup"><span data-stu-id="723ef-111">This tag is applied to a method definition.</span></span>  
  
 <span data-ttu-id="723ef-112">コンパイル時に [-doc](../../reference/command-line-compiler/doc.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="723ef-112">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="723ef-113">例</span><span class="sxs-lookup"><span data-stu-id="723ef-113">Example</span></span>  
 <span data-ttu-id="723ef-114">この例では、`<exception>` タグを使用して、`IntDivide` 関数がスローできる例外を記述します。</span><span class="sxs-lookup"><span data-stu-id="723ef-114">This example uses the `<exception>` tag to describe an exception that the `IntDivide` function can throw.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="723ef-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="723ef-115">See also</span></span>

- [<span data-ttu-id="723ef-116">XML のコメント用タグ</span><span class="sxs-lookup"><span data-stu-id="723ef-116">XML Comment Tags</span></span>](index.md)
