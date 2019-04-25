---
title: この 'Sub New' の最初のステートメントは、'MyBase.New' または 'MyClass.New' への呼び出しでなければなりません (パラメーターのないアクセス可能なコンストラクターがありません)。
ms.date: 07/20/2015
f1_keywords:
- bc30148
- vbc30148
helpviewer_keywords:
- BC30148
ms.assetid: 4426e8fc-cb39-4eb8-ba95-503cd32fcc89
ms.openlocfilehash: debab4e495d05a05801dd11850d0665c8bd6b299
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61801375"
---
# <a name="first-statement-of-this-sub-new-must-be-a-call-to-mybasenew-or-myclassnew-no-accessible-constructor-without-parameters"></a><span data-ttu-id="79fa3-102">この 'Sub New' の最初のステートメントは、'MyBase.New' または 'MyClass.New' への呼び出しでなければなりません (パラメーターのないアクセス可能なコンストラクターがありません)。</span><span class="sxs-lookup"><span data-stu-id="79fa3-102">First statement of this 'Sub New' must be a call to 'MyBase.New' or 'MyClass.New' (No Accessible Constructor Without Parameters)</span></span>
<span data-ttu-id="79fa3-103">この 'Sub New' の最初のステートメントは 'mybase.new' または 'myclass.new' への呼び出しをする必要がありますので、基本クラスの\<basename >' の'\<derivedname >' 引数なしで呼び出せるアクセス可能な ' Sub New' はありません。</span><span class="sxs-lookup"><span data-stu-id="79fa3-103">First statement of this 'Sub New' must be a call to 'MyBase.New' or 'MyClass.New' because base class '\<basename>' of '\<derivedname>' does not have an accessible 'Sub New' that can be called with no arguments.</span></span>  
  
 <span data-ttu-id="79fa3-104">派生クラスでは、すべてのコンス トラクターが基底クラスのコンス トラクターを呼び出す必要があります (`MyBase.New`)。</span><span class="sxs-lookup"><span data-stu-id="79fa3-104">In a derived class, every constructor must call a base class constructor (`MyBase.New`).</span></span> <span data-ttu-id="79fa3-105">基底クラスが派生クラスでアクセス可能なパラメーターなしのコンス トラクターを持つ場合`MyBase.New`自動的に呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="79fa3-105">If the base class has a constructor with no parameters that is accessible to derived classes, `MyBase.New` can be called automatically.</span></span> <span data-ttu-id="79fa3-106">できない場合は、パラメーターを持つ基底クラスのコンス トラクターを呼び出す必要があり、自動的に実行できません。</span><span class="sxs-lookup"><span data-stu-id="79fa3-106">If not, a base class constructor must be called with parameters, and this cannot be done automatically.</span></span> <span data-ttu-id="79fa3-107">この場合、すべての派生クラス コンス トラクターの最初のステートメントは、基本クラスをパラメーター化されたコンス トラクターを呼び出すか、呼び出す基底クラスのコンス トラクターを派生クラスで別のコンス トラクターを呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="79fa3-107">In this case, the first statement of every derived class constructor must call a parameterized constructor on the base class, or call another constructor in the derived class that makes a base class constructor call.</span></span>  
  
 <span data-ttu-id="79fa3-108">**エラー ID:** BC30148</span><span class="sxs-lookup"><span data-stu-id="79fa3-108">**Error ID:** BC30148</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="79fa3-109">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="79fa3-109">To correct this error</span></span>  
  
-   <span data-ttu-id="79fa3-110">いずれかの呼び出し`MyBase.New`、必要なパラメーターを指定するか、ピア コンス トラクターが、このような呼び出しを行います。</span><span class="sxs-lookup"><span data-stu-id="79fa3-110">Either call `MyBase.New` supplying the required parameters, or call a peer constructor that makes such a call.</span></span>  
  
     <span data-ttu-id="79fa3-111">たとえば、基底クラスとして宣言されているコンス トラクターがある`Public Sub New(ByVal index as Integer)`、最初のステートメントで、派生クラスのコンス トラクターがあります`MyBase.New(100)`します。</span><span class="sxs-lookup"><span data-stu-id="79fa3-111">For example, if the base class has a constructor that’s declared as `Public Sub New(ByVal index as Integer)`, the first statement in the derived class constructor might be `MyBase.New(100)`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79fa3-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="79fa3-112">See also</span></span>

- [<span data-ttu-id="79fa3-113">継承の基本</span><span class="sxs-lookup"><span data-stu-id="79fa3-113">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
