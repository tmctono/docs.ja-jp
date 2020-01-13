---
title: <returns> - C# プログラミング ガイド
ms.date: 07/20/2015
f1_keywords:
- returns
- <returns>
helpviewer_keywords:
- <returns> C# XML tag
- returns C# XML tag
ms.assetid: bb2d9958-62fc-47c7-9511-6311171f119f
ms.openlocfilehash: 16105ed0f4d7b2ea0067e1b2f0409dfa5b30c4a4
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75694869"
---
# <a name="returns-c-programming-guide"></a><span data-ttu-id="427c3-102">\<returns> (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="427c3-102">\<returns> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="427c3-103">構文</span><span class="sxs-lookup"><span data-stu-id="427c3-103">Syntax</span></span>  
  
```xml  
<returns>description</returns>  
```  
  
## <a name="parameters"></a><span data-ttu-id="427c3-104">パラメーター</span><span class="sxs-lookup"><span data-stu-id="427c3-104">Parameters</span></span>  
 `description`  
 <span data-ttu-id="427c3-105">戻り値の説明。</span><span class="sxs-lookup"><span data-stu-id="427c3-105">A description of the return value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="427c3-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="427c3-106">Remarks</span></span>  
 <span data-ttu-id="427c3-107">\<returns> タグは、戻り値を説明するためにメソッドの宣言のコメントで使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="427c3-107">The \<returns> tag should be used in the comment for a method declaration to describe the return value.</span></span>  
  
 <span data-ttu-id="427c3-108">コンパイル時に [-doc](../../language-reference/compiler-options/doc-compiler-option.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="427c3-108">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="427c3-109">例</span><span class="sxs-lookup"><span data-stu-id="427c3-109">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#10)]  
  
## <a name="see-also"></a><span data-ttu-id="427c3-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="427c3-110">See also</span></span>

- [<span data-ttu-id="427c3-111">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="427c3-111">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="427c3-112">ドキュメント コメントとして推奨されるタグ</span><span class="sxs-lookup"><span data-stu-id="427c3-112">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
