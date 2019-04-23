---
title: コンストラクター '<name>' はそれ自体を呼び出すことはできません。
ms.date: 07/20/2015
f1_keywords:
- bc30298
- vbc30298
helpviewer_keywords:
- BC30298
ms.assetid: 2d77b7f4-0640-4f89-9c65-f101fd2847c0
ms.openlocfilehash: 8459ee7fec6d761161a721c88ccdc88e513fc95f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59324384"
---
# <a name="constructor-name-cannot-call-itself"></a><span data-ttu-id="46b1c-102">コンス トラクター '\<名 >' 自体を呼び出すことはできません</span><span class="sxs-lookup"><span data-stu-id="46b1c-102">Constructor '\<name>' cannot call itself</span></span>
<span data-ttu-id="46b1c-103">A`Sub New`クラスまたは構造体でプロシージャを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="46b1c-103">A `Sub New` procedure in a class or structure calls itself.</span></span>  
  
 <span data-ttu-id="46b1c-104">コンス トラクターの目的は、クラスのインスタンスを初期化するために、またはそのが最初に構造を作成します。</span><span class="sxs-lookup"><span data-stu-id="46b1c-104">The purpose of a constructor is to initialize an instance of a class or structure when it is first created.</span></span> <span data-ttu-id="46b1c-105">異なるパラメーター リストがすべて、クラスまたは構造体によって複数のコンス トラクター、することができます。</span><span class="sxs-lookup"><span data-stu-id="46b1c-105">A class or structure can have several constructors, provided they all have different parameter lists.</span></span> <span data-ttu-id="46b1c-106">コンス トラクターは、独自に加え、その機能を実行する別のコンス トラクターを呼び出す許可されています。</span><span class="sxs-lookup"><span data-stu-id="46b1c-106">A constructor is permitted to call another constructor to perform its functionality in addition to its own.</span></span> <span data-ttu-id="46b1c-107">コンス トラクターを呼び出す意味がありませんし、許可されている場合、無限再帰の結果が実際にします。</span><span class="sxs-lookup"><span data-stu-id="46b1c-107">But it is meaningless for a constructor to call itself, and in fact it would result in infinite recursion if permitted.</span></span>  
  
 <span data-ttu-id="46b1c-108">**エラー ID:** BC30298</span><span class="sxs-lookup"><span data-stu-id="46b1c-108">**Error ID:** BC30298</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="46b1c-109">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="46b1c-109">To correct this error</span></span>  
  
1. <span data-ttu-id="46b1c-110">呼び出されるコンス トラクターのパラメーター リストを確認します。</span><span class="sxs-lookup"><span data-stu-id="46b1c-110">Check the parameter list of the constructor being called.</span></span> <span data-ttu-id="46b1c-111">コンス トラクターの呼び出しを行うのと異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="46b1c-111">It should be different from that of the constructor making the call.</span></span>  
  
2. <span data-ttu-id="46b1c-112">別のコンス トラクターを呼び出すしない場合は、削除、`Sub New`完全呼び出します。</span><span class="sxs-lookup"><span data-stu-id="46b1c-112">If you do not intend to call a different constructor, remove the `Sub New` call entirely.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46b1c-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="46b1c-113">See also</span></span>

- [<span data-ttu-id="46b1c-114">オブジェクトの有効期間:オブジェクトを作成および破棄する方法</span><span class="sxs-lookup"><span data-stu-id="46b1c-114">Object Lifetime: How Objects Are Created and Destroyed</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
