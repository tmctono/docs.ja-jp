---
title: <see>
ms.date: 07/20/2015
helpviewer_keywords:
- see XML tag
- <see> XML tag
ms.assetid: 7e18f60b-ef4a-4678-a797-5eb918635ca9
ms.openlocfilehash: 380923c2313450afc5745b25eeea6a444705dd3f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84411526"
---
# <a name="see-visual-basic"></a><span data-ttu-id="51520-101">\<see> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="51520-101">\<see> (Visual Basic)</span></span>
<span data-ttu-id="51520-102">別のメンバーへのリンクを指定します。</span><span class="sxs-lookup"><span data-stu-id="51520-102">Specifies a link to another member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51520-103">構文</span><span class="sxs-lookup"><span data-stu-id="51520-103">Syntax</span></span>  
  
```xml  
<see cref="member"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="51520-104">パラメーター</span><span class="sxs-lookup"><span data-stu-id="51520-104">Parameters</span></span>  
 `member`  
 <span data-ttu-id="51520-105">現在のコンパイル環境からの呼び出しに利用できる、メンバーまたはフィールドへの参照。</span><span class="sxs-lookup"><span data-stu-id="51520-105">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="51520-106">コンパイラは、指定されたコード要素が存在するかどうかを確認し、`member` を出力 XML 内の要素名に渡します。</span><span class="sxs-lookup"><span data-stu-id="51520-106">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.</span></span> <span data-ttu-id="51520-107">`member` は、二重引用符 (" ") で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="51520-107">`member` must appear within double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="51520-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="51520-108">Remarks</span></span>  
 <span data-ttu-id="51520-109">`<see>` タグを使用して、テキスト内からリンクを指定します。</span><span class="sxs-lookup"><span data-stu-id="51520-109">Use the `<see>` tag to specify a link from within text.</span></span> <span data-ttu-id="51520-110">[\<seealso>](seealso.md) を使用して、"関連項目" セクションに表示するテキストを指定します。</span><span class="sxs-lookup"><span data-stu-id="51520-110">Use [\<seealso>](seealso.md) to indicate text that you might want to appear in a "See Also" section.</span></span>  
  
 <span data-ttu-id="51520-111">コンパイル時に [-doc](../../reference/command-line-compiler/doc.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="51520-111">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="51520-112">例</span><span class="sxs-lookup"><span data-stu-id="51520-112">Example</span></span>  
 <span data-ttu-id="51520-113">この例では、`UpdateRecord` 解説セクションの `<see>` タグを使用して、`DoesRecordExist` メソッドを参照します。</span><span class="sxs-lookup"><span data-stu-id="51520-113">This example uses the `<see>` tag in the `UpdateRecord` remarks section to refer to the `DoesRecordExist` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="51520-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="51520-114">See also</span></span>

- [<span data-ttu-id="51520-115">XML のコメント用タグ</span><span class="sxs-lookup"><span data-stu-id="51520-115">XML Comment Tags</span></span>](index.md)
