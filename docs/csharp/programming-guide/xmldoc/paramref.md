---
title: <paramref> - C# プログラミング ガイド
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- paramref
- <paramref>
helpviewer_keywords:
- <paramref> C# XML tag
- paramref C# XML tag
ms.assetid: 756c24c1-f591-40e8-a838-559761539b0b
ms.openlocfilehash: e442b6829859ebc4dce6a0f5b6cd6cb777ab1400
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2019
ms.locfileid: "69587909"
---
# <a name="paramref-c-programming-guide"></a><span data-ttu-id="6bef8-102">\<paramref> (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="6bef8-102">\<paramref> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="6bef8-103">構文</span><span class="sxs-lookup"><span data-stu-id="6bef8-103">Syntax</span></span>  
  
```xml  
<paramref name="name"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="6bef8-104">parameters</span><span class="sxs-lookup"><span data-stu-id="6bef8-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="6bef8-105">参照されるパラメーターの名前です。</span><span class="sxs-lookup"><span data-stu-id="6bef8-105">The name of the parameter to refer to.</span></span> <span data-ttu-id="6bef8-106">名前は二重引用符 (" ") で囲みます。</span><span class="sxs-lookup"><span data-stu-id="6bef8-106">Enclose the name in double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6bef8-107">解説</span><span class="sxs-lookup"><span data-stu-id="6bef8-107">Remarks</span></span>  
 <span data-ttu-id="6bef8-108">\<paramref> タグを使用すると、\<summary> または \<remarks> ブロックなどのコード コメント内の単語がパラメーターを参照することを示すことができます。</span><span class="sxs-lookup"><span data-stu-id="6bef8-108">The \<paramref> tag gives you a way to indicate that a word in the code comments, for example in a \<summary> or \<remarks> block refers to a parameter.</span></span> <span data-ttu-id="6bef8-109">この単語を、太字や斜体のフォントを使うなど、何らかの独自の方法で書式設定するために XML ファイルを処理できます。</span><span class="sxs-lookup"><span data-stu-id="6bef8-109">The XML file can be processed to format this word in some distinct way, such as with a bold or italic font.</span></span>  
  
 <span data-ttu-id="6bef8-110">コンパイル時に [/doc](../../language-reference/compiler-options/doc-compiler-option.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="6bef8-110">Compile with [/doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6bef8-111">例</span><span class="sxs-lookup"><span data-stu-id="6bef8-111">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#7)]  
  
## <a name="see-also"></a><span data-ttu-id="6bef8-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="6bef8-112">See also</span></span>

- [<span data-ttu-id="6bef8-113">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="6bef8-113">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="6bef8-114">ドキュメント コメントとして推奨されるタグ</span><span class="sxs-lookup"><span data-stu-id="6bef8-114">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
