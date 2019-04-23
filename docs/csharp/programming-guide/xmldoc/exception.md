---
title: <exception> - C# プログラミング ガイド
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- exception
- <exception>
helpviewer_keywords:
- <exception> C# XML tag
- exception C# XML tag
ms.assetid: dd73aac5-3c74-4fcf-9498-f11bff3a2f3c
ms.openlocfilehash: 639e3a345fc8ed3d348461718f73ead6167158db
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2019
ms.locfileid: "59610913"
---
# <a name="exception-c-programming-guide"></a><span data-ttu-id="98884-102">\<exception> (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="98884-102">\<exception> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="98884-103">構文</span><span class="sxs-lookup"><span data-stu-id="98884-103">Syntax</span></span>  
  
```xml  
<exception cref="member">description</exception>  
```  
  
## <a name="parameters"></a><span data-ttu-id="98884-104">パラメーター</span><span class="sxs-lookup"><span data-stu-id="98884-104">Parameters</span></span>  
 <span data-ttu-id="98884-105">cref = "`member`"</span><span class="sxs-lookup"><span data-stu-id="98884-105">cref = " `member`"</span></span>  
 <span data-ttu-id="98884-106">現在のコンパイル環境から使用できる例外の参照。</span><span class="sxs-lookup"><span data-stu-id="98884-106">A reference to an exception that is available from the current compilation environment.</span></span> <span data-ttu-id="98884-107">コンパイラは、指定された例外が存在し、出力の XML で `member` が正規要素名に変換されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="98884-107">The compiler checks that the given exception exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="98884-108">`member` は、二重引用符 (" ") で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="98884-108">`member` must appear within double quotation marks (" ").</span></span>  
  
 <span data-ttu-id="98884-109">ジェネリック型を参照するよう `member` を書式設定する方法について詳しくは、[XML ファイルの処理](processing-the-xml-file.md)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="98884-109">For more information on how to format `member` to reference a generic type, see [Processing the XML File](processing-the-xml-file.md).</span></span>
  
 `description`  
 <span data-ttu-id="98884-110">例外の説明。</span><span class="sxs-lookup"><span data-stu-id="98884-110">A description of the exception.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="98884-111">解説</span><span class="sxs-lookup"><span data-stu-id="98884-111">Remarks</span></span>  
 <span data-ttu-id="98884-112">\<exception> タグを使用すると、スローできる例外を指定できます。</span><span class="sxs-lookup"><span data-stu-id="98884-112">The \<exception> tag lets you specify which exceptions can be thrown.</span></span> <span data-ttu-id="98884-113">このタブは、メソッド、プロパティ、イベント、インデクサーの定義に適用できます。</span><span class="sxs-lookup"><span data-stu-id="98884-113">This tag can be applied to definitions for methods, properties, events, and indexers.</span></span>  
  
 <span data-ttu-id="98884-114">コンパイル時に [/doc](../../language-reference/compiler-options/doc-compiler-option.md) を指定してドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="98884-114">Compile with [/doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
 <span data-ttu-id="98884-115">例外処理の詳細については、「[例外と例外処理](../exceptions/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="98884-115">For more information about exception handling, see [Exceptions and Exception Handling](../exceptions/index.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="98884-116">例</span><span class="sxs-lookup"><span data-stu-id="98884-116">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#4)]  
  
## <a name="see-also"></a><span data-ttu-id="98884-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="98884-117">See also</span></span>

- [<span data-ttu-id="98884-118">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="98884-118">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="98884-119">ドキュメント コメントとして推奨されるタグ</span><span class="sxs-lookup"><span data-stu-id="98884-119">Recommended Tags for Documentation Comments</span></span>](recommended-tags-for-documentation-comments.md)
