---
title: <remarks>
ms.date: 07/20/2015
helpviewer_keywords:
- <remarks> XML tag
- remarks XML tag
ms.assetid: c6241773-a7ed-41c9-9a8b-9722a0c606a9
ms.openlocfilehash: c57ddb870192bd94301f99eb71ad29526e8efc28
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400022"
---
# <a name="remarks-visual-basic"></a><span data-ttu-id="c81a5-101">\<remarks> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c81a5-101">\<remarks> (Visual Basic)</span></span>
<span data-ttu-id="c81a5-102">メンバーの解説セクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="c81a5-102">Specifies a remarks section for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c81a5-103">構文</span><span class="sxs-lookup"><span data-stu-id="c81a5-103">Syntax</span></span>  
  
```xml  
<remarks>description</remarks>  
```  
  
## <a name="parameters"></a><span data-ttu-id="c81a5-104">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c81a5-104">Parameters</span></span>  
 `description`  
 <span data-ttu-id="c81a5-105">メンバーの説明。</span><span class="sxs-lookup"><span data-stu-id="c81a5-105">A description of the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c81a5-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="c81a5-106">Remarks</span></span>  
 <span data-ttu-id="c81a5-107">`<remarks>` タグを使用して、型の情報を追加し、[\<summary>](summary.md) で指定された情報を補足します。</span><span class="sxs-lookup"><span data-stu-id="c81a5-107">Use the `<remarks>` tag to add information about a type, supplementing the information specified with [\<summary>](summary.md).</span></span>  
  
 <span data-ttu-id="c81a5-108">この情報はオブジェクト ブラウザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="c81a5-108">This information appears in the Object Browser.</span></span> <span data-ttu-id="c81a5-109">オブジェクト ブラウザーについては、「[コードの構造の表示](/visualstudio/ide/viewing-the-structure-of-code)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c81a5-109">For information about the Object Browser, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="c81a5-110">コンパイル時に [-doc](../../reference/command-line-compiler/doc.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="c81a5-110">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c81a5-111">例</span><span class="sxs-lookup"><span data-stu-id="c81a5-111">Example</span></span>  
 <span data-ttu-id="c81a5-112">この例では、`<remarks>` タグを使用して `UpdateRecord` メソッドの動作を説明します。</span><span class="sxs-lookup"><span data-stu-id="c81a5-112">This example uses the `<remarks>` tag to explain what the `UpdateRecord` method does.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="c81a5-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="c81a5-113">See also</span></span>

- [<span data-ttu-id="c81a5-114">XML のコメント用タグ</span><span class="sxs-lookup"><span data-stu-id="c81a5-114">XML Comment Tags</span></span>](index.md)
