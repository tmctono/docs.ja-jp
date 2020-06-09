---
title: <param> - C# プログラミング ガイド
ms.date: 07/20/2015
f1_keywords:
- param
- <param>
helpviewer_keywords:
- <param> C# XML tag
- param C# XML tag
ms.assetid: 46d329b1-5b84-4537-9e17-73ca97313e4e
ms.openlocfilehash: 396ed716c246091a674268020261069f36dd2be8
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287325"
---
# <a name="param-c-programming-guide"></a><span data-ttu-id="86560-102">\<param> (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="86560-102">\<param> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="86560-103">構文</span><span class="sxs-lookup"><span data-stu-id="86560-103">Syntax</span></span>

```xml
<param name="name">description</param>
```

## <a name="parameters"></a><span data-ttu-id="86560-104">パラメーター</span><span class="sxs-lookup"><span data-stu-id="86560-104">Parameters</span></span>

- `name`

  <span data-ttu-id="86560-105">メソッド パラメーターの名前です。</span><span class="sxs-lookup"><span data-stu-id="86560-105">The name of a method parameter.</span></span> <span data-ttu-id="86560-106">名前は二重引用符 (" ") で囲みます。</span><span class="sxs-lookup"><span data-stu-id="86560-106">Enclose the name in double quotation marks (" ").</span></span>

- `description`

  <span data-ttu-id="86560-107">パラメーターの説明です。</span><span class="sxs-lookup"><span data-stu-id="86560-107">A description for the parameter.</span></span>

## <a name="remarks"></a><span data-ttu-id="86560-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="86560-108">Remarks</span></span>

<span data-ttu-id="86560-109">`<param>` タグは、メソッドのいずれかのパラメーターを記述するために、メソッド宣言のコメントで使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="86560-109">The `<param>` tag should be used in the comment for a method declaration to describe one of the parameters for the method.</span></span> <span data-ttu-id="86560-110">複数のパラメーターをドキュメント化するには、複数の `<param>` タグを使用します。</span><span class="sxs-lookup"><span data-stu-id="86560-110">To document multiple parameters, use multiple `<param>` tags.</span></span>

<span data-ttu-id="86560-111">`<param>` タグのテキストは、IntelliSense、オブジェクト ブラウザー、コード コメント Web レポートに表示されます。</span><span class="sxs-lookup"><span data-stu-id="86560-111">The text for the `<param>` tag is displayed in IntelliSense, the Object Browser, and the Code Comment Web Report.</span></span>

<span data-ttu-id="86560-112">コンパイル時に [-doc](../../language-reference/compiler-options/doc-compiler-option.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="86560-112">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="86560-113">例</span><span class="sxs-lookup"><span data-stu-id="86560-113">Example</span></span>

[!code-csharp[csProgGuideDocComments#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#1)]

## <a name="see-also"></a><span data-ttu-id="86560-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="86560-114">See also</span></span>

- [<span data-ttu-id="86560-115">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="86560-115">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="86560-116">ドキュメント コメント用の推奨タグ</span><span class="sxs-lookup"><span data-stu-id="86560-116">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
