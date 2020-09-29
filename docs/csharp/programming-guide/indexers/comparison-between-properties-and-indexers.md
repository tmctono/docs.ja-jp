---
title: プロパティとインデクサーの比較 - C# プログラミング ガイド
description: C# のインデクサーとプロパティの類似点を比較します。 一部の違いを除いて、プロパティのアクセサーに対して定義されている規則は、インデクサーのアクセサーに適用されます。
ms.date: 07/20/2015
helpviewer_keywords:
- properties [C#], vs. indexers
- indexers [C#], vs. properties
ms.assetid: 3358a89f-44a0-4a4d-bf8c-07237a90af39
ms.openlocfilehash: fff20ca965e7614d26f7da32321a829d13292389
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91192530"
---
# <a name="comparison-between-properties-and-indexers-c-programming-guide"></a><span data-ttu-id="96063-104">プロパティとインデクサーの比較 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="96063-104">Comparison Between Properties and Indexers (C# Programming Guide)</span></span>

<span data-ttu-id="96063-105">インデクサーはプロパティと似ています。</span><span class="sxs-lookup"><span data-stu-id="96063-105">Indexers are like properties.</span></span> <span data-ttu-id="96063-106">次の表で示す相違点を除けば、プロパティのアクセサーに対して定義されているすべての規則が、インデクサーのアクセサーにも適用されます。</span><span class="sxs-lookup"><span data-stu-id="96063-106">Except for the differences shown in the following table, all the rules that are defined for property accessors apply to indexer accessors also.</span></span>  
  
|<span data-ttu-id="96063-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="96063-107">Property</span></span>|<span data-ttu-id="96063-108">インデクサー</span><span class="sxs-lookup"><span data-stu-id="96063-108">Indexer</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="96063-109">パブリック データ メンバーのように、メソッドを呼び出せるようにします。</span><span class="sxs-lookup"><span data-stu-id="96063-109">Allows methods to be called as if they were public data members.</span></span>|<span data-ttu-id="96063-110">オブジェクト自体で配列表記を使用して、オブジェクトの内部コレクションの要素にアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="96063-110">Allows elements of an internal collection of an object to be accessed by using array notation on the object itself.</span></span>|  
|<span data-ttu-id="96063-111">シンプルな名前でアクセスされます。</span><span class="sxs-lookup"><span data-stu-id="96063-111">Accessed through a simple name.</span></span>|<span data-ttu-id="96063-112">インデックスでアクセスされます。</span><span class="sxs-lookup"><span data-stu-id="96063-112">Accessed through an index.</span></span>|  
|<span data-ttu-id="96063-113">静的メンバーまたはインスタンス メンバーとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="96063-113">Can be a static or an instance member.</span></span>|<span data-ttu-id="96063-114">インスタンス メンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="96063-114">Must be an instance member.</span></span>|  
|<span data-ttu-id="96063-115">プロパティの [get](../../language-reference/keywords/get.md) アクセサーにはパラメーターがありません。</span><span class="sxs-lookup"><span data-stu-id="96063-115">A [get](../../language-reference/keywords/get.md) accessor of a property has no parameters.</span></span>|<span data-ttu-id="96063-116">インデクサーの `get` アクセサーには、インデクサーと同じ仮パラメーター リストがあります。</span><span class="sxs-lookup"><span data-stu-id="96063-116">A `get` accessor of an indexer has the same formal parameter list as the indexer.</span></span>|  
|<span data-ttu-id="96063-117">プロパティの [set](../../language-reference/keywords/set.md) アクセサーには、暗黙の `value` パラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="96063-117">A [set](../../language-reference/keywords/set.md) accessor of a property contains the implicit `value` parameter.</span></span>|<span data-ttu-id="96063-118">インデクサーの `set` アクセサーには、インデクサーと同じ仮パラメーター リストのほか、[value](../../language-reference/keywords/value.md) パラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="96063-118">A `set` accessor of an indexer has the same formal parameter list as the indexer, and also to the [value](../../language-reference/keywords/value.md) parameter.</span></span>|  
|<span data-ttu-id="96063-119">[自動実装プロパティ](../classes-and-structs/auto-implemented-properties.md)を持つ簡略化された構文がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="96063-119">Supports shortened syntax with [Auto-Implemented Properties](../classes-and-structs/auto-implemented-properties.md).</span></span>|<span data-ttu-id="96063-120">インデクサーのみを取得するための式形式メンバーがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="96063-120">Supports expression bodied members for get only indexers.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="96063-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="96063-121">See also</span></span>

- [<span data-ttu-id="96063-122">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="96063-122">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="96063-123">インデクサー</span><span class="sxs-lookup"><span data-stu-id="96063-123">Indexers</span></span>](./index.md)
- [<span data-ttu-id="96063-124">プロパティ</span><span class="sxs-lookup"><span data-stu-id="96063-124">Properties</span></span>](../classes-and-structs/properties.md)
