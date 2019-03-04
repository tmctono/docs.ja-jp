---
title: <see> - C# プログラミング ガイド
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- <see>
- see
helpviewer_keywords:
- cref [C#], <see> tag
- <see> C# XML tag
- cross-references [C#]
- see C# XML tag
ms.assetid: 0200de01-7e2f-45c4-9094-829d61236383
ms.openlocfilehash: 1816aeb0ddf783c8ad0baa7f5d460f0fc60747e1
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2019
ms.locfileid: "56974823"
---
# <a name="see-c-programming-guide"></a><span data-ttu-id="72604-102">\<see> (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="72604-102">\<see> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="72604-103">構文</span><span class="sxs-lookup"><span data-stu-id="72604-103">Syntax</span></span>  
  
```xml  
<see cref="member"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="72604-104">パラメーター</span><span class="sxs-lookup"><span data-stu-id="72604-104">Parameters</span></span>  
 <span data-ttu-id="72604-105">cref = "`member`"</span><span class="sxs-lookup"><span data-stu-id="72604-105">cref = " `member`"</span></span>  
 <span data-ttu-id="72604-106">現在のコンパイル環境からの呼び出しに利用できる、メンバーまたはフィールドへの参照。</span><span class="sxs-lookup"><span data-stu-id="72604-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="72604-107">コンパイラは、指定されたコード要素が存在するかどうかを確認し、`member` を出力 XML 内の要素名に渡します。</span><span class="sxs-lookup"><span data-stu-id="72604-107">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.</span></span> <span data-ttu-id="72604-108">*メンバー*は二重引用符 (" ") で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="72604-108">Place *member* within double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="72604-109">解説</span><span class="sxs-lookup"><span data-stu-id="72604-109">Remarks</span></span>  
 <span data-ttu-id="72604-110">\<see> タグを使用すると、テキスト内でリンクを指定できます。</span><span class="sxs-lookup"><span data-stu-id="72604-110">The \<see> tag lets you specify a link from within text.</span></span> <span data-ttu-id="72604-111">テキストが参照セクションに配置されていることを示すには、[\<seealso>](../../../csharp/programming-guide/xmldoc/seealso.md) を使用します。</span><span class="sxs-lookup"><span data-stu-id="72604-111">Use [\<seealso>](../../../csharp/programming-guide/xmldoc/seealso.md) to indicate that text should be placed in a See Also section.</span></span> <span data-ttu-id="72604-112">コード要素のドキュメント ページへの内部ハイパーリンクを作成するには、[cref 属性](../../../csharp/programming-guide/xmldoc/cref-attribute.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="72604-112">Use the [cref Attribute](../../../csharp/programming-guide/xmldoc/cref-attribute.md) to create internal hyperlinks to documentation pages for code elements.</span></span>  
  
 <span data-ttu-id="72604-113">コンパイル時に [-doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="72604-113">Compile with [-doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
 <span data-ttu-id="72604-114">次の例では、summary セクション内の \<see> タグを示しています。</span><span class="sxs-lookup"><span data-stu-id="72604-114">The following example shows a \<see> tag within a summary section.</span></span>  
  
 [!code-csharp[csProgGuideDocComments#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#12)]  
  
## <a name="see-also"></a><span data-ttu-id="72604-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="72604-115">See also</span></span>

- [<span data-ttu-id="72604-116">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="72604-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="72604-117">ドキュメント コメントとして推奨されるタグ</span><span class="sxs-lookup"><span data-stu-id="72604-117">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
