---
title: <param> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- param XML tag
- <param> XML tag
ms.assetid: 4e32e86f-f6f3-4301-b7fc-2f321fb54368
ms.openlocfilehash: 91489ee1664da22cc8897cdf8d12b61d962d1c83
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64664183"
---
# <a name="param-visual-basic"></a><span data-ttu-id="103dc-102">\<param > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="103dc-102">\<param> (Visual Basic)</span></span>
<span data-ttu-id="103dc-103">パラメーターの名前と説明を定義します。</span><span class="sxs-lookup"><span data-stu-id="103dc-103">Defines a parameter name and description.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="103dc-104">構文</span><span class="sxs-lookup"><span data-stu-id="103dc-104">Syntax</span></span>  
  
```xml  
<param name="name">description</param>  
```  
  
## <a name="parameters"></a><span data-ttu-id="103dc-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="103dc-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="103dc-106">メソッド パラメーターの名前です。</span><span class="sxs-lookup"><span data-stu-id="103dc-106">The name of a method parameter.</span></span> <span data-ttu-id="103dc-107">名前は二重引用符 (" ") で囲みます。</span><span class="sxs-lookup"><span data-stu-id="103dc-107">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="103dc-108">パラメーターの説明です。</span><span class="sxs-lookup"><span data-stu-id="103dc-108">A description for the parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="103dc-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="103dc-109">Remarks</span></span>  
 <span data-ttu-id="103dc-110">`<param>`タグは、メソッドのパラメーターのいずれかを説明するメソッド宣言のコメントで使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="103dc-110">The `<param>` tag should be used in the comment for a method declaration to describe one of the parameters for the method.</span></span>  
  
 <span data-ttu-id="103dc-111">テキスト、`<param>`タグは、次の場所に表示されます。</span><span class="sxs-lookup"><span data-stu-id="103dc-111">The text for the `<param>` tag will appear in the following locations:</span></span>  
  
- <span data-ttu-id="103dc-112">IntelliSense のパラメーター情報。</span><span class="sxs-lookup"><span data-stu-id="103dc-112">Parameter Info of IntelliSense.</span></span> <span data-ttu-id="103dc-113">詳細については、「[IntelliSense の使用](/visualstudio/ide/using-intellisense)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="103dc-113">For more information, see [Using IntelliSense](/visualstudio/ide/using-intellisense).</span></span>  
  
- <span data-ttu-id="103dc-114">オブジェクト ブラウザー。</span><span class="sxs-lookup"><span data-stu-id="103dc-114">Object Browser.</span></span> <span data-ttu-id="103dc-115">詳細については、「[コードの構造の表示](/visualstudio/ide/viewing-the-structure-of-code)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="103dc-115">For more information, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="103dc-116">コンパイル時に [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="103dc-116">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="103dc-117">例</span><span class="sxs-lookup"><span data-stu-id="103dc-117">Example</span></span>  
 <span data-ttu-id="103dc-118">この例では、`<param>`を記述するタグ、`id`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="103dc-118">This example uses the `<param>` tag to describe the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="103dc-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="103dc-119">See also</span></span>

- [<span data-ttu-id="103dc-120">XML のコメント用タグ</span><span class="sxs-lookup"><span data-stu-id="103dc-120">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
