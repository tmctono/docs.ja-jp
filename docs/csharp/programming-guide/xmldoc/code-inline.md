---
title: <c> - C# プログラミング ガイド
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- c
- <c>
helpviewer_keywords:
- text, marking as code [C#]
- code, marking text as [C#]
- c C# XML tag
- <c> C# XML tag
ms.assetid: aad5b16e-a29e-445e-bd0d-eea0b138d7b2
ms.openlocfilehash: c881b9ec577fb04381f9e10c7df8f9d0da44cd66
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2019
ms.locfileid: "69588186"
---
# <a name="c-c-programming-guide"></a><span data-ttu-id="e6fc0-102">\<c> (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="e6fc0-102">\<c> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="e6fc0-103">構文</span><span class="sxs-lookup"><span data-stu-id="e6fc0-103">Syntax</span></span>  
  
```xml  
<c>text</c>  
```  
  
## <a name="parameters"></a><span data-ttu-id="e6fc0-104">parameters</span><span class="sxs-lookup"><span data-stu-id="e6fc0-104">Parameters</span></span>  
 `text`  
 <span data-ttu-id="e6fc0-105">コードとして指定するテキストです。</span><span class="sxs-lookup"><span data-stu-id="e6fc0-105">The text you would like to indicate as code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e6fc0-106">解説</span><span class="sxs-lookup"><span data-stu-id="e6fc0-106">Remarks</span></span>  
 <span data-ttu-id="e6fc0-107">\<c> タグを使用すると、説明内のテキストをコードとして指定できます。</span><span class="sxs-lookup"><span data-stu-id="e6fc0-107">The \<c> tag gives you a way to indicate that text within a description should be marked as code.</span></span> <span data-ttu-id="e6fc0-108">複数行をコードとして指定する場合は、[\<code>](./code.md) タグを使用します。</span><span class="sxs-lookup"><span data-stu-id="e6fc0-108">Use [\<code>](./code.md) to indicate multiple lines as code.</span></span>  
  
 <span data-ttu-id="e6fc0-109">コンパイル時に [/doc](../../language-reference/compiler-options/doc-compiler-option.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="e6fc0-109">Compile with [/doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e6fc0-110">例</span><span class="sxs-lookup"><span data-stu-id="e6fc0-110">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#2)]  
  
## <a name="see-also"></a><span data-ttu-id="e6fc0-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="e6fc0-111">See also</span></span>

- [<span data-ttu-id="e6fc0-112">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="e6fc0-112">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="e6fc0-113">ドキュメント コメントとして推奨されるタグ</span><span class="sxs-lookup"><span data-stu-id="e6fc0-113">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
