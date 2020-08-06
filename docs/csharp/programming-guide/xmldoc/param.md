---
title: <param> - C# プログラミング ガイド
description: XML タグについて説明 <param> します。 このタグは、メソッド宣言のコメントで、メソッドのいずれかのパラメーターを記述するために使用されます。
ms.date: 07/20/2015
f1_keywords:
- param
- <param>
helpviewer_keywords:
- <param> C# XML tag
- param C# XML tag
ms.assetid: 46d329b1-5b84-4537-9e17-73ca97313e4e
ms.openlocfilehash: a9e3b2e86528afcbe1330788e248f0143efb5c1b
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381555"
---
# <a name="param-c-programming-guide"></a><span data-ttu-id="4fa76-105">\<param> (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="4fa76-105">\<param> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="4fa76-106">構文</span><span class="sxs-lookup"><span data-stu-id="4fa76-106">Syntax</span></span>

```xml
<param name="name">description</param>
```

## <a name="parameters"></a><span data-ttu-id="4fa76-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4fa76-107">Parameters</span></span>

- `name`

  <span data-ttu-id="4fa76-108">メソッド パラメーターの名前です。</span><span class="sxs-lookup"><span data-stu-id="4fa76-108">The name of a method parameter.</span></span> <span data-ttu-id="4fa76-109">名前は二重引用符 (" ") で囲みます。</span><span class="sxs-lookup"><span data-stu-id="4fa76-109">Enclose the name in double quotation marks (" ").</span></span>

- `description`

  <span data-ttu-id="4fa76-110">パラメーターの説明です。</span><span class="sxs-lookup"><span data-stu-id="4fa76-110">A description for the parameter.</span></span>

## <a name="remarks"></a><span data-ttu-id="4fa76-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="4fa76-111">Remarks</span></span>

<span data-ttu-id="4fa76-112">`<param>` タグは、メソッドのいずれかのパラメーターを記述するために、メソッド宣言のコメントで使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4fa76-112">The `<param>` tag should be used in the comment for a method declaration to describe one of the parameters for the method.</span></span> <span data-ttu-id="4fa76-113">複数のパラメーターをドキュメント化するには、複数の `<param>` タグを使用します。</span><span class="sxs-lookup"><span data-stu-id="4fa76-113">To document multiple parameters, use multiple `<param>` tags.</span></span>

<span data-ttu-id="4fa76-114">`<param>` タグのテキストは、IntelliSense、オブジェクト ブラウザー、コード コメント Web レポートに表示されます。</span><span class="sxs-lookup"><span data-stu-id="4fa76-114">The text for the `<param>` tag is displayed in IntelliSense, the Object Browser, and the Code Comment Web Report.</span></span>

<span data-ttu-id="4fa76-115">コンパイル時に [-doc](../../language-reference/compiler-options/doc-compiler-option.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="4fa76-115">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="4fa76-116">例</span><span class="sxs-lookup"><span data-stu-id="4fa76-116">Example</span></span>

[!code-csharp[csProgGuideDocComments#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#1)]

## <a name="see-also"></a><span data-ttu-id="4fa76-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="4fa76-117">See also</span></span>

- [<span data-ttu-id="4fa76-118">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="4fa76-118">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="4fa76-119">ドキュメント コメント用の推奨タグ</span><span class="sxs-lookup"><span data-stu-id="4fa76-119">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
