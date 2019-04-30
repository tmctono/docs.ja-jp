---
title: Protected Friend (Visual Basic)
ms.date: 05/10/2018
helpviewer_keywords:
- Protected Friend keyword [Visual Basic]
- Protected Friend keyword [Visual Basic], syntax
ms.openlocfilehash: 331c63dc290d4096e8158f265ee869b47743a273
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62053887"
---
# <a name="protected-friend-visual-basic"></a><span data-ttu-id="fdc1e-102">Protected Friend (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fdc1e-102">Protected Friend (Visual Basic)</span></span>

<span data-ttu-id="fdc1e-103">キーワード組み合わせ `Protected Friend` はメンバー アクセス修飾子です。</span><span class="sxs-lookup"><span data-stu-id="fdc1e-103">The `Protected Friend` keyword combination is a member access modifier.</span></span> <span data-ttu-id="fdc1e-104">両方を設定する[フレンド](friend.md)アクセスと[Protected](protected.md)および派生クラス独自のクラスからは、同じアセンブリ内の任意の場所からアクセスできるように、宣言された要素へのアクセス。</span><span class="sxs-lookup"><span data-stu-id="fdc1e-104">It confers both [Friend](friend.md) access and [Protected](protected.md) access on the declared elements, so they are accessible from anywhere in the same assembly, from their own class, and from derived classes.</span></span> <span data-ttu-id="fdc1e-105">指定できます`Protected Friend`クラスのメンバーにのみ適用することはできません`Protected Friend`構造体のメンバーに構造体は継承できないためです。</span><span class="sxs-lookup"><span data-stu-id="fdc1e-105">You can specify `Protected Friend` only on members of classes; you cannot apply `Protected Friend` to members of a structure because structures cannot be inherited.</span></span>

> [!NOTE]
> <span data-ttu-id="fdc1e-106">Visual Studio での F1 ヘルプを選択する`protected friend`のいずれかのヘルプを提供します。[保護](protected.md)または[フレンド](friend.md)します。</span><span class="sxs-lookup"><span data-stu-id="fdc1e-106">In Visual Studio, selecting F1 help on `protected friend` provides help for either [protected](protected.md) or [friend](friend.md).</span></span> <span data-ttu-id="fdc1e-107">IDE では、複合語ではなく、カーソルの下の 1 つのトークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="fdc1e-107">The IDE picks the single token under the cursor rather than the compound word.</span></span>

## <a name="rules"></a><span data-ttu-id="fdc1e-108">ルール</span><span class="sxs-lookup"><span data-stu-id="fdc1e-108">Rules</span></span>

- <span data-ttu-id="fdc1e-109">**宣言コンテキスト。**</span><span class="sxs-lookup"><span data-stu-id="fdc1e-109">**Declaration Context.**</span></span> <span data-ttu-id="fdc1e-110">使用することができます`Protected Friend`クラス レベルでのみです。</span><span class="sxs-lookup"><span data-stu-id="fdc1e-110">You can use `Protected Friend` only at the class level.</span></span> <span data-ttu-id="fdc1e-111">これは、意味の宣言のコンテキストを`Protected`要素は、クラスでなければなりませんし、ソース ファイル、名前空間、インターフェイス、モジュール、構造体、またはプロシージャにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="fdc1e-111">This means the declaration context for a `Protected` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span> 

## <a name="see-also"></a><span data-ttu-id="fdc1e-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="fdc1e-112">See also</span></span>

- [<span data-ttu-id="fdc1e-113">Public</span><span class="sxs-lookup"><span data-stu-id="fdc1e-113">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="fdc1e-114">Protected</span><span class="sxs-lookup"><span data-stu-id="fdc1e-114">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="fdc1e-115">Friend</span><span class="sxs-lookup"><span data-stu-id="fdc1e-115">Friend</span></span>](friend.md)
- [<span data-ttu-id="fdc1e-116">Private</span><span class="sxs-lookup"><span data-stu-id="fdc1e-116">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="fdc1e-117">Private Protected</span><span class="sxs-lookup"><span data-stu-id="fdc1e-117">Private Protected</span></span>](./private-protected.md)
- [<span data-ttu-id="fdc1e-118">Visual Basic でのアクセス レベル</span><span class="sxs-lookup"><span data-stu-id="fdc1e-118">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="fdc1e-119">プロシージャ</span><span class="sxs-lookup"><span data-stu-id="fdc1e-119">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="fdc1e-120">構造体</span><span class="sxs-lookup"><span data-stu-id="fdc1e-120">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="fdc1e-121">クラスとオブジェクト</span><span class="sxs-lookup"><span data-stu-id="fdc1e-121">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
