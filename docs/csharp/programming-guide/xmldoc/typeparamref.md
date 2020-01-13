---
title: <typeparamref> - C# プログラミング ガイド
ms.date: 07/20/2015
f1_keywords:
- typeparamref
helpviewer_keywords:
- typeparamref C# XML tag
- <typeparamref> C# XML tag
ms.assetid: 6d8ffc58-12c5-4688-8db6-833a7ded5886
ms.openlocfilehash: 3e96d55d7cf60b2a9085cf065ef3b8193b173c5d
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711676"
---
# <a name="typeparamref-c-programming-guide"></a><span data-ttu-id="fb8e8-102">\<typeparamref> (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="fb8e8-102">\<typeparamref> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="fb8e8-103">構文</span><span class="sxs-lookup"><span data-stu-id="fb8e8-103">Syntax</span></span>  
  
```xml  
<typeparamref name="name"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="fb8e8-104">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fb8e8-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="fb8e8-105">型パラメーターの名前。</span><span class="sxs-lookup"><span data-stu-id="fb8e8-105">The name of the type parameter.</span></span> <span data-ttu-id="fb8e8-106">名前は二重引用符 (" ") で囲みます。</span><span class="sxs-lookup"><span data-stu-id="fb8e8-106">Enclose the name in double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fb8e8-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="fb8e8-107">Remarks</span></span>  
 <span data-ttu-id="fb8e8-108">ジェネリック型およびメソッドの型パラメーターの詳細については、「[ジェネリック (C# プログラミング ガイド)](../generics/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb8e8-108">For more information on type parameters in generic types and methods, see [Generics](../generics/index.md).</span></span>  
  
 <span data-ttu-id="fb8e8-109">ドキュメント ファイルを使用するときに何らかの方法で単語の書式 (斜体など) を指定するには、このタグを使用します。</span><span class="sxs-lookup"><span data-stu-id="fb8e8-109">Use this tag to enable consumers of the documentation file to format the word in some distinct way, for example in italics.</span></span>  
  
 <span data-ttu-id="fb8e8-110">コンパイル時に [-doc](../../language-reference/compiler-options/doc-compiler-option.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="fb8e8-110">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fb8e8-111">例</span><span class="sxs-lookup"><span data-stu-id="fb8e8-111">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#13)]  
  
## <a name="see-also"></a><span data-ttu-id="fb8e8-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="fb8e8-112">See also</span></span>

- [<span data-ttu-id="fb8e8-113">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="fb8e8-113">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="fb8e8-114">ドキュメント コメントとして推奨されるタグ</span><span class="sxs-lookup"><span data-stu-id="fb8e8-114">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
