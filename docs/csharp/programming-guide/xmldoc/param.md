---
title: <param> - C# プログラミング ガイド
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- param
- <param>
helpviewer_keywords:
- <param> C# XML tag
- param C# XML tag
ms.assetid: 46d329b1-5b84-4537-9e17-73ca97313e4e
ms.openlocfilehash: ffa3bd066ce753f2b953f2d6d0a70a3bf65293ff
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57468033"
---
# <a name="param-c-programming-guide"></a><span data-ttu-id="e8d83-102">\<param> (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="e8d83-102">\<param> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="e8d83-103">構文</span><span class="sxs-lookup"><span data-stu-id="e8d83-103">Syntax</span></span>  
  
```xml  
<param name="name">description</param>  
```  
  
## <a name="parameters"></a><span data-ttu-id="e8d83-104">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e8d83-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="e8d83-105">メソッド パラメーターの名前です。</span><span class="sxs-lookup"><span data-stu-id="e8d83-105">The name of a method parameter.</span></span> <span data-ttu-id="e8d83-106">名前は二重引用符 (" ") で囲みます。</span><span class="sxs-lookup"><span data-stu-id="e8d83-106">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="e8d83-107">パラメーターの説明です。</span><span class="sxs-lookup"><span data-stu-id="e8d83-107">A description for the parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e8d83-108">解説</span><span class="sxs-lookup"><span data-stu-id="e8d83-108">Remarks</span></span>  
 <span data-ttu-id="e8d83-109">\<param> タグは、メソッドのいずれか 1 つのパラメーターを説明するためにメソッドの宣言のコメントで使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8d83-109">The \<param> tag should be used in the comment for a method declaration to describe one of the parameters for the method.</span></span> <span data-ttu-id="e8d83-110">複数のパラメーターをドキュメント化するには、複数の \<param> タグを使用します。</span><span class="sxs-lookup"><span data-stu-id="e8d83-110">To document multiple parameters, use multiple \<param> tags.</span></span>  
  
 <span data-ttu-id="e8d83-111">\<param> タグのテキストは、IntelliSense、オブジェクト ブラウザー、コード コメント Web レポートに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e8d83-111">The text for the \<param> tag will be displayed in IntelliSense, the Object Browser, and in the Code Comment Web Report.</span></span>  
  
 <span data-ttu-id="e8d83-112">コンパイル時に [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="e8d83-112">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e8d83-113">例</span><span class="sxs-lookup"><span data-stu-id="e8d83-113">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#1)]  
  
## <a name="see-also"></a><span data-ttu-id="e8d83-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="e8d83-114">See also</span></span>

- [<span data-ttu-id="e8d83-115">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="e8d83-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="e8d83-116">ドキュメント コメントとして推奨されるタグ</span><span class="sxs-lookup"><span data-stu-id="e8d83-116">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
