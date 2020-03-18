---
title: <permission> - C# プログラミング ガイド
ms.date: 07/20/2015
f1_keywords:
- permission
- <permission>
helpviewer_keywords:
- <permission> C# XML tag
- permission C# XML tag
ms.assetid: 769e93fe-8404-443f-bf99-577aa42b6a49
ms.openlocfilehash: 4f76d28d5531c1b9f01fa950589407934cc1244a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "77093475"
---
# <a name="permission-c-programming-guide"></a><span data-ttu-id="31df2-102">\<permission> (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="31df2-102">\<permission> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="31df2-103">構文</span><span class="sxs-lookup"><span data-stu-id="31df2-103">Syntax</span></span>

```xml
<permission cref="member">description</permission>
```

## <a name="parameters"></a><span data-ttu-id="31df2-104">パラメーター</span><span class="sxs-lookup"><span data-stu-id="31df2-104">Parameters</span></span>

- <span data-ttu-id="31df2-105">cref = "`member`"</span><span class="sxs-lookup"><span data-stu-id="31df2-105">cref = " `member`"</span></span>

  <span data-ttu-id="31df2-106">現在のコンパイル環境からの呼び出しに利用できる、メンバーまたはフィールドへの参照。</span><span class="sxs-lookup"><span data-stu-id="31df2-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="31df2-107">コンパイラは、指定されたコード要素が存在し、出力の XML で `member` が正規要素名に変換されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="31df2-107">The compiler checks that the given code element exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="31df2-108">*member* は、二重引用符 (" ") で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="31df2-108">*member* must appear within double quotation marks (" ").</span></span>

  <span data-ttu-id="31df2-109">ジェネリック型への cref 参照を作成する方法については、[cref 属性](./cref-attribute.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="31df2-109">For information on how to create a cref reference to a generic type, see [cref attribute](./cref-attribute.md).</span></span>

- `description`

  <span data-ttu-id="31df2-110">メンバーへのアクセスの説明です。</span><span class="sxs-lookup"><span data-stu-id="31df2-110">A description of the access to the member.</span></span>

## <a name="remarks"></a><span data-ttu-id="31df2-111">解説</span><span class="sxs-lookup"><span data-stu-id="31df2-111">Remarks</span></span>

<span data-ttu-id="31df2-112">\<permission> タグを使用すると、メンバーのアクセスを文書化できます。</span><span class="sxs-lookup"><span data-stu-id="31df2-112">The \<permission> tag lets you document the access of a member.</span></span> <span data-ttu-id="31df2-113"><xref:System.Security.PermissionSet> クラスを使用すると、メンバーへのアクセスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="31df2-113">The <xref:System.Security.PermissionSet> class lets you specify access to a member.</span></span>

<span data-ttu-id="31df2-114">コンパイル時に [-doc](../../language-reference/compiler-options/doc-compiler-option.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="31df2-114">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="31df2-115">例</span><span class="sxs-lookup"><span data-stu-id="31df2-115">Example</span></span>

[!code-csharp[csProgGuideDocComments#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#8)]

## <a name="see-also"></a><span data-ttu-id="31df2-116">参照</span><span class="sxs-lookup"><span data-stu-id="31df2-116">See also</span></span>

- [<span data-ttu-id="31df2-117">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="31df2-117">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="31df2-118">ドキュメント コメント用の推奨タグ</span><span class="sxs-lookup"><span data-stu-id="31df2-118">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
