---
title: '方法: グローバル名前空間エイリアスを使用する - C# プログラミング ガイド'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- aliases [C#]
- namespaces [C#], global namespace qualifier
- global namespace [C#]
ms.assetid: 98a1d89b-3c5a-44f7-8400-c4a3c0ec22a9
ms.openlocfilehash: b163981d3cf6d56ab953757931b0b386a47263ff
ms.sourcegitcommit: bbfcc913c275885381820be28f61efcf8e83eecc
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2019
ms.locfileid: "68796283"
---
# <a name="how-to-use-the-global-namespace-alias-c-programming-guide"></a><span data-ttu-id="2f89d-102">方法: グローバル名前空間エイリアスを使用する (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="2f89d-102">How to: Use the Global Namespace Alias (C# Programming Guide)</span></span>
<span data-ttu-id="2f89d-103">グローバル[名前空間](../../../csharp/language-reference/keywords/namespace.md)のメンバーにアクセスできると、そのメンバーが同名の別のエンティティによって隠される可能性がある場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="2f89d-103">The ability to access a member in the global [namespace](../../../csharp/language-reference/keywords/namespace.md) is useful when the member might be hidden by another entity of the same name.</span></span>  
  
 <span data-ttu-id="2f89d-104">たとえば、次のコードでは、`Console` は、<xref:System> 名前空間の `Console` 型ではなく、`TestApp.Console` に解決されます。</span><span class="sxs-lookup"><span data-stu-id="2f89d-104">For example, in the following code, `Console` resolves to `TestApp.Console` instead of to the `Console` type in the <xref:System> namespace.</span></span>  
  
 [!code-csharp[csProgGuide#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/using.cs#1)]  
  
 [!code-csharp[csProgGuideNamespaces#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#1)]  
  
 <span data-ttu-id="2f89d-105">`System.Console` を使用すると、`System` 名前空間が `TestApp.System` クラスによって隠されているため、依然としてエラーになります。</span><span class="sxs-lookup"><span data-stu-id="2f89d-105">Using `System.Console` still results in an error because the `System` namespace is hidden by the class `TestApp.System`:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#2)]  
  
 <span data-ttu-id="2f89d-106">ただし、次のように `global::System.Console` を使用すると、このエラーを回避できます。</span><span class="sxs-lookup"><span data-stu-id="2f89d-106">However, you can work around this error by using `global::System.Console`, like this:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#3)]  
  
 <span data-ttu-id="2f89d-107">左の識別子が `global` の場合、右の識別子の検索はグローバル名前空間から開始されます。</span><span class="sxs-lookup"><span data-stu-id="2f89d-107">When the left identifier is `global`, the search for the right identifier starts at the global namespace.</span></span> <span data-ttu-id="2f89d-108">たとえば、次の宣言は、グローバル空間のメンバーとして `TestApp` を参照します。</span><span class="sxs-lookup"><span data-stu-id="2f89d-108">For example, the following declaration is referencing `TestApp` as a member of the global space.</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#4)]  
  
 <span data-ttu-id="2f89d-109">当然ながら、`System` という名前の独自の名前空間を作成することはお勧めしません。そのようなコードに遭遇することはほとんどありません。</span><span class="sxs-lookup"><span data-stu-id="2f89d-109">Obviously, creating your own namespaces called `System` is not recommended, and it is unlikely you will encounter any code in which this has happened.</span></span> <span data-ttu-id="2f89d-110">ただし、大型のプロジェクトでは、フォームによっては名前空間の重複が実際に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2f89d-110">However, in larger projects, it is a very real possibility that namespace duplication may occur in one form or another.</span></span> <span data-ttu-id="2f89d-111">そのような場合は、グローバル名前空間修飾子によって、ルート名前空間を指定できます。</span><span class="sxs-lookup"><span data-stu-id="2f89d-111">In these situations, the global namespace qualifier is your guarantee that you can specify the root namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f89d-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="2f89d-112">See also</span></span>

- [<span data-ttu-id="2f89d-113">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="2f89d-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="2f89d-114">名前空間</span><span class="sxs-lookup"><span data-stu-id="2f89d-114">Namespaces</span></span>](../../../csharp/programming-guide/namespaces/index.md)
- [<span data-ttu-id="2f89d-115">::演算子</span><span class="sxs-lookup"><span data-stu-id="2f89d-115">:: Operator</span></span>](../../../csharp/language-reference/operators/namespace-alias-qualifier.md)
- [<span data-ttu-id="2f89d-116">extern</span><span class="sxs-lookup"><span data-stu-id="2f89d-116">extern</span></span>](../../../csharp/language-reference/keywords/extern.md)
