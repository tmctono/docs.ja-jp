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
ms.openlocfilehash: 454928d5dfd023639bc68f194f2f5ec9e2d7dc22
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2019
ms.locfileid: "72523395"
---
# <a name="permission-c-programming-guide"></a><span data-ttu-id="e0969-102">\<permission> (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="e0969-102">\<permission> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="e0969-103">構文</span><span class="sxs-lookup"><span data-stu-id="e0969-103">Syntax</span></span>  
  
```xml  
<permission cref="member">description</permission>  
```  
  
## <a name="parameters"></a><span data-ttu-id="e0969-104">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e0969-104">Parameters</span></span>  
 <span data-ttu-id="e0969-105">cref = "`member`"</span><span class="sxs-lookup"><span data-stu-id="e0969-105">cref = " `member`"</span></span>  
 <span data-ttu-id="e0969-106">現在のコンパイル環境からの呼び出しに利用できる、メンバーまたはフィールドへの参照。</span><span class="sxs-lookup"><span data-stu-id="e0969-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="e0969-107">コンパイラは、指定されたコード要素が存在し、出力の XML で `member` が正規要素名に変換されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e0969-107">The compiler checks that the given code element exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="e0969-108">*member* は、二重引用符 (" ") で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0969-108">*member* must appear within double quotation marks (" ").</span></span>  
  
 <span data-ttu-id="e0969-109">ジェネリック型への cref 参照を作成する方法については、「[\<see>](./see.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0969-109">For information on how to create a cref reference to a generic type, see [\<see>](./see.md).</span></span>  
  
 `description`  
 <span data-ttu-id="e0969-110">メンバーへのアクセスの説明です。</span><span class="sxs-lookup"><span data-stu-id="e0969-110">A description of the access to the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e0969-111">解説</span><span class="sxs-lookup"><span data-stu-id="e0969-111">Remarks</span></span>  
 <span data-ttu-id="e0969-112">\<permission> タグを使用すると、メンバーのアクセスを文書化できます。</span><span class="sxs-lookup"><span data-stu-id="e0969-112">The \<permission> tag lets you document the access of a member.</span></span> <span data-ttu-id="e0969-113"><xref:System.Security.PermissionSet> クラスを使用すると、メンバーへのアクセスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="e0969-113">The <xref:System.Security.PermissionSet> class lets you specify access to a member.</span></span>  
  
 <span data-ttu-id="e0969-114">コンパイル時に [-doc](../../language-reference/compiler-options/doc-compiler-option.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="e0969-114">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e0969-115">例</span><span class="sxs-lookup"><span data-stu-id="e0969-115">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#8)]  
  
## <a name="see-also"></a><span data-ttu-id="e0969-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="e0969-116">See also</span></span>

- [<span data-ttu-id="e0969-117">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="e0969-117">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="e0969-118">ドキュメント コメントとして推奨されるタグ</span><span class="sxs-lookup"><span data-stu-id="e0969-118">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
