---
title: この 'Sub New' の最初のステートメントは、'MyBase.New' または 'MyClass.New' への呼び出しでなければなりません (パラメーターのないアクセス可能なコンストラクターがありません)。
ms.date: 07/20/2015
f1_keywords:
- bc30148
- vbc30148
helpviewer_keywords:
- BC30148
ms.assetid: 4426e8fc-cb39-4eb8-ba95-503cd32fcc89
ms.openlocfilehash: 2b9d2568fb64e4af72733ad1f3dee58aaee650e5
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402980"
---
# <a name="first-statement-of-this-sub-new-must-be-a-call-to-mybasenew-or-myclassnew-no-accessible-constructor-without-parameters"></a><span data-ttu-id="76a6a-102">この 'Sub New' の最初のステートメントは、'MyBase.New' または 'MyClass.New' への呼び出しでなければなりません (パラメーターのないアクセス可能なコンストラクターがありません)。</span><span class="sxs-lookup"><span data-stu-id="76a6a-102">First statement of this 'Sub New' must be a call to 'MyBase.New' or 'MyClass.New' (No Accessible Constructor Without Parameters)</span></span>
<span data-ttu-id="76a6a-103">'\<derivedname>' の基底クラス '\<basename>' には、引数なしで呼び出すことができる、アクセス可能な 'Sub New' がないため、この 'Sub New' の最初のステートメントは、'MyBase.New' または 'MyClass.New' に対して呼び出さなければなりません。</span><span class="sxs-lookup"><span data-stu-id="76a6a-103">First statement of this 'Sub New' must be a call to 'MyBase.New' or 'MyClass.New' because base class '\<basename>' of '\<derivedname>' does not have an accessible 'Sub New' that can be called with no arguments.</span></span>  
  
 <span data-ttu-id="76a6a-104">派生クラスでは、すべてのコンストラクターが基底クラスのコンストラクター (`MyBase.New`) を呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="76a6a-104">In a derived class, every constructor must call a base class constructor (`MyBase.New`).</span></span> <span data-ttu-id="76a6a-105">基底クラスに、派生クラスにアクセスできるパラメーターがないコンストラクターがある場合は、`MyBase.New` を自動的に呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="76a6a-105">If the base class has a constructor with no parameters that is accessible to derived classes, `MyBase.New` can be called automatically.</span></span> <span data-ttu-id="76a6a-106">それ以外の場合、基底クラスのコンストラクターはパラメーターを指定して呼び出す必要があり、これを自動的に実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="76a6a-106">If not, a base class constructor must be called with parameters, and this cannot be done automatically.</span></span> <span data-ttu-id="76a6a-107">この場合、すべての派生クラスのコンストラクターの最初のステートメントは、基底クラスのパラメーター化されたコンストラクターを呼び出すか、または基底クラスのコンストラクター呼び出しを行う派生クラス内の別のコンストラクターを呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="76a6a-107">In this case, the first statement of every derived class constructor must call a parameterized constructor on the base class, or call another constructor in the derived class that makes a base class constructor call.</span></span>  
  
 <span data-ttu-id="76a6a-108">**エラー ID:** BC30148</span><span class="sxs-lookup"><span data-stu-id="76a6a-108">**Error ID:** BC30148</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="76a6a-109">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="76a6a-109">To correct this error</span></span>  
  
- <span data-ttu-id="76a6a-110">必要なパラメーターを指定して `MyBase.New` を呼び出すか、このような呼び出しを行うピア コンストラクターを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="76a6a-110">Either call `MyBase.New` supplying the required parameters, or call a peer constructor that makes such a call.</span></span>  
  
     <span data-ttu-id="76a6a-111">たとえば、基底クラスに `Public Sub New(ByVal index as Integer)` として宣言されたコンストラクターがある場合、派生クラスのコンストラクターの最初のステートメントは `MyBase.New(100)` である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="76a6a-111">For example, if the base class has a constructor that’s declared as `Public Sub New(ByVal index as Integer)`, the first statement in the derived class constructor might be `MyBase.New(100)`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76a6a-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="76a6a-112">See also</span></span>

- [<span data-ttu-id="76a6a-113">継承の基本</span><span class="sxs-lookup"><span data-stu-id="76a6a-113">Inheritance Basics</span></span>](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)
