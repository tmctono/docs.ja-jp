---
title: <example> - C# プログラミング ガイド
description: XML タグについて説明 <example> します。 このタグを使用すると、メソッドまたは他のライブラリ メンバーの使用例を指定できます。
ms.date: 07/20/2015
f1_keywords:
- <example>
- example
helpviewer_keywords:
- <example> C# XML tag
- example C# XML tag
ms.assetid: 32d6e73b-2554-4abb-83ee-a1e321334fd2
ms.openlocfilehash: dd529e8f2a54cf9086d0d8c555dd1adb70b99126
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381529"
---
# <a name="example-c-programming-guide"></a><span data-ttu-id="1bfb7-105">\<example> (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="1bfb7-105">\<example> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="1bfb7-106">構文</span><span class="sxs-lookup"><span data-stu-id="1bfb7-106">Syntax</span></span>

```xml
<example>description</example>
```

## <a name="parameters"></a><span data-ttu-id="1bfb7-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1bfb7-107">Parameters</span></span>

- `description`

  <span data-ttu-id="1bfb7-108">コード例の説明です。</span><span class="sxs-lookup"><span data-stu-id="1bfb7-108">A description of the code sample.</span></span>

## <a name="remarks"></a><span data-ttu-id="1bfb7-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="1bfb7-109">Remarks</span></span>

<span data-ttu-id="1bfb7-110">`<example>` タグを使用すると、メソッドまたは他のライブラリ メンバーの使用例を指定できます。</span><span class="sxs-lookup"><span data-stu-id="1bfb7-110">The `<example>` tag lets you specify an example of how to use a method or other library member.</span></span> <span data-ttu-id="1bfb7-111">一般的に、[\<code>](./code.md) タグが使用されます。</span><span class="sxs-lookup"><span data-stu-id="1bfb7-111">This commonly involves using the [\<code>](./code.md) tag.</span></span>

<span data-ttu-id="1bfb7-112">コンパイル時に [-doc](../../language-reference/compiler-options/doc-compiler-option.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="1bfb7-112">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="1bfb7-113">例</span><span class="sxs-lookup"><span data-stu-id="1bfb7-113">Example</span></span>

[!code-csharp[csProgGuideDocComments#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#3)]

## <a name="see-also"></a><span data-ttu-id="1bfb7-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="1bfb7-114">See also</span></span>

- [<span data-ttu-id="1bfb7-115">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="1bfb7-115">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="1bfb7-116">ドキュメント コメント用の推奨タグ</span><span class="sxs-lookup"><span data-stu-id="1bfb7-116">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
