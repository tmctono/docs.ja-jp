---
title: ベース <typename> のアクセスをアセンブリの外側に展開しているため、'<type>' は <basetypename> '<type>' から継承できません。
ms.date: 07/20/2015
f1_keywords:
- vbc30910
- bc30910
helpviewer_keywords:
- BC30910
ms.assetid: 68fc05c5-5d55-4742-9a3b-ea04312594f4
ms.openlocfilehash: e21eea20d953e64e91522074c25f037451145bf8
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64664209"
---
# <a name="typename-cannot-inherit-from-type-basetypename-because-it-expands-the-access-of-the-base-type-outside-the-assembly"></a><span data-ttu-id="464ad-102">'\<typename >' から継承できません\<型 >'\<basetypename >' ベースのアクセスを展開するので、\<型 >、アセンブリ外</span><span class="sxs-lookup"><span data-stu-id="464ad-102">'\<typename>' cannot inherit from \<type> '\<basetypename>' because it expands the access of the base \<type> outside the assembly</span></span>
<span data-ttu-id="464ad-103">クラスまたはインターフェイスは、基本クラスから継承されているかインターフェイスより制限の少ないアクセス レベル。</span><span class="sxs-lookup"><span data-stu-id="464ad-103">A class or interface inherits from a base class or interface but has a less restrictive access level.</span></span>  
  
 <span data-ttu-id="464ad-104">たとえば、`Public`インターフェイスから継承、`Friend`インターフェイス、または`Protected`クラスから継承、`Private`クラス。</span><span class="sxs-lookup"><span data-stu-id="464ad-104">For example, a `Public` interface inherits from a `Friend` interface, or a `Protected` class inherits from a `Private` class.</span></span> <span data-ttu-id="464ad-105">これは、基底クラスまたはインターフェイスの目的のレベルを超えてへのアクセスに公開します。</span><span class="sxs-lookup"><span data-stu-id="464ad-105">This exposes the base class or interface to access beyond the intended level.</span></span>  
  
 <span data-ttu-id="464ad-106">**エラー ID:** BC30910</span><span class="sxs-lookup"><span data-stu-id="464ad-106">**Error ID:** BC30910</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="464ad-107">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="464ad-107">To correct this error</span></span>  
  
- <span data-ttu-id="464ad-108">派生クラスまたは少なくとも基底クラスまたはインターフェイスの場合と同程度に制限するようにインターフェイスのアクセス レベルを変更します。</span><span class="sxs-lookup"><span data-stu-id="464ad-108">Change the access level of the derived class or interface to be at least as restrictive as that of the base class or interface.</span></span>  
  
     <span data-ttu-id="464ad-109">- または -</span><span class="sxs-lookup"><span data-stu-id="464ad-109">-or-</span></span>  
  
- <span data-ttu-id="464ad-110">制限の少ないアクセス レベルが必要な場合は、削除、`Inherits`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="464ad-110">If you require the less restrictive access level, remove the `Inherits` statement.</span></span> <span data-ttu-id="464ad-111">さらに制限された基底クラスまたはインターフェイスから継承することはできません。</span><span class="sxs-lookup"><span data-stu-id="464ad-111">You cannot inherit from a more restricted base class or interface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="464ad-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="464ad-112">See also</span></span>

- [<span data-ttu-id="464ad-113">Class ステートメント</span><span class="sxs-lookup"><span data-stu-id="464ad-113">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)
- [<span data-ttu-id="464ad-114">Interface ステートメント</span><span class="sxs-lookup"><span data-stu-id="464ad-114">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)
- [<span data-ttu-id="464ad-115">Inherits ステートメント</span><span class="sxs-lookup"><span data-stu-id="464ad-115">Inherits Statement</span></span>](../../../visual-basic/language-reference/statements/inherits-statement.md)
- [<span data-ttu-id="464ad-116">Visual Basic でのアクセス レベル</span><span class="sxs-lookup"><span data-stu-id="464ad-116">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
