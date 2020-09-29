---
title: <permission>
ms.date: 07/20/2015
helpviewer_keywords:
- <permission> XML tag
- permission XML tag
ms.assetid: 0edf0500-5cd7-49c0-9255-64c48f972b77
ms.openlocfilehash: ae6167f3582fe22cd10d9ef7a10873d6d9bdfa06
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90872552"
---
# <a name="permission-visual-basic"></a><span data-ttu-id="087a4-101">\<permission> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="087a4-101">\<permission> (Visual Basic)</span></span>

<span data-ttu-id="087a4-102">メンバーの必要な権限を指定します。</span><span class="sxs-lookup"><span data-stu-id="087a4-102">Specifies a required permission for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="087a4-103">構文</span><span class="sxs-lookup"><span data-stu-id="087a4-103">Syntax</span></span>  
  
```xml  
<permission cref="member">description</permission>  
```  
  
## <a name="parameters"></a><span data-ttu-id="087a4-104">パラメーター</span><span class="sxs-lookup"><span data-stu-id="087a4-104">Parameters</span></span>  

 `member`  
 <span data-ttu-id="087a4-105">現在のコンパイル環境からの呼び出しに利用できる、メンバーまたはフィールドへの参照。</span><span class="sxs-lookup"><span data-stu-id="087a4-105">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="087a4-106">コンパイラは、指定されたコード要素が存在し、出力の XML で `member` が正規要素名に変換されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="087a4-106">The compiler checks that the given code element exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="087a4-107">`member` を引用符 (" ") で囲みます。</span><span class="sxs-lookup"><span data-stu-id="087a4-107">Enclose `member` in quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="087a4-108">メンバーへのアクセスの説明です。</span><span class="sxs-lookup"><span data-stu-id="087a4-108">A description of the access to the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="087a4-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="087a4-109">Remarks</span></span>  

 <span data-ttu-id="087a4-110">`<permission>` タグを使用して、メンバーのアクセスを文書化します。</span><span class="sxs-lookup"><span data-stu-id="087a4-110">Use the `<permission>` tag to document the access of a member.</span></span> <span data-ttu-id="087a4-111"><xref:System.Security.PermissionSet> クラスを使用して、メンバーへのアクセスを指定します。</span><span class="sxs-lookup"><span data-stu-id="087a4-111">Use the <xref:System.Security.PermissionSet> class to specify access to a member.</span></span>  
  
 <span data-ttu-id="087a4-112">コンパイル時に [-doc](../../reference/command-line-compiler/doc.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="087a4-112">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="087a4-113">例</span><span class="sxs-lookup"><span data-stu-id="087a4-113">Example</span></span>  

 <span data-ttu-id="087a4-114">この例では、`<permission>` タグを使用して、<xref:System.Security.Permissions.FileIOPermission> が `ReadFile` メソッドに必要であることを記述します。</span><span class="sxs-lookup"><span data-stu-id="087a4-114">This example uses the `<permission>` tag to describe that the <xref:System.Security.Permissions.FileIOPermission> is required by the `ReadFile` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="087a4-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="087a4-115">See also</span></span>

- [<span data-ttu-id="087a4-116">XML のコメント用タグ</span><span class="sxs-lookup"><span data-stu-id="087a4-116">XML Comment Tags</span></span>](index.md)
