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
ms.openlocfilehash: d16070a82531519dd276b2ea999623017769d716
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "76789760"
---
# <a name="param-c-programming-guide"></a><span data-ttu-id="37293-102">\<param> (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="37293-102">\<param> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="37293-103">構文</span><span class="sxs-lookup"><span data-stu-id="37293-103">Syntax</span></span>

```xml
<param name="name">description</param>
```

## <a name="parameters"></a><span data-ttu-id="37293-104">パラメーター</span><span class="sxs-lookup"><span data-stu-id="37293-104">Parameters</span></span>

- `name`

  <span data-ttu-id="37293-105">メソッド パラメーターの名前です。</span><span class="sxs-lookup"><span data-stu-id="37293-105">The name of a method parameter.</span></span> <span data-ttu-id="37293-106">名前は二重引用符 (" ") で囲みます。</span><span class="sxs-lookup"><span data-stu-id="37293-106">Enclose the name in double quotation marks (" ").</span></span>

- `description`

  <span data-ttu-id="37293-107">パラメーターの説明です。</span><span class="sxs-lookup"><span data-stu-id="37293-107">A description for the parameter.</span></span>

## <a name="remarks"></a><span data-ttu-id="37293-108">解説</span><span class="sxs-lookup"><span data-stu-id="37293-108">Remarks</span></span>

<span data-ttu-id="37293-109">\<param> タグは、メソッドのいずれか 1 つのパラメーターを説明するためにメソッドの宣言のコメントで使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="37293-109">The \<param> tag should be used in the comment for a method declaration to describe one of the parameters for the method.</span></span> <span data-ttu-id="37293-110">複数のパラメーターをドキュメント化するには、複数の \<param> タグを使用します。</span><span class="sxs-lookup"><span data-stu-id="37293-110">To document multiple parameters, use multiple \<param> tags.</span></span>

<span data-ttu-id="37293-111">\<param> タグのテキストは、IntelliSense、オブジェクト ブラウザー、コード コメント Web レポートに表示されます。</span><span class="sxs-lookup"><span data-stu-id="37293-111">The text for the \<param> tag will be displayed in IntelliSense, the Object Browser, and in the Code Comment Web Report.</span></span>

<span data-ttu-id="37293-112">コンパイル時に [-doc](../../language-reference/compiler-options/doc-compiler-option.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="37293-112">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="37293-113">例</span><span class="sxs-lookup"><span data-stu-id="37293-113">Example</span></span>

[!code-csharp[csProgGuideDocComments#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#1)]

## <a name="see-also"></a><span data-ttu-id="37293-114">参照</span><span class="sxs-lookup"><span data-stu-id="37293-114">See also</span></span>

- [<span data-ttu-id="37293-115">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="37293-115">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="37293-116">ドキュメント コメント用の推奨タグ</span><span class="sxs-lookup"><span data-stu-id="37293-116">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
