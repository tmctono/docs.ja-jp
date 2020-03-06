---
title: <see> - C# プログラミング ガイド
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
ms.openlocfilehash: f4834f88c646b44269f8290c2ad08698c34e714a
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2020
ms.locfileid: "77627673"
---
# <a name="see-c-programming-guide"></a><span data-ttu-id="7d918-102">\<see> (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="7d918-102">\<see> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="7d918-103">構文</span><span class="sxs-lookup"><span data-stu-id="7d918-103">Syntax</span></span>

```xml
<see cref="member"/>
```

## <a name="parameters"></a><span data-ttu-id="7d918-104">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7d918-104">Parameters</span></span>

- <span data-ttu-id="7d918-105">cref = "`member`"</span><span class="sxs-lookup"><span data-stu-id="7d918-105">cref = "`member`"</span></span>

  <span data-ttu-id="7d918-106">現在のコンパイル環境からの呼び出しに利用できる、メンバーまたはフィールドへの参照。</span><span class="sxs-lookup"><span data-stu-id="7d918-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="7d918-107">コンパイラは、指定されたコード要素が存在するかどうかを確認し、`member` を出力 XML 内の要素名に渡します。</span><span class="sxs-lookup"><span data-stu-id="7d918-107">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.</span></span> <span data-ttu-id="7d918-108">*メンバー*は二重引用符 (" ") で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d918-108">Place *member* within double quotation marks (" ").</span></span>

## <a name="remarks"></a><span data-ttu-id="7d918-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="7d918-109">Remarks</span></span>

<span data-ttu-id="7d918-110">\<see> タグを使用すると、テキスト内でリンクを指定できます。</span><span class="sxs-lookup"><span data-stu-id="7d918-110">The \<see> tag lets you specify a link from within text.</span></span> <span data-ttu-id="7d918-111">テキストが参照セクションに配置されていることを示すには、[\<seealso>](./seealso.md) を使用します。</span><span class="sxs-lookup"><span data-stu-id="7d918-111">Use [\<seealso>](./seealso.md) to indicate that text should be placed in a See Also section.</span></span> <span data-ttu-id="7d918-112">コード要素のドキュメント ページへの内部ハイパーリンクを作成するには、[cref 属性](./cref-attribute.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="7d918-112">Use the [cref Attribute](./cref-attribute.md) to create internal hyperlinks to documentation pages for code elements.</span></span>

<span data-ttu-id="7d918-113">コンパイル時に [-doc](../../language-reference/compiler-options/doc-compiler-option.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="7d918-113">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

<span data-ttu-id="7d918-114">次の例では、summary セクション内の \<see> タグを示しています。</span><span class="sxs-lookup"><span data-stu-id="7d918-114">The following example shows a \<see> tag within a summary section.</span></span>

[!code-csharp[csProgGuideDocComments#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#12)]

## <a name="see-also"></a><span data-ttu-id="7d918-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="7d918-115">See also</span></span>

- [<span data-ttu-id="7d918-116">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="7d918-116">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="7d918-117">ドキュメント コメント用の推奨タグ</span><span class="sxs-lookup"><span data-stu-id="7d918-117">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
