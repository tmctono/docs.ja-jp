---
title: ベース <typename> のアクセスをアセンブリの外側に展開しているため、'<type>' は <basetypename> '<type>' から継承できません。
ms.date: 07/20/2015
f1_keywords:
- vbc30910
- bc30910
helpviewer_keywords:
- BC30910
ms.assetid: 68fc05c5-5d55-4742-9a3b-ea04312594f4
ms.openlocfilehash: aa04c558abbcc4259c2821cdcbdc1669b91ffee0
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402773"
---
# <a name="typename-cannot-inherit-from-type-basetypename-because-it-expands-the-access-of-the-base-type-outside-the-assembly"></a><span data-ttu-id="b77b5-102">ベース \<typename> のアクセスをアセンブリの外側に展開しているため、'\<type>' は \<basetypename> '\<type>' から継承できません。</span><span class="sxs-lookup"><span data-stu-id="b77b5-102">'\<typename>' cannot inherit from \<type> '\<basetypename>' because it expands the access of the base \<type> outside the assembly</span></span>
<span data-ttu-id="b77b5-103">クラスまたはインターフェイスは、基底クラスまたはインターフェイスから継承されますが、アクセス レベルの制限が緩くなります。</span><span class="sxs-lookup"><span data-stu-id="b77b5-103">A class or interface inherits from a base class or interface but has a less restrictive access level.</span></span>  
  
 <span data-ttu-id="b77b5-104">たとえば、`Public` インターフェイスは `Friend` インターフェイスから継承し、または `Protected` クラスは、`Private` クラスから継承します。</span><span class="sxs-lookup"><span data-stu-id="b77b5-104">For example, a `Public` interface inherits from a `Friend` interface, or a `Protected` class inherits from a `Private` class.</span></span> <span data-ttu-id="b77b5-105">これにより、目的のレベルを超えてアクセスする基底クラスまたはインターフェイスが公開されます。</span><span class="sxs-lookup"><span data-stu-id="b77b5-105">This exposes the base class or interface to access beyond the intended level.</span></span>  
  
 <span data-ttu-id="b77b5-106">**エラー ID:** BC30910</span><span class="sxs-lookup"><span data-stu-id="b77b5-106">**Error ID:** BC30910</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b77b5-107">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="b77b5-107">To correct this error</span></span>  
  
- <span data-ttu-id="b77b5-108">派生クラスまたはインターフェイスのアクセス レベルを、少なくとも基底クラスまたはインターフェイスのアクセス レベルの制限になるように変更します。</span><span class="sxs-lookup"><span data-stu-id="b77b5-108">Change the access level of the derived class or interface to be at least as restrictive as that of the base class or interface.</span></span>  
  
     <span data-ttu-id="b77b5-109">\- または -</span><span class="sxs-lookup"><span data-stu-id="b77b5-109">-or-</span></span>  
  
- <span data-ttu-id="b77b5-110">制限の緩いアクセス レベルが必要な場合は、`Inherits` ステートメントを削除します。</span><span class="sxs-lookup"><span data-stu-id="b77b5-110">If you require the less restrictive access level, remove the `Inherits` statement.</span></span> <span data-ttu-id="b77b5-111">より制限の厳しい基底クラスまたはインターフェイスから継承することはできません。</span><span class="sxs-lookup"><span data-stu-id="b77b5-111">You cannot inherit from a more restricted base class or interface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b77b5-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="b77b5-112">See also</span></span>

- [<span data-ttu-id="b77b5-113">Class ステートメント</span><span class="sxs-lookup"><span data-stu-id="b77b5-113">Class Statement</span></span>](../statements/class-statement.md)
- [<span data-ttu-id="b77b5-114">Interface ステートメント</span><span class="sxs-lookup"><span data-stu-id="b77b5-114">Interface Statement</span></span>](../statements/interface-statement.md)
- [<span data-ttu-id="b77b5-115">Inherits ステートメント</span><span class="sxs-lookup"><span data-stu-id="b77b5-115">Inherits Statement</span></span>](../statements/inherits-statement.md)
- [<span data-ttu-id="b77b5-116">Visual Basic でのアクセス レベル</span><span class="sxs-lookup"><span data-stu-id="b77b5-116">Access levels in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/access-levels.md)
