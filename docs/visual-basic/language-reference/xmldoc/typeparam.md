---
title: <typeparam> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- typeparam XML tag
- <typeparam> XML tag
ms.assetid: 1bb5ba78-f060-478c-905c-77a2e43639af
ms.openlocfilehash: 014623be84f9d7eb8a25ac4aadcce450f158c154
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940752"
---
# <a name="typeparam-visual-basic"></a><span data-ttu-id="8dc1e-102">\<typeparam > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8dc1e-102">\<typeparam> (Visual Basic)</span></span>
<span data-ttu-id="8dc1e-103">型パラメーターの名前と説明を定義します。</span><span class="sxs-lookup"><span data-stu-id="8dc1e-103">Defines a type parameter name and description.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8dc1e-104">構文</span><span class="sxs-lookup"><span data-stu-id="8dc1e-104">Syntax</span></span>  
  
```xml  
<typeparam name="name">description</typeparam>  
```  
  
## <a name="parameters"></a><span data-ttu-id="8dc1e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8dc1e-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="8dc1e-106">型パラメーターの名前。</span><span class="sxs-lookup"><span data-stu-id="8dc1e-106">The name of the type parameter.</span></span> <span data-ttu-id="8dc1e-107">名前は二重引用符 (" ") で囲みます。</span><span class="sxs-lookup"><span data-stu-id="8dc1e-107">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="8dc1e-108">型パラメーターの説明。</span><span class="sxs-lookup"><span data-stu-id="8dc1e-108">A description of the type parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8dc1e-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="8dc1e-109">Remarks</span></span>  
 <span data-ttu-id="8dc1e-110">使用して、`<typeparam>`型パラメーターのいずれかを記述するには、ジェネリック型またはジェネリック メンバー宣言のコメント内のタグ。</span><span class="sxs-lookup"><span data-stu-id="8dc1e-110">Use the `<typeparam>` tag in the comment for a generic type or generic member declaration to describe one of the type parameters.</span></span>  
  
 <span data-ttu-id="8dc1e-111">コンパイル時に [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="8dc1e-111">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8dc1e-112">例</span><span class="sxs-lookup"><span data-stu-id="8dc1e-112">Example</span></span>  
 <span data-ttu-id="8dc1e-113">この例では、`<typeparam>`を記述するタグ、`id`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="8dc1e-113">This example uses the `<typeparam>` tag to describe the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#8)]  
  
## <a name="see-also"></a><span data-ttu-id="8dc1e-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="8dc1e-114">See also</span></span>

- [<span data-ttu-id="8dc1e-115">XML のコメント用タグ</span><span class="sxs-lookup"><span data-stu-id="8dc1e-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
