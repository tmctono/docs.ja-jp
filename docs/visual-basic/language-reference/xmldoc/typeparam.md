---
title: <typeparam> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- typeparam XML tag
- <typeparam> XML tag
ms.assetid: 1bb5ba78-f060-478c-905c-77a2e43639af
ms.openlocfilehash: dbd99997fed33c192a2160fb45a739addbae254a
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524624"
---
# <a name="typeparam-visual-basic"></a><span data-ttu-id="9cfb5-102">\<typeparam > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9cfb5-102">\<typeparam> (Visual Basic)</span></span>
<span data-ttu-id="9cfb5-103">型パラメーターの名前と説明を定義します。</span><span class="sxs-lookup"><span data-stu-id="9cfb5-103">Defines a type parameter name and description.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9cfb5-104">構文</span><span class="sxs-lookup"><span data-stu-id="9cfb5-104">Syntax</span></span>  
  
```xml  
<typeparam name="name">description</typeparam>  
```  
  
## <a name="parameters"></a><span data-ttu-id="9cfb5-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9cfb5-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="9cfb5-106">型パラメーターの名前。</span><span class="sxs-lookup"><span data-stu-id="9cfb5-106">The name of the type parameter.</span></span> <span data-ttu-id="9cfb5-107">名前は二重引用符 (" ") で囲みます。</span><span class="sxs-lookup"><span data-stu-id="9cfb5-107">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="9cfb5-108">型パラメーターの説明。</span><span class="sxs-lookup"><span data-stu-id="9cfb5-108">A description of the type parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9cfb5-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="9cfb5-109">Remarks</span></span>  
 <span data-ttu-id="9cfb5-110">ジェネリック型またはジェネリックメンバー宣言のコメントに `<typeparam>` タグを使用して、型パラメーターの1つを記述します。</span><span class="sxs-lookup"><span data-stu-id="9cfb5-110">Use the `<typeparam>` tag in the comment for a generic type or generic member declaration to describe one of the type parameters.</span></span>  
  
 <span data-ttu-id="9cfb5-111">コンパイル時に [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="9cfb5-111">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9cfb5-112">例</span><span class="sxs-lookup"><span data-stu-id="9cfb5-112">Example</span></span>  
 <span data-ttu-id="9cfb5-113">この例では、`<typeparam>` タグを使用して、`id` パラメーターを記述します。</span><span class="sxs-lookup"><span data-stu-id="9cfb5-113">This example uses the `<typeparam>` tag to describe the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#8)]  
  
## <a name="see-also"></a><span data-ttu-id="9cfb5-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="9cfb5-114">See also</span></span>

- [<span data-ttu-id="9cfb5-115">XML のコメント用タグ</span><span class="sxs-lookup"><span data-stu-id="9cfb5-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
