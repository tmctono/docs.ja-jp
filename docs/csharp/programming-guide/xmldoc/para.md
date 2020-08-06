---
title: <para> - C# プログラミング ガイド
description: 'XML タグについて説明 <para> します。 このタグを使用すると、次のような別のタグのテキストに構造を追加できます: <summary>, <remarks>、または <returns>.'
ms.date: 07/20/2015
f1_keywords:
- <para>
- para
helpviewer_keywords:
- <para> C# XML tag
- para C# XML tag
ms.assetid: c74b8705-29df-40b1-bff5-237492b0e978
ms.openlocfilehash: 146078bcb556b4085724ddcdac561ea868ab0481
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381854"
---
# <a name="para-c-programming-guide"></a><span data-ttu-id="d606f-108">\<para> (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="d606f-108">\<para> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="d606f-109">構文</span><span class="sxs-lookup"><span data-stu-id="d606f-109">Syntax</span></span>

```xml
<para>content</para>
```

## <a name="parameters"></a><span data-ttu-id="d606f-110">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d606f-110">Parameters</span></span>

- `content`

  <span data-ttu-id="d606f-111">段落のテキストです。</span><span class="sxs-lookup"><span data-stu-id="d606f-111">The text of the paragraph.</span></span>

## <a name="remarks"></a><span data-ttu-id="d606f-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="d606f-112">Remarks</span></span>

<span data-ttu-id="d606f-113">`<para>` タグは、[\<summary>](./summary.md)、[\<remarks>](./remarks.md)、または [\<returns>](./returns.md) などのタグ内で使用します。このタグを使用すると、テキストに構造を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="d606f-113">The `<para>` tag is for use inside a tag, such as [\<summary>](./summary.md), [\<remarks>](./remarks.md), or [\<returns>](./returns.md), and lets you add structure to the text.</span></span>

<span data-ttu-id="d606f-114">コンパイル時に [-doc](../../language-reference/compiler-options/doc-compiler-option.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="d606f-114">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="d606f-115">例</span><span class="sxs-lookup"><span data-stu-id="d606f-115">Example</span></span>

<span data-ttu-id="d606f-116">`<para>` の使用例については、[\<summary>](./summary.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d606f-116">See [\<summary>](./summary.md) for an example of using `<para>`.</span></span>

## <a name="see-also"></a><span data-ttu-id="d606f-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="d606f-117">See also</span></span>

- [<span data-ttu-id="d606f-118">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="d606f-118">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="d606f-119">ドキュメント コメント用の推奨タグ</span><span class="sxs-lookup"><span data-stu-id="d606f-119">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
