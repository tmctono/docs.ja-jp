---
title: <param>
ms.date: 07/20/2015
helpviewer_keywords:
- param XML tag
- <param> XML tag
ms.assetid: 4e32e86f-f6f3-4301-b7fc-2f321fb54368
ms.openlocfilehash: 4405fdf2defbb27aa2146d20083fd406d1f07236
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352297"
---
# <a name="param-visual-basic"></a><span data-ttu-id="6555e-101">\<param> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6555e-101">\<param> (Visual Basic)</span></span>
<span data-ttu-id="6555e-102">パラメーターの名前と説明を定義します。</span><span class="sxs-lookup"><span data-stu-id="6555e-102">Defines a parameter name and description.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6555e-103">構文</span><span class="sxs-lookup"><span data-stu-id="6555e-103">Syntax</span></span>  
  
```xml  
<param name="name">description</param>  
```  
  
## <a name="parameters"></a><span data-ttu-id="6555e-104">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6555e-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="6555e-105">メソッド パラメーターの名前です。</span><span class="sxs-lookup"><span data-stu-id="6555e-105">The name of a method parameter.</span></span> <span data-ttu-id="6555e-106">名前は二重引用符 (" ") で囲みます。</span><span class="sxs-lookup"><span data-stu-id="6555e-106">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="6555e-107">パラメーターの説明です。</span><span class="sxs-lookup"><span data-stu-id="6555e-107">A description for the parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6555e-108">コメント</span><span class="sxs-lookup"><span data-stu-id="6555e-108">Remarks</span></span>  
 <span data-ttu-id="6555e-109">メソッド宣言のコメントには、メソッドのパラメーターの1つを記述するために `<param>` タグを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6555e-109">The `<param>` tag should be used in the comment for a method declaration to describe one of the parameters for the method.</span></span>  
  
 <span data-ttu-id="6555e-110">`<param>` タグのテキストは次の場所に表示されます。</span><span class="sxs-lookup"><span data-stu-id="6555e-110">The text for the `<param>` tag will appear in the following locations:</span></span>  
  
- <span data-ttu-id="6555e-111">IntelliSense のパラメーター情報。</span><span class="sxs-lookup"><span data-stu-id="6555e-111">Parameter Info of IntelliSense.</span></span> <span data-ttu-id="6555e-112">詳細については、「[IntelliSense を使用する](/visualstudio/ide/using-intellisense)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6555e-112">For more information, see [Using IntelliSense](/visualstudio/ide/using-intellisense).</span></span>  
  
- <span data-ttu-id="6555e-113">オブジェクト ブラウザー。</span><span class="sxs-lookup"><span data-stu-id="6555e-113">Object Browser.</span></span> <span data-ttu-id="6555e-114">詳細については、「[コードの構造の表示](/visualstudio/ide/viewing-the-structure-of-code)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6555e-114">For more information, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="6555e-115">コンパイル時に [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="6555e-115">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6555e-116">例</span><span class="sxs-lookup"><span data-stu-id="6555e-116">Example</span></span>  
 <span data-ttu-id="6555e-117">この例では、`<param>` タグを使用して、`id` パラメーターを記述します。</span><span class="sxs-lookup"><span data-stu-id="6555e-117">This example uses the `<param>` tag to describe the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="6555e-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="6555e-118">See also</span></span>

- [<span data-ttu-id="6555e-119">XML のコメント用タグ</span><span class="sxs-lookup"><span data-stu-id="6555e-119">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
