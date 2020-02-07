---
title: <seealso> - C# プログラミング ガイド
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
ms.openlocfilehash: ad22b423d085a152f47c4e34d7ee4247ef9836b8
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789680"
---
# <a name="seealso-c-programming-guide"></a><span data-ttu-id="bc6e5-102">\<seealso> (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="bc6e5-102">\<seealso> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="bc6e5-103">構文</span><span class="sxs-lookup"><span data-stu-id="bc6e5-103">Syntax</span></span>

```xml
<seealso cref="member"/>
```

## <a name="parameters"></a><span data-ttu-id="bc6e5-104">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bc6e5-104">Parameters</span></span>

- <span data-ttu-id="bc6e5-105">cref = "`member`"</span><span class="sxs-lookup"><span data-stu-id="bc6e5-105">cref = " `member`"</span></span>

  <span data-ttu-id="bc6e5-106">現在のコンパイル環境からの呼び出しに利用できる、メンバーまたはフィールドへの参照。</span><span class="sxs-lookup"><span data-stu-id="bc6e5-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="bc6e5-107">コンパイラは、指定されたコード要素が存在するかどうかを確認し、`member` を出力 XML 内の要素名に渡します。`member`</span><span class="sxs-lookup"><span data-stu-id="bc6e5-107">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.`member`</span></span> <span data-ttu-id="bc6e5-108">は二重引用符 (" ") で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc6e5-108">must appear within double quotation marks (" ").</span></span>

  <span data-ttu-id="bc6e5-109">ジェネリック型への cref 参照を作成する方法については、「[\<see>](./see.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bc6e5-109">For information on how to create a cref reference to a generic type, see [\<see>](./see.md).</span></span>

## <a name="remarks"></a><span data-ttu-id="bc6e5-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="bc6e5-110">Remarks</span></span>

<span data-ttu-id="bc6e5-111">\<seealso > タグを使用して、「See Also」セクションに表示するテキストを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="bc6e5-111">The \<seealso> tag lets you specify the text that you might want to appear in a See Also section.</span></span> <span data-ttu-id="bc6e5-112">[\<see>](./see.md) タグを使用すると、テキスト内からリンクを指定できます。</span><span class="sxs-lookup"><span data-stu-id="bc6e5-112">Use [\<see>](./see.md) to specify a link from within text.</span></span>

<span data-ttu-id="bc6e5-113">コンパイル時に [-doc](../../language-reference/compiler-options/doc-compiler-option.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="bc6e5-113">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="bc6e5-114">例</span><span class="sxs-lookup"><span data-stu-id="bc6e5-114">Example</span></span>

<span data-ttu-id="bc6e5-115">\<seealso> の使用例については、[\<summary>](./summary.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bc6e5-115">See [\<summary>](./summary.md) for an example of using \<seealso>.</span></span>

## <a name="see-also"></a><span data-ttu-id="bc6e5-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="bc6e5-116">See also</span></span>

- [<span data-ttu-id="bc6e5-117">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="bc6e5-117">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="bc6e5-118">ドキュメント コメント用の推奨タグ</span><span class="sxs-lookup"><span data-stu-id="bc6e5-118">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
