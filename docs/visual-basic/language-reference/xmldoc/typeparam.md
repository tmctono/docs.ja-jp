---
title: <typeparam> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- typeparam XML tag
- <typeparam> XML tag
ms.assetid: 1bb5ba78-f060-478c-905c-77a2e43639af
ms.openlocfilehash: 9e07a0c9d100669215f01a168da98902644a6f0b
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57496145"
---
# <a name="typeparam-visual-basic"></a><span data-ttu-id="48cfb-102">\<typeparam > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="48cfb-102">\<typeparam> (Visual Basic)</span></span>
<span data-ttu-id="48cfb-103">型パラメーターの名前と説明を定義します。</span><span class="sxs-lookup"><span data-stu-id="48cfb-103">Defines a type parameter name and description.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48cfb-104">構文</span><span class="sxs-lookup"><span data-stu-id="48cfb-104">Syntax</span></span>  
  
```xml  
<typeparam name="name">description</typeparam>  
```  
  
## <a name="parameters"></a><span data-ttu-id="48cfb-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="48cfb-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="48cfb-106">型パラメーターの名前。</span><span class="sxs-lookup"><span data-stu-id="48cfb-106">The name of the type parameter.</span></span> <span data-ttu-id="48cfb-107">名前は二重引用符 (" ") で囲みます。</span><span class="sxs-lookup"><span data-stu-id="48cfb-107">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="48cfb-108">型パラメーターの説明。</span><span class="sxs-lookup"><span data-stu-id="48cfb-108">A description of the type parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="48cfb-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="48cfb-109">Remarks</span></span>  
 <span data-ttu-id="48cfb-110">使用して、`<typeparam>`型パラメーターのいずれかを記述するには、ジェネリック型またはジェネリック メンバー宣言のコメント内のタグ。</span><span class="sxs-lookup"><span data-stu-id="48cfb-110">Use the `<typeparam>` tag in the comment for a generic type or generic member declaration to describe one of the type parameters.</span></span>  
  
 <span data-ttu-id="48cfb-111">コンパイル時に [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="48cfb-111">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="48cfb-112">例</span><span class="sxs-lookup"><span data-stu-id="48cfb-112">Example</span></span>  
 <span data-ttu-id="48cfb-113">この例では、`<typeparam>`を記述するタグ、`id`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="48cfb-113">This example uses the `<typeparam>` tag to describe the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#8)]  
  
## <a name="see-also"></a><span data-ttu-id="48cfb-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="48cfb-114">See also</span></span>
- [<span data-ttu-id="48cfb-115">XML のコメント用タグ</span><span class="sxs-lookup"><span data-stu-id="48cfb-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
