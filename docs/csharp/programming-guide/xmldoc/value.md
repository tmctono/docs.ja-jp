---
title: <value> - C# プログラミング ガイド
ms.date: 07/20/2015
f1_keywords:
- <value>
helpviewer_keywords:
- <value> C# XML tag
- value C# XML tag
ms.assetid: 08dbadaf-9ab6-43d9-9493-98e43bed199a
ms.openlocfilehash: 120805346672738e614743ab8c98388b8dbac0f7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "76793346"
---
# <a name="value-c-programming-guide"></a><span data-ttu-id="47bdb-102">\<value> (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="47bdb-102">\<value> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="47bdb-103">構文</span><span class="sxs-lookup"><span data-stu-id="47bdb-103">Syntax</span></span>

```xml
<value>property-description</value>
```

## <a name="parameters"></a><span data-ttu-id="47bdb-104">パラメーター</span><span class="sxs-lookup"><span data-stu-id="47bdb-104">Parameters</span></span>

- `property-description`

  <span data-ttu-id="47bdb-105">プロパティの説明。</span><span class="sxs-lookup"><span data-stu-id="47bdb-105">A description for the property.</span></span>

## <a name="remarks"></a><span data-ttu-id="47bdb-106">解説</span><span class="sxs-lookup"><span data-stu-id="47bdb-106">Remarks</span></span>

<span data-ttu-id="47bdb-107">\<value> タグを使用して、プロパティが表す値を記述することができます。</span><span class="sxs-lookup"><span data-stu-id="47bdb-107">The \<value> tag lets you describe the value that a property represents.</span></span> <span data-ttu-id="47bdb-108">Visual Studio .NET 開発環境では、コード ウィザードを使用してプロパティを追加するときに、新しいプロパティの [\<summary>](./summary.md) タグが追加されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="47bdb-108">Note that when you add a property via code wizard in the Visual Studio .NET development environment, it will add a [\<summary>](./summary.md) tag for the new property.</span></span> <span data-ttu-id="47bdb-109">その後、手動で \<value> タグを追加してプロパティが表す値を記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="47bdb-109">You should then manually add a \<value> tag to describe the value that the property represents.</span></span>

<span data-ttu-id="47bdb-110">コンパイル時に [-doc](../../language-reference/compiler-options/doc-compiler-option.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="47bdb-110">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="47bdb-111">例</span><span class="sxs-lookup"><span data-stu-id="47bdb-111">Example</span></span>

[!code-csharp[csProgGuideDocComments#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#14)]

## <a name="see-also"></a><span data-ttu-id="47bdb-112">参照</span><span class="sxs-lookup"><span data-stu-id="47bdb-112">See also</span></span>

- [<span data-ttu-id="47bdb-113">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="47bdb-113">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="47bdb-114">ドキュメント コメント用の推奨タグ</span><span class="sxs-lookup"><span data-stu-id="47bdb-114">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
