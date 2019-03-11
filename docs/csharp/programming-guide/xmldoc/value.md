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
ms.openlocfilehash: 7f82008d000bf0316b505bfc5d40e9e64b2685a3
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57465194"
---
# <a name="value-c-programming-guide"></a><span data-ttu-id="6efca-102">\<value> (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="6efca-102">\<value> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="6efca-103">構文</span><span class="sxs-lookup"><span data-stu-id="6efca-103">Syntax</span></span>  
  
```xml  
<value>property-description</value>  
```  
  
## <a name="parameters"></a><span data-ttu-id="6efca-104">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6efca-104">Parameters</span></span>  
 `property-description`  
 <span data-ttu-id="6efca-105">プロパティの説明。</span><span class="sxs-lookup"><span data-stu-id="6efca-105">A description for the property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6efca-106">解説</span><span class="sxs-lookup"><span data-stu-id="6efca-106">Remarks</span></span>  
 <span data-ttu-id="6efca-107">\<value> タグを使用して、プロパティが表す値を記述することができます。</span><span class="sxs-lookup"><span data-stu-id="6efca-107">The \<value> tag lets you describe the value that a property represents.</span></span> <span data-ttu-id="6efca-108">Visual Studio .NET 開発環境では、コード ウィザードを使用してプロパティを追加するときに、新しいプロパティの [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md) タグが追加されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="6efca-108">Note that when you add a property via code wizard in the Visual Studio .NET development environment, it will add a [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md) tag for the new property.</span></span> <span data-ttu-id="6efca-109">その後、手動で \<value> タグを追加してプロパティが表す値を記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6efca-109">You should then manually add a \<value> tag to describe the value that the property represents.</span></span>  
  
 <span data-ttu-id="6efca-110">コンパイル時に [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="6efca-110">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6efca-111">例</span><span class="sxs-lookup"><span data-stu-id="6efca-111">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#14)]  
  
## <a name="see-also"></a><span data-ttu-id="6efca-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="6efca-112">See also</span></span>

- [<span data-ttu-id="6efca-113">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="6efca-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="6efca-114">ドキュメント コメントとして推奨されるタグ</span><span class="sxs-lookup"><span data-stu-id="6efca-114">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
