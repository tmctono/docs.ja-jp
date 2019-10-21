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
ms.openlocfilehash: ed7a8f8a06771a18dc4244bffbda53e9adbd4e90
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2019
ms.locfileid: "72523420"
---
# <a name="param-c-programming-guide"></a><span data-ttu-id="ec003-102">\<param> (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="ec003-102">\<param> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="ec003-103">構文</span><span class="sxs-lookup"><span data-stu-id="ec003-103">Syntax</span></span>  
  
```xml  
<param name="name">description</param>  
```  
  
## <a name="parameters"></a><span data-ttu-id="ec003-104">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ec003-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="ec003-105">メソッド パラメーターの名前です。</span><span class="sxs-lookup"><span data-stu-id="ec003-105">The name of a method parameter.</span></span> <span data-ttu-id="ec003-106">名前は二重引用符 (" ") で囲みます。</span><span class="sxs-lookup"><span data-stu-id="ec003-106">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="ec003-107">パラメーターの説明です。</span><span class="sxs-lookup"><span data-stu-id="ec003-107">A description for the parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ec003-108">解説</span><span class="sxs-lookup"><span data-stu-id="ec003-108">Remarks</span></span>  
 <span data-ttu-id="ec003-109">\<param> タグは、メソッドのいずれか 1 つのパラメーターを説明するためにメソッドの宣言のコメントで使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ec003-109">The \<param> tag should be used in the comment for a method declaration to describe one of the parameters for the method.</span></span> <span data-ttu-id="ec003-110">複数のパラメーターをドキュメント化するには、複数の \<param> タグを使用します。</span><span class="sxs-lookup"><span data-stu-id="ec003-110">To document multiple parameters, use multiple \<param> tags.</span></span>  
  
 <span data-ttu-id="ec003-111">\<param> タグのテキストは、IntelliSense、オブジェクト ブラウザー、コード コメント Web レポートに表示されます。</span><span class="sxs-lookup"><span data-stu-id="ec003-111">The text for the \<param> tag will be displayed in IntelliSense, the Object Browser, and in the Code Comment Web Report.</span></span>  
  
 <span data-ttu-id="ec003-112">コンパイル時に [-doc](../../language-reference/compiler-options/doc-compiler-option.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="ec003-112">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ec003-113">例</span><span class="sxs-lookup"><span data-stu-id="ec003-113">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#1)]  
  
## <a name="see-also"></a><span data-ttu-id="ec003-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="ec003-114">See also</span></span>

- [<span data-ttu-id="ec003-115">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="ec003-115">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="ec003-116">ドキュメント コメントとして推奨されるタグ</span><span class="sxs-lookup"><span data-stu-id="ec003-116">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
