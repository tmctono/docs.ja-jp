---
title: <typeparam> - C# プログラミング ガイド
ms.date: 07/20/2015
f1_keywords:
- typeparam
helpviewer_keywords:
- <typeparam> C# XML tag
- typeparam C# XML tag
ms.assetid: 9b99d400-e911-4e55-99c6-64367c96aa4f
ms.openlocfilehash: 04145b82cbed0e9a5cae38ff9ef33d061ee792c9
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75694531"
---
# <a name="typeparam-c-programming-guide"></a><span data-ttu-id="392b1-102">\<typeparam> (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="392b1-102">\<typeparam> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="392b1-103">構文</span><span class="sxs-lookup"><span data-stu-id="392b1-103">Syntax</span></span>  
  
```xml  
<typeparam name="name">description</typeparam>  
```  
  
## <a name="parameters"></a><span data-ttu-id="392b1-104">パラメーター</span><span class="sxs-lookup"><span data-stu-id="392b1-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="392b1-105">型パラメーターの名前。</span><span class="sxs-lookup"><span data-stu-id="392b1-105">The name of the type parameter.</span></span> <span data-ttu-id="392b1-106">名前は二重引用符 (" ") で囲みます。</span><span class="sxs-lookup"><span data-stu-id="392b1-106">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="392b1-107">型パラメーターの説明。</span><span class="sxs-lookup"><span data-stu-id="392b1-107">A description for the type parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="392b1-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="392b1-108">Remarks</span></span>  
 <span data-ttu-id="392b1-109">`<typeparam>` タグは、型パラメーターを説明するためにジェネリック型またはメソッドの宣言のコメントで使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="392b1-109">The `<typeparam>` tag should be used in the comment for a generic type or method declaration to describe a type parameter.</span></span> <span data-ttu-id="392b1-110">ジェネリック型またはメソッドの型パラメーターごとにタグを追加します。</span><span class="sxs-lookup"><span data-stu-id="392b1-110">Add a tag for each type parameter of the generic type or method.</span></span>  
  
 <span data-ttu-id="392b1-111">詳細については、「[ジェネリック](../generics/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="392b1-111">For more information, see [Generics](../generics/index.md).</span></span>  
  
 <span data-ttu-id="392b1-112">`<typeparam>` タグのテキストは、IntelliSense、[オブジェクト ブラウザー ウィンドウ](/visualstudio/ide/viewing-the-structure-of-code#BKMK_ObjectBrowser)、コード コメント Web レポートに表示されます。</span><span class="sxs-lookup"><span data-stu-id="392b1-112">The text for the `<typeparam>` tag will be displayed in IntelliSense, the [Object Browser Window](/visualstudio/ide/viewing-the-structure-of-code#BKMK_ObjectBrowser) code comment web report.</span></span>  
  
 <span data-ttu-id="392b1-113">コンパイル時に [-doc](../../language-reference/compiler-options/doc-compiler-option.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="392b1-113">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="392b1-114">例</span><span class="sxs-lookup"><span data-stu-id="392b1-114">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#13)]  
  
## <a name="see-also"></a><span data-ttu-id="392b1-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="392b1-115">See also</span></span>

- [<span data-ttu-id="392b1-116">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="392b1-116">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="392b1-117">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="392b1-117">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="392b1-118">ドキュメント コメントとして推奨されるタグ</span><span class="sxs-lookup"><span data-stu-id="392b1-118">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
