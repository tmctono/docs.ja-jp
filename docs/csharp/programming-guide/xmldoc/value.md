---
title: <value> - C# プログラミング ガイド
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- <value>
helpviewer_keywords:
- <value> C# XML tag
- value C# XML tag
ms.assetid: 08dbadaf-9ab6-43d9-9493-98e43bed199a
ms.openlocfilehash: 3495a6c88d340342362d84d6ea3f12048d42b21f
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2019
ms.locfileid: "56982155"
---
# <a name="value-c-programming-guide"></a><span data-ttu-id="8dec4-102">\<value> (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="8dec4-102">\<value> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="8dec4-103">構文</span><span class="sxs-lookup"><span data-stu-id="8dec4-103">Syntax</span></span>  
  
```xml  
<value>property-description</value>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8dec4-104">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8dec4-104">Parameters</span></span>  
 `property-description`  
 <span data-ttu-id="8dec4-105">プロパティの説明。</span><span class="sxs-lookup"><span data-stu-id="8dec4-105">A description for the property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8dec4-106">解説</span><span class="sxs-lookup"><span data-stu-id="8dec4-106">Remarks</span></span>  
 <span data-ttu-id="8dec4-107">\<value> タグを使用して、プロパティが表す値を記述することができます。</span><span class="sxs-lookup"><span data-stu-id="8dec4-107">The \<value> tag lets you describe the value that a property represents.</span></span> <span data-ttu-id="8dec4-108">Visual Studio .NET 開発環境では、コード ウィザードを使用してプロパティを追加するときに、新しいプロパティの [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md) タグが追加されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="8dec4-108">Note that when you add a property via code wizard in the Visual Studio .NET development environment, it will add a [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md) tag for the new property.</span></span> <span data-ttu-id="8dec4-109">その後、手動で \<value> タグを追加してプロパティが表す値を記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8dec4-109">You should then manually add a \<value> tag to describe the value that the property represents.</span></span>  
  
 <span data-ttu-id="8dec4-110">コンパイル時に [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="8dec4-110">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8dec4-111">例</span><span class="sxs-lookup"><span data-stu-id="8dec4-111">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#14)]  
  
## <a name="see-also"></a><span data-ttu-id="8dec4-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="8dec4-112">See also</span></span>

- [<span data-ttu-id="8dec4-113">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="8dec4-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="8dec4-114">ドキュメント コメントとして推奨されるタグ</span><span class="sxs-lookup"><span data-stu-id="8dec4-114">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
