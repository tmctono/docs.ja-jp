---
title: <code>
ms.date: 07/20/2015
helpviewer_keywords:
- code XML tag
- <code> XML tag
ms.assetid: 925e5342-be05-45f2-bf66-7398bbd6710e
ms.openlocfilehash: d058663213cf02f2142bff740aeec1b60791362c
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873031"
---
# <a name="code-visual-basic"></a><span data-ttu-id="597b6-101">\<code> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="597b6-101">\<code> (Visual Basic)</span></span>

<span data-ttu-id="597b6-102">テキストが複数コード行であることを示します。</span><span class="sxs-lookup"><span data-stu-id="597b6-102">Indicates that the text is multiple lines of code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="597b6-103">構文</span><span class="sxs-lookup"><span data-stu-id="597b6-103">Syntax</span></span>  
  
```xml  
<code>content</code>  
```  
  
## <a name="parameters"></a><span data-ttu-id="597b6-104">パラメーター</span><span class="sxs-lookup"><span data-stu-id="597b6-104">Parameters</span></span>  

 `content`  
 <span data-ttu-id="597b6-105">コードとしてマークするテキスト。</span><span class="sxs-lookup"><span data-stu-id="597b6-105">The text to mark as code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="597b6-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="597b6-106">Remarks</span></span>  

 <span data-ttu-id="597b6-107">`<code>` タグを使用して、複数行をコードとして指定します。</span><span class="sxs-lookup"><span data-stu-id="597b6-107">Use the `<code>` tag to indicate multiple lines as code.</span></span> <span data-ttu-id="597b6-108">説明内のテキストをコードとしてマークする場合は、[\<c>](c.md) を使用します。</span><span class="sxs-lookup"><span data-stu-id="597b6-108">Use [\<c>](c.md) to indicate that text within a description should be marked as code.</span></span>  
  
 <span data-ttu-id="597b6-109">コンパイル時に [-doc](../../reference/command-line-compiler/doc.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="597b6-109">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="597b6-110">例</span><span class="sxs-lookup"><span data-stu-id="597b6-110">Example</span></span>  

 <span data-ttu-id="597b6-111">この例では、\<code> タグを使用して、`ID` フィールドを使用するためのコード例を追加します。</span><span class="sxs-lookup"><span data-stu-id="597b6-111">This example uses the \<code> tag to include example code for using the `ID` field.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="597b6-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="597b6-112">See also</span></span>

- [<span data-ttu-id="597b6-113">XML のコメント用タグ</span><span class="sxs-lookup"><span data-stu-id="597b6-113">XML Comment Tags</span></span>](index.md)
