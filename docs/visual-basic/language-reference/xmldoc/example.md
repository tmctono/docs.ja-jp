---
title: <example>
ms.date: 07/20/2015
helpviewer_keywords:
- example XML tag
- <example> XML tag
ms.assetid: 90eeda1c-3fc4-427c-879c-5046d265a97c
ms.openlocfilehash: 42f40581d252956433165789d6674234a295867c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400145"
---
# <a name="example-visual-basic"></a><span data-ttu-id="27ffa-101">\<example> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="27ffa-101">\<example> (Visual Basic)</span></span>
<span data-ttu-id="27ffa-102">メンバーの例を指定します。</span><span class="sxs-lookup"><span data-stu-id="27ffa-102">Specifies an example for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27ffa-103">構文</span><span class="sxs-lookup"><span data-stu-id="27ffa-103">Syntax</span></span>  
  
```xml  
<example>description</example>  
```  
  
## <a name="parameters"></a><span data-ttu-id="27ffa-104">パラメーター</span><span class="sxs-lookup"><span data-stu-id="27ffa-104">Parameters</span></span>  
 `description`  
 <span data-ttu-id="27ffa-105">コード例の説明です。</span><span class="sxs-lookup"><span data-stu-id="27ffa-105">A description of the code sample.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="27ffa-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="27ffa-106">Remarks</span></span>  
 <span data-ttu-id="27ffa-107">`<example>` タグを使用すると、メソッドまたは他のライブラリ メンバーの使用例を指定できます。</span><span class="sxs-lookup"><span data-stu-id="27ffa-107">The `<example>` tag lets you specify an example of how to use a method or other library member.</span></span> <span data-ttu-id="27ffa-108">一般的に、[\<code>](code.md) タグが使用されます。</span><span class="sxs-lookup"><span data-stu-id="27ffa-108">This commonly involves using the [\<code>](code.md) tag.</span></span>  
  
 <span data-ttu-id="27ffa-109">コンパイル時に [-doc](../../reference/command-line-compiler/doc.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="27ffa-109">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="27ffa-110">例</span><span class="sxs-lookup"><span data-stu-id="27ffa-110">Example</span></span>  
 <span data-ttu-id="27ffa-111">この例では、`<example>` タグを使用して、`ID` フィールドを使用する例を組み込みます。</span><span class="sxs-lookup"><span data-stu-id="27ffa-111">This example uses the `<example>` tag to include an example for using the `ID` field.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="27ffa-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="27ffa-112">See also</span></span>

- [<span data-ttu-id="27ffa-113">XML のコメント用タグ</span><span class="sxs-lookup"><span data-stu-id="27ffa-113">XML Comment Tags</span></span>](index.md)
