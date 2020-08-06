---
title: <seealso> - C# プログラミング ガイド
description: XML タグを使用する方法について説明 <seealso> します。 このタグを使用して、「関連項目」セクションに表示するテキストを指定することができます。
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
ms.openlocfilehash: e8618ef352a4fa7f0fd4c88733c6568b0e12e376
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2020
ms.locfileid: "87380645"
---
# <a name="seealso-c-programming-guide"></a><span data-ttu-id="5da52-105">\<seealso> (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="5da52-105">\<seealso> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="5da52-106">構文</span><span class="sxs-lookup"><span data-stu-id="5da52-106">Syntax</span></span>

```xml
<seealso cref="member"/>
```

## <a name="parameters"></a><span data-ttu-id="5da52-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5da52-107">Parameters</span></span>

- <span data-ttu-id="5da52-108">cref = "`member`"</span><span class="sxs-lookup"><span data-stu-id="5da52-108">cref = " `member`"</span></span>

  <span data-ttu-id="5da52-109">現在のコンパイル環境からの呼び出しに利用できる、メンバーまたはフィールドへの参照。</span><span class="sxs-lookup"><span data-stu-id="5da52-109">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="5da52-110">コンパイラは、指定されたコード要素が存在するかどうかを確認し、`member` を出力 XML 内の要素名に渡します。`member`</span><span class="sxs-lookup"><span data-stu-id="5da52-110">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.`member`</span></span> <span data-ttu-id="5da52-111">は二重引用符 (" ") で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="5da52-111">must appear within double quotation marks (" ").</span></span>

  <span data-ttu-id="5da52-112">ジェネリック型への cref 参照を作成する方法については、[cref 属性](./cref-attribute.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5da52-112">For information on how to create a cref reference to a generic type, see [cref attribute](./cref-attribute.md).</span></span>

## <a name="remarks"></a><span data-ttu-id="5da52-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="5da52-113">Remarks</span></span>

<span data-ttu-id="5da52-114">`<seealso>` タグを使用して、「関連項目」セクションに表示するテキストを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="5da52-114">The `<seealso>` tag lets you specify the text that you might want to appear in a See Also section.</span></span> <span data-ttu-id="5da52-115">[\<see>](./see.md) を使用すると、テキスト内からリンクを指定できます。</span><span class="sxs-lookup"><span data-stu-id="5da52-115">Use [\<see>](./see.md) to specify a link from within text.</span></span>

<span data-ttu-id="5da52-116">コンパイル時に [-doc](../../language-reference/compiler-options/doc-compiler-option.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="5da52-116">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="5da52-117">例</span><span class="sxs-lookup"><span data-stu-id="5da52-117">Example</span></span>

<span data-ttu-id="5da52-118">\<seealso> の使用例については、[\<summary>](./summary.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5da52-118">See [\<summary>](./summary.md) for an example of using \<seealso>.</span></span>

## <a name="see-also"></a><span data-ttu-id="5da52-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="5da52-119">See also</span></span>

- [<span data-ttu-id="5da52-120">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="5da52-120">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="5da52-121">ドキュメント コメント用の推奨タグ</span><span class="sxs-lookup"><span data-stu-id="5da52-121">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
