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
ms.openlocfilehash: 09577d931c6b1f571cd4112c788da38bab85bf42
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2019
ms.locfileid: "72523281"
---
# <a name="value-c-programming-guide"></a><span data-ttu-id="4fea6-102">\<value> (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="4fea6-102">\<value> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="4fea6-103">構文</span><span class="sxs-lookup"><span data-stu-id="4fea6-103">Syntax</span></span>  
  
```xml  
<value>property-description</value>  
```  
  
## <a name="parameters"></a><span data-ttu-id="4fea6-104">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4fea6-104">Parameters</span></span>  
 `property-description`  
 <span data-ttu-id="4fea6-105">プロパティの説明。</span><span class="sxs-lookup"><span data-stu-id="4fea6-105">A description for the property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4fea6-106">解説</span><span class="sxs-lookup"><span data-stu-id="4fea6-106">Remarks</span></span>  
 <span data-ttu-id="4fea6-107">\<value> タグを使用して、プロパティが表す値を記述することができます。</span><span class="sxs-lookup"><span data-stu-id="4fea6-107">The \<value> tag lets you describe the value that a property represents.</span></span> <span data-ttu-id="4fea6-108">Visual Studio .NET 開発環境では、コード ウィザードを使用してプロパティを追加するときに、新しいプロパティの [\<summary>](./summary.md) タグが追加されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="4fea6-108">Note that when you add a property via code wizard in the Visual Studio .NET development environment, it will add a [\<summary>](./summary.md) tag for the new property.</span></span> <span data-ttu-id="4fea6-109">その後、手動で \<value> タグを追加してプロパティが表す値を記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4fea6-109">You should then manually add a \<value> tag to describe the value that the property represents.</span></span>  
  
 <span data-ttu-id="4fea6-110">コンパイル時に [-doc](../../language-reference/compiler-options/doc-compiler-option.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="4fea6-110">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4fea6-111">例</span><span class="sxs-lookup"><span data-stu-id="4fea6-111">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#14)]  
  
## <a name="see-also"></a><span data-ttu-id="4fea6-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="4fea6-112">See also</span></span>

- [<span data-ttu-id="4fea6-113">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="4fea6-113">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="4fea6-114">ドキュメント コメントとして推奨されるタグ</span><span class="sxs-lookup"><span data-stu-id="4fea6-114">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
