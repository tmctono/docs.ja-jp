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
ms.openlocfilehash: f9613a7373a829d2a52f3f56b8ea1ab35ebdcf5f
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711728"
---
# <a name="param-c-programming-guide"></a><span data-ttu-id="90a21-102">\<param> (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="90a21-102">\<param> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="90a21-103">構文</span><span class="sxs-lookup"><span data-stu-id="90a21-103">Syntax</span></span>  
  
```xml  
<param name="name">description</param>  
```  
  
## <a name="parameters"></a><span data-ttu-id="90a21-104">パラメーター</span><span class="sxs-lookup"><span data-stu-id="90a21-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="90a21-105">メソッド パラメーターの名前です。</span><span class="sxs-lookup"><span data-stu-id="90a21-105">The name of a method parameter.</span></span> <span data-ttu-id="90a21-106">名前は二重引用符 (" ") で囲みます。</span><span class="sxs-lookup"><span data-stu-id="90a21-106">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="90a21-107">パラメーターの説明です。</span><span class="sxs-lookup"><span data-stu-id="90a21-107">A description for the parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="90a21-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="90a21-108">Remarks</span></span>  
 <span data-ttu-id="90a21-109">\<param> タグは、メソッドのいずれか 1 つのパラメーターを説明するためにメソッドの宣言のコメントで使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="90a21-109">The \<param> tag should be used in the comment for a method declaration to describe one of the parameters for the method.</span></span> <span data-ttu-id="90a21-110">複数のパラメーターをドキュメント化するには、複数の \<param> タグを使用します。</span><span class="sxs-lookup"><span data-stu-id="90a21-110">To document multiple parameters, use multiple \<param> tags.</span></span>  
  
 <span data-ttu-id="90a21-111">\<param> タグのテキストは、IntelliSense、オブジェクト ブラウザー、コード コメント Web レポートに表示されます。</span><span class="sxs-lookup"><span data-stu-id="90a21-111">The text for the \<param> tag will be displayed in IntelliSense, the Object Browser, and in the Code Comment Web Report.</span></span>  
  
 <span data-ttu-id="90a21-112">コンパイル時に [-doc](../../language-reference/compiler-options/doc-compiler-option.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="90a21-112">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="90a21-113">例</span><span class="sxs-lookup"><span data-stu-id="90a21-113">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#1)]  
  
## <a name="see-also"></a><span data-ttu-id="90a21-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="90a21-114">See also</span></span>

- [<span data-ttu-id="90a21-115">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="90a21-115">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="90a21-116">ドキュメント コメントとして推奨されるタグ</span><span class="sxs-lookup"><span data-stu-id="90a21-116">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
