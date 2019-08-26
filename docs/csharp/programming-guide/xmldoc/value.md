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
ms.openlocfilehash: 4d967d671b3a27698b457c80ff5a8f7031dc6bcb
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2019
ms.locfileid: "69587402"
---
# <a name="value-c-programming-guide"></a><span data-ttu-id="5783f-102">\<value> (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="5783f-102">\<value> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="5783f-103">構文</span><span class="sxs-lookup"><span data-stu-id="5783f-103">Syntax</span></span>  
  
```xml  
<value>property-description</value>  
```  
  
## <a name="parameters"></a><span data-ttu-id="5783f-104">parameters</span><span class="sxs-lookup"><span data-stu-id="5783f-104">Parameters</span></span>  
 `property-description`  
 <span data-ttu-id="5783f-105">プロパティの説明。</span><span class="sxs-lookup"><span data-stu-id="5783f-105">A description for the property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5783f-106">解説</span><span class="sxs-lookup"><span data-stu-id="5783f-106">Remarks</span></span>  
 <span data-ttu-id="5783f-107">\<value> タグを使用して、プロパティが表す値を記述することができます。</span><span class="sxs-lookup"><span data-stu-id="5783f-107">The \<value> tag lets you describe the value that a property represents.</span></span> <span data-ttu-id="5783f-108">Visual Studio .NET 開発環境では、コード ウィザードを使用してプロパティを追加するときに、新しいプロパティの [\<summary>](./summary.md) タグが追加されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="5783f-108">Note that when you add a property via code wizard in the Visual Studio .NET development environment, it will add a [\<summary>](./summary.md) tag for the new property.</span></span> <span data-ttu-id="5783f-109">その後、手動で \<value> タグを追加してプロパティが表す値を記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5783f-109">You should then manually add a \<value> tag to describe the value that the property represents.</span></span>  
  
 <span data-ttu-id="5783f-110">コンパイル時に [/doc](../../language-reference/compiler-options/doc-compiler-option.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="5783f-110">Compile with [/doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5783f-111">例</span><span class="sxs-lookup"><span data-stu-id="5783f-111">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#14)]  
  
## <a name="see-also"></a><span data-ttu-id="5783f-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="5783f-112">See also</span></span>

- [<span data-ttu-id="5783f-113">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="5783f-113">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="5783f-114">ドキュメント コメントとして推奨されるタグ</span><span class="sxs-lookup"><span data-stu-id="5783f-114">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
