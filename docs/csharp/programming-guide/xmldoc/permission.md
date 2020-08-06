---
title: <permission> - C# プログラミング ガイド
description: XML タグについて説明 <permission> します。 このタグを使用すると、メンバーのアクセスをドキュメント化できます。一方、PermissionSet クラスを使用すると、メンバーへのアクセスを指定できます。
ms.date: 07/20/2015
f1_keywords:
- permission
- <permission>
helpviewer_keywords:
- <permission> C# XML tag
- permission C# XML tag
ms.assetid: 769e93fe-8404-443f-bf99-577aa42b6a49
ms.openlocfilehash: 38c87505b8b2973875e474ffd296dc02b7fb9de6
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381724"
---
# <a name="permission-c-programming-guide"></a><span data-ttu-id="e3ad0-105">\<permission> (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="e3ad0-105">\<permission> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="e3ad0-106">構文</span><span class="sxs-lookup"><span data-stu-id="e3ad0-106">Syntax</span></span>

```xml
<permission cref="member">description</permission>
```

## <a name="parameters"></a><span data-ttu-id="e3ad0-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e3ad0-107">Parameters</span></span>

- <span data-ttu-id="e3ad0-108">cref = "`member`"</span><span class="sxs-lookup"><span data-stu-id="e3ad0-108">cref = " `member`"</span></span>

  <span data-ttu-id="e3ad0-109">現在のコンパイル環境からの呼び出しに利用できる、メンバーまたはフィールドへの参照。</span><span class="sxs-lookup"><span data-stu-id="e3ad0-109">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="e3ad0-110">コンパイラは、指定されたコード要素が存在し、出力の XML で `member` が正規要素名に変換されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e3ad0-110">The compiler checks that the given code element exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="e3ad0-111">*member* は、二重引用符 (" ") で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3ad0-111">*member* must appear within double quotation marks (" ").</span></span>

  <span data-ttu-id="e3ad0-112">ジェネリック型への cref 参照を作成する方法については、[cref 属性](./cref-attribute.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3ad0-112">For information on how to create a cref reference to a generic type, see [cref attribute](./cref-attribute.md).</span></span>

- `description`

  <span data-ttu-id="e3ad0-113">メンバーへのアクセスの説明です。</span><span class="sxs-lookup"><span data-stu-id="e3ad0-113">A description of the access to the member.</span></span>

## <a name="remarks"></a><span data-ttu-id="e3ad0-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="e3ad0-114">Remarks</span></span>

<span data-ttu-id="e3ad0-115">`<permission>` タグを使用すると、メンバーのアクセスをドキュメント化できます。</span><span class="sxs-lookup"><span data-stu-id="e3ad0-115">The `<permission>` tag lets you document the access of a member.</span></span> <span data-ttu-id="e3ad0-116"><xref:System.Security.PermissionSet> クラスを使用すると、メンバーへのアクセスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="e3ad0-116">The <xref:System.Security.PermissionSet> class lets you specify access to a member.</span></span>

<span data-ttu-id="e3ad0-117">コンパイル時に [-doc](../../language-reference/compiler-options/doc-compiler-option.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="e3ad0-117">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="e3ad0-118">例</span><span class="sxs-lookup"><span data-stu-id="e3ad0-118">Example</span></span>

[!code-csharp[csProgGuideDocComments#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#8)]

## <a name="see-also"></a><span data-ttu-id="e3ad0-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="e3ad0-119">See also</span></span>

- [<span data-ttu-id="e3ad0-120">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="e3ad0-120">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="e3ad0-121">ドキュメント コメント用の推奨タグ</span><span class="sxs-lookup"><span data-stu-id="e3ad0-121">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
