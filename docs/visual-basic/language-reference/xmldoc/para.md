---
title: <para>
ms.date: 07/20/2015
helpviewer_keywords:
- <para> XML tag
- para XML tag
ms.assetid: a3a18b6c-6416-4358-94ec-37b22675fd37
ms.openlocfilehash: 0e2051d1b00b881c06082b3af483890d8595899f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400074"
---
# <a name="para-visual-basic"></a><span data-ttu-id="e6931-101">\<para> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e6931-101">\<para> (Visual Basic)</span></span>
<span data-ttu-id="e6931-102">コンテンツが段落として書式設定されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="e6931-102">Specifies that the content is formatted as a paragraph.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6931-103">構文</span><span class="sxs-lookup"><span data-stu-id="e6931-103">Syntax</span></span>  
  
```xml  
<para>content</para>  
```  
  
## <a name="parameters"></a><span data-ttu-id="e6931-104">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e6931-104">Parameters</span></span>  
 `content`  
 <span data-ttu-id="e6931-105">段落のテキストです。</span><span class="sxs-lookup"><span data-stu-id="e6931-105">The text of the paragraph.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e6931-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="e6931-106">Remarks</span></span>  
 <span data-ttu-id="e6931-107">`<para>` タグは、[\<summary>](summary.md)、[\<remarks>](remarks.md)、または [\<returns>](returns.md) などのタグ内で使用します。このタグを使用すると、テキストに構造を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="e6931-107">The `<para>` tag is for use inside a tag, such as [\<summary>](summary.md), [\<remarks>](remarks.md), or [\<returns>](returns.md), and lets you add structure to the text.</span></span>  
  
 <span data-ttu-id="e6931-108">コンパイル時に [-doc](../../reference/command-line-compiler/doc.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="e6931-108">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e6931-109">例</span><span class="sxs-lookup"><span data-stu-id="e6931-109">Example</span></span>  
 <span data-ttu-id="e6931-110">この例では、`<para>` タグを使用して、`UpdateRecord` メソッドの解説セクションを 2 つの段落に分割します。</span><span class="sxs-lookup"><span data-stu-id="e6931-110">This example uses the `<para>` tag to split the remarks section for the `UpdateRecord` method into two paragraphs.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="e6931-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="e6931-111">See also</span></span>

- [<span data-ttu-id="e6931-112">XML のコメント用タグ</span><span class="sxs-lookup"><span data-stu-id="e6931-112">XML Comment Tags</span></span>](index.md)
