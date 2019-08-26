---
title: <permission> - C# プログラミング ガイド
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- permission
- <permission>
helpviewer_keywords:
- <permission> C# XML tag
- permission C# XML tag
ms.assetid: 769e93fe-8404-443f-bf99-577aa42b6a49
ms.openlocfilehash: e9eb50394f01072a194d3f746577707f89ba65dd
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2019
ms.locfileid: "69587887"
---
# <a name="permission-c-programming-guide"></a><span data-ttu-id="011ea-102">\<permission> (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="011ea-102">\<permission> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="011ea-103">構文</span><span class="sxs-lookup"><span data-stu-id="011ea-103">Syntax</span></span>  
  
```xml  
<permission cref="member">description</permission>  
```  
  
## <a name="parameters"></a><span data-ttu-id="011ea-104">parameters</span><span class="sxs-lookup"><span data-stu-id="011ea-104">Parameters</span></span>  
 <span data-ttu-id="011ea-105">cref = "`member`"</span><span class="sxs-lookup"><span data-stu-id="011ea-105">cref = " `member`"</span></span>  
 <span data-ttu-id="011ea-106">現在のコンパイル環境からの呼び出しに利用できる、メンバーまたはフィールドへの参照。</span><span class="sxs-lookup"><span data-stu-id="011ea-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="011ea-107">コンパイラは、指定されたコード要素が存在し、出力の XML で `member` が正規要素名に変換されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="011ea-107">The compiler checks that the given code element exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="011ea-108">*member* は、二重引用符 (" ") で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="011ea-108">*member* must appear within double quotation marks (" ").</span></span>  
  
 <span data-ttu-id="011ea-109">ジェネリック型への cref 参照を作成する方法については、「[\<see>](./see.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="011ea-109">For information on how to create a cref reference to a generic type, see [\<see>](./see.md).</span></span>  
  
 `description`  
 <span data-ttu-id="011ea-110">メンバーへのアクセスの説明です。</span><span class="sxs-lookup"><span data-stu-id="011ea-110">A description of the access to the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="011ea-111">解説</span><span class="sxs-lookup"><span data-stu-id="011ea-111">Remarks</span></span>  
 <span data-ttu-id="011ea-112">\<permission> タグを使用すると、メンバーのアクセスを文書化できます。</span><span class="sxs-lookup"><span data-stu-id="011ea-112">The \<permission> tag lets you document the access of a member.</span></span> <span data-ttu-id="011ea-113"><xref:System.Security.PermissionSet> クラスを使用すると、メンバーへのアクセスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="011ea-113">The <xref:System.Security.PermissionSet> class lets you specify access to a member.</span></span>  
  
 <span data-ttu-id="011ea-114">コンパイル時に [/doc](../../language-reference/compiler-options/doc-compiler-option.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="011ea-114">Compile with [/doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="011ea-115">例</span><span class="sxs-lookup"><span data-stu-id="011ea-115">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#8)]  
  
## <a name="see-also"></a><span data-ttu-id="011ea-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="011ea-116">See also</span></span>

- [<span data-ttu-id="011ea-117">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="011ea-117">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="011ea-118">ドキュメント コメントとして推奨されるタグ</span><span class="sxs-lookup"><span data-stu-id="011ea-118">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
