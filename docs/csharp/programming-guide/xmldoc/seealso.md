---
title: <seealso> - C# プログラミング ガイド
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- cref
- <seealso>
- seealso
helpviewer_keywords:
- cref [C#], see also
- seealso C# XML tag
- cref [C#]
- cross-references [C#], tags
- <seealso> C# XML tag
ms.assetid: 8e157f3f-f220-4fcf-9010-88905b080b18
ms.openlocfilehash: 3ddaa7efec2b4bf5ffa53971aa6f380a1be9bad8
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2019
ms.locfileid: "69587664"
---
# <a name="seealso-c-programming-guide"></a><span data-ttu-id="e7576-102">\<seealso> (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="e7576-102">\<seealso> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="e7576-103">構文</span><span class="sxs-lookup"><span data-stu-id="e7576-103">Syntax</span></span>  
  
```xml  
<seealso cref="member"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="e7576-104">parameters</span><span class="sxs-lookup"><span data-stu-id="e7576-104">Parameters</span></span>  
 <span data-ttu-id="e7576-105">cref = "`member`"</span><span class="sxs-lookup"><span data-stu-id="e7576-105">cref = " `member`"</span></span>  
 <span data-ttu-id="e7576-106">現在のコンパイル環境からの呼び出しに利用できる、メンバーまたはフィールドへの参照。</span><span class="sxs-lookup"><span data-stu-id="e7576-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="e7576-107">コンパイラは、指定されたコード要素が存在するかどうかを確認し、`member` を出力 XML 内の要素名に渡します。`member`</span><span class="sxs-lookup"><span data-stu-id="e7576-107">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.`member`</span></span> <span data-ttu-id="e7576-108">は二重引用符 (" ") で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7576-108">must appear within double quotation marks (" ").</span></span>  
  
 <span data-ttu-id="e7576-109">ジェネリック型への cref 参照を作成する方法については、「[\<see>](./see.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e7576-109">For information on how to create a cref reference to a generic type, see [\<see>](./see.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e7576-110">解説</span><span class="sxs-lookup"><span data-stu-id="e7576-110">Remarks</span></span>  
 <span data-ttu-id="e7576-111">\<seealso > タグを使用して、「See Also」セクションに表示するテキストを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="e7576-111">The \<seealso> tag lets you specify the text that you might want to appear in a See Also section.</span></span> <span data-ttu-id="e7576-112">[\<see>](./see.md) タグを使用すると、テキスト内からリンクを指定できます。</span><span class="sxs-lookup"><span data-stu-id="e7576-112">Use [\<see>](./see.md) to specify a link from within text.</span></span>  
  
 <span data-ttu-id="e7576-113">コンパイル時に [/doc](../../language-reference/compiler-options/doc-compiler-option.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="e7576-113">Compile with [/doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e7576-114">例</span><span class="sxs-lookup"><span data-stu-id="e7576-114">Example</span></span>  
 <span data-ttu-id="e7576-115">\<seealso> の使用例については、[\<summary>](./summary.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e7576-115">See [\<summary>](./summary.md) for an example of using \<seealso>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7576-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="e7576-116">See also</span></span>

- [<span data-ttu-id="e7576-117">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="e7576-117">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="e7576-118">ドキュメント コメントとして推奨されるタグ</span><span class="sxs-lookup"><span data-stu-id="e7576-118">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
