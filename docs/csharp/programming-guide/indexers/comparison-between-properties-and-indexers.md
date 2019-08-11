---
title: プロパティとインデクサーの比較 - C# プログラミング ガイド
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- properties [C#], vs. indexers
- indexers [C#], vs. properties
ms.assetid: 3358a89f-44a0-4a4d-bf8c-07237a90af39
ms.openlocfilehash: 31e6b4b10a6ffec031a2e41a2bd16c843f802fb7
ms.sourcegitcommit: 3eeea78f52ca771087a6736c23f74600cc662658
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/31/2019
ms.locfileid: "68671677"
---
# <a name="comparison-between-properties-and-indexers-c-programming-guide"></a><span data-ttu-id="87ea3-102">プロパティとインデクサーの比較 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="87ea3-102">Comparison Between Properties and Indexers (C# Programming Guide)</span></span>
<span data-ttu-id="87ea3-103">インデクサーはプロパティと似ています。</span><span class="sxs-lookup"><span data-stu-id="87ea3-103">Indexers are like properties.</span></span> <span data-ttu-id="87ea3-104">次の表で示す相違点を除けば、プロパティのアクセサーに対して定義されているすべての規則が、インデクサーのアクセサーにも適用されます。</span><span class="sxs-lookup"><span data-stu-id="87ea3-104">Except for the differences shown in the following table, all the rules that are defined for property accessors apply to indexer accessors also.</span></span>  
  
|<span data-ttu-id="87ea3-105">プロパティ</span><span class="sxs-lookup"><span data-stu-id="87ea3-105">Property</span></span>|<span data-ttu-id="87ea3-106">インデクサー</span><span class="sxs-lookup"><span data-stu-id="87ea3-106">Indexer</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="87ea3-107">パブリック データ メンバーのように、メソッドを呼び出せるようにします。</span><span class="sxs-lookup"><span data-stu-id="87ea3-107">Allows methods to be called as if they were public data members.</span></span>|<span data-ttu-id="87ea3-108">オブジェクト自体で配列表記を使用して、オブジェクトの内部コレクションの要素にアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="87ea3-108">Allows elements of an internal collection of an object to be accessed by using array notation on the object itself.</span></span>|  
|<span data-ttu-id="87ea3-109">シンプルな名前でアクセスされます。</span><span class="sxs-lookup"><span data-stu-id="87ea3-109">Accessed through a simple name.</span></span>|<span data-ttu-id="87ea3-110">インデックスでアクセスされます。</span><span class="sxs-lookup"><span data-stu-id="87ea3-110">Accessed through an index.</span></span>|  
|<span data-ttu-id="87ea3-111">静的メンバーまたはインスタンス メンバーとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="87ea3-111">Can be a static or an instance member.</span></span>|<span data-ttu-id="87ea3-112">インスタンス メンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="87ea3-112">Must be an instance member.</span></span>|  
|<span data-ttu-id="87ea3-113">プロパティの [get](../../../csharp/language-reference/keywords/get.md) アクセサーにはパラメーターがありません。</span><span class="sxs-lookup"><span data-stu-id="87ea3-113">A [get](../../../csharp/language-reference/keywords/get.md) accessor of a property has no parameters.</span></span>|<span data-ttu-id="87ea3-114">インデクサーの `get` アクセサーには、インデクサーと同じ仮パラメーター リストがあります。</span><span class="sxs-lookup"><span data-stu-id="87ea3-114">A `get` accessor of an indexer has the same formal parameter list as the indexer.</span></span>|  
|<span data-ttu-id="87ea3-115">プロパティの [set](../../../csharp/language-reference/keywords/set.md) アクセサーには、暗黙の `value` パラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="87ea3-115">A [set](../../../csharp/language-reference/keywords/set.md) accessor of a property contains the implicit `value` parameter.</span></span>|<span data-ttu-id="87ea3-116">インデクサーの `set` アクセサーには、インデクサーと同じ仮パラメーター リストのほか、[value](../../../csharp/language-reference/keywords/value.md) パラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="87ea3-116">A `set` accessor of an indexer has the same formal parameter list as the indexer, and also to the [value](../../../csharp/language-reference/keywords/value.md) parameter.</span></span>|  
|<span data-ttu-id="87ea3-117">[自動実装プロパティ](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md)を持つ簡略化された構文がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="87ea3-117">Supports shortened syntax with [Auto-Implemented Properties](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md).</span></span>|<span data-ttu-id="87ea3-118">インデクサーのみを取得するための式形式メンバーがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="87ea3-118">Supports expression bodied members for get only indexers.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="87ea3-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="87ea3-119">See also</span></span>

- [<span data-ttu-id="87ea3-120">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="87ea3-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="87ea3-121">インデクサー</span><span class="sxs-lookup"><span data-stu-id="87ea3-121">Indexers</span></span>](../../../csharp/programming-guide/indexers/index.md)
- [<span data-ttu-id="87ea3-122">プロパティ</span><span class="sxs-lookup"><span data-stu-id="87ea3-122">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/properties.md)
