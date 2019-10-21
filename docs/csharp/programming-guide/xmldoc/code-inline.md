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
ms.openlocfilehash: 9454ef8cc4b72d1d6bdcac26faf76eb17080328c
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2019
ms.locfileid: "72523534"
---
# <a name="c-c-programming-guide"></a><span data-ttu-id="f9e7a-102">\<c> (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="f9e7a-102">\<c> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="f9e7a-103">構文</span><span class="sxs-lookup"><span data-stu-id="f9e7a-103">Syntax</span></span>  
  
```xml  
<c>text</c>  
```  
  
## <a name="parameters"></a><span data-ttu-id="f9e7a-104">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f9e7a-104">Parameters</span></span>  
 `text`  
 <span data-ttu-id="f9e7a-105">コードとして指定するテキストです。</span><span class="sxs-lookup"><span data-stu-id="f9e7a-105">The text you would like to indicate as code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f9e7a-106">解説</span><span class="sxs-lookup"><span data-stu-id="f9e7a-106">Remarks</span></span>  
 <span data-ttu-id="f9e7a-107">\<c> タグを使用すると、説明内のテキストをコードとして指定できます。</span><span class="sxs-lookup"><span data-stu-id="f9e7a-107">The \<c> tag gives you a way to indicate that text within a description should be marked as code.</span></span> <span data-ttu-id="f9e7a-108">複数行をコードとして指定する場合は、[\<code>](./code.md) タグを使用します。</span><span class="sxs-lookup"><span data-stu-id="f9e7a-108">Use [\<code>](./code.md) to indicate multiple lines as code.</span></span>  
  
 <span data-ttu-id="f9e7a-109">コンパイル時に [-doc](../../language-reference/compiler-options/doc-compiler-option.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="f9e7a-109">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f9e7a-110">例</span><span class="sxs-lookup"><span data-stu-id="f9e7a-110">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#2)]  
  
## <a name="see-also"></a><span data-ttu-id="f9e7a-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="f9e7a-111">See also</span></span>

- [<span data-ttu-id="f9e7a-112">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="f9e7a-112">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="f9e7a-113">ドキュメント コメントとして推奨されるタグ</span><span class="sxs-lookup"><span data-stu-id="f9e7a-113">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
