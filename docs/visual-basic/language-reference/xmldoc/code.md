---
title: <code>
ms.date: 07/20/2015
helpviewer_keywords:
- code XML tag
- <code> XML tag
ms.assetid: 925e5342-be05-45f2-bf66-7398bbd6710e
ms.openlocfilehash: 1cbac2162bd39cdc8af9a55dfd6e2f90bc40b08a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74354322"
---
# <a name="code-visual-basic"></a><span data-ttu-id="da365-101">\<コード > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="da365-101">\<code> (Visual Basic)</span></span>
<span data-ttu-id="da365-102">テキストが複数行のコードであることを示します。</span><span class="sxs-lookup"><span data-stu-id="da365-102">Indicates that the text is multiple lines of code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da365-103">構文</span><span class="sxs-lookup"><span data-stu-id="da365-103">Syntax</span></span>  
  
```xml  
<code>content</code>  
```  
  
## <a name="parameters"></a><span data-ttu-id="da365-104">パラメーター</span><span class="sxs-lookup"><span data-stu-id="da365-104">Parameters</span></span>  
 `content`  
 <span data-ttu-id="da365-105">コードとしてマークするテキスト。</span><span class="sxs-lookup"><span data-stu-id="da365-105">The text to mark as code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="da365-106">コメント</span><span class="sxs-lookup"><span data-stu-id="da365-106">Remarks</span></span>  
 <span data-ttu-id="da365-107">複数行をコードとして示すには、`<code>` タグを使用します。</span><span class="sxs-lookup"><span data-stu-id="da365-107">Use the `<code>` tag to indicate multiple lines as code.</span></span> <span data-ttu-id="da365-108">説明内のテキストをコードとしてマークする場合は、[\<c](../../../visual-basic/language-reference/xmldoc/c.md) タグを使用します。</span><span class="sxs-lookup"><span data-stu-id="da365-108">Use [\<c>](../../../visual-basic/language-reference/xmldoc/c.md) to indicate that text within a description should be marked as code.</span></span>  
  
 <span data-ttu-id="da365-109">コンパイル時に [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="da365-109">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="da365-110">例</span><span class="sxs-lookup"><span data-stu-id="da365-110">Example</span></span>  
 <span data-ttu-id="da365-111">この例では、\<コード > タグを使用して、`ID` フィールドを使用するためのコード例を含めます。</span><span class="sxs-lookup"><span data-stu-id="da365-111">This example uses the \<code> tag to include example code for using the `ID` field.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="da365-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="da365-112">See also</span></span>

- [<span data-ttu-id="da365-113">XML のコメント用タグ</span><span class="sxs-lookup"><span data-stu-id="da365-113">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
