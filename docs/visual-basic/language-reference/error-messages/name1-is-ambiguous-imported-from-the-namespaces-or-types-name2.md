---
title: "'<name1>' 名前空間または型からインポートされた '<name2>' があいまいです。"
ms.date: 07/20/2015
f1_keywords:
- vbc30561
- bc30561
helpviewer_keywords:
- BC30561
ms.assetid: 761091f7-1018-4299-b481-3966a4a2c126
ms.openlocfilehash: fe67dc70c18297319225c3d2ae97f1ce949603d6
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871536"
---
# <a name="name1-is-ambiguous-imported-from-the-namespaces-or-types-name2"></a><span data-ttu-id="66626-102">'\<name1>' 名前空間または型からインポートされた '\<name2>' があいまいです。</span><span class="sxs-lookup"><span data-stu-id="66626-102">'\<name1>' is ambiguous, imported from the namespaces or types '\<name2>'</span></span>

<span data-ttu-id="66626-103">あいまいな名前を指定したため、別の名前と競合しています。</span><span class="sxs-lookup"><span data-stu-id="66626-103">You have provided a name that is ambiguous and therefore conflicts with another name.</span></span> <span data-ttu-id="66626-104">Visual Basic コンパイラには、競合解決規則がありません。ユーザー自身が名前のあいまいさを解消する必要があります。</span><span class="sxs-lookup"><span data-stu-id="66626-104">The Visual Basic compiler does not have any conflict resolution rules; you must disambiguate names yourself.</span></span>  
  
 <span data-ttu-id="66626-105">**エラー ID:** BC30561</span><span class="sxs-lookup"><span data-stu-id="66626-105">**Error ID:** BC30561</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="66626-106">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="66626-106">To correct this error</span></span>  
  
1. <span data-ttu-id="66626-107">名前空間のインポートを削除して、名前のあいまいさをなくします。</span><span class="sxs-lookup"><span data-stu-id="66626-107">Disambiguate the name by removing namespace imports.</span></span>  
  
2. <span data-ttu-id="66626-108">名前を完全修飾します。</span><span class="sxs-lookup"><span data-stu-id="66626-108">Fully qualify the name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66626-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="66626-109">See also</span></span>

- [<span data-ttu-id="66626-110">Imports ステートメント (.NET 名前空間および型)</span><span class="sxs-lookup"><span data-stu-id="66626-110">Imports Statement (.NET Namespace and Type)</span></span>](../statements/imports-statement-net-namespace-and-type.md)
- [<span data-ttu-id="66626-111">Visual Basic における名前空間</span><span class="sxs-lookup"><span data-stu-id="66626-111">Namespaces in Visual Basic</span></span>](../../programming-guide/program-structure/namespaces.md)
- [<span data-ttu-id="66626-112">Namespace ステートメント</span><span class="sxs-lookup"><span data-stu-id="66626-112">Namespace Statement</span></span>](../statements/namespace-statement.md)
