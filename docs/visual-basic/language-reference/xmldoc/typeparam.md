---
title: <typeparam>
ms.date: 07/20/2015
helpviewer_keywords:
- typeparam XML tag
- <typeparam> XML tag
ms.assetid: 1bb5ba78-f060-478c-905c-77a2e43639af
ms.openlocfilehash: 00cb62827381146c172e0d15a2c64b167c21f025
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352186"
---
# <a name="typeparam-visual-basic"></a><span data-ttu-id="4dab4-101">\<typeparam > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4dab4-101">\<typeparam> (Visual Basic)</span></span>
<span data-ttu-id="4dab4-102">型パラメーターの名前と説明を定義します。</span><span class="sxs-lookup"><span data-stu-id="4dab4-102">Defines a type parameter name and description.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4dab4-103">構文</span><span class="sxs-lookup"><span data-stu-id="4dab4-103">Syntax</span></span>  
  
```xml  
<typeparam name="name">description</typeparam>  
```  
  
## <a name="parameters"></a><span data-ttu-id="4dab4-104">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4dab4-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="4dab4-105">型パラメーターの名前。</span><span class="sxs-lookup"><span data-stu-id="4dab4-105">The name of the type parameter.</span></span> <span data-ttu-id="4dab4-106">名前は二重引用符 (" ") で囲みます。</span><span class="sxs-lookup"><span data-stu-id="4dab4-106">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="4dab4-107">型パラメーターの説明。</span><span class="sxs-lookup"><span data-stu-id="4dab4-107">A description of the type parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4dab4-108">コメント</span><span class="sxs-lookup"><span data-stu-id="4dab4-108">Remarks</span></span>  
 <span data-ttu-id="4dab4-109">ジェネリック型またはジェネリックメンバー宣言のコメントに `<typeparam>` タグを使用して、型パラメーターの1つを記述します。</span><span class="sxs-lookup"><span data-stu-id="4dab4-109">Use the `<typeparam>` tag in the comment for a generic type or generic member declaration to describe one of the type parameters.</span></span>  
  
 <span data-ttu-id="4dab4-110">コンパイル時に [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="4dab4-110">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4dab4-111">例</span><span class="sxs-lookup"><span data-stu-id="4dab4-111">Example</span></span>  
 <span data-ttu-id="4dab4-112">この例では、`<typeparam>` タグを使用して、`id` パラメーターを記述します。</span><span class="sxs-lookup"><span data-stu-id="4dab4-112">This example uses the `<typeparam>` tag to describe the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#8)]  
  
## <a name="see-also"></a><span data-ttu-id="4dab4-113">参照</span><span class="sxs-lookup"><span data-stu-id="4dab4-113">See also</span></span>

- [<span data-ttu-id="4dab4-114">XML のコメント用タグ</span><span class="sxs-lookup"><span data-stu-id="4dab4-114">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
