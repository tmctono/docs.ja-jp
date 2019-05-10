---
title: この 'Sub New' の最初のステートメントは、'MyBase.New' または 'MyClass.New' への呼び出しでなければなりません (パラメーターのないアクセス可能なコンストラクターがありません)。
ms.date: 07/20/2015
f1_keywords:
- bc30148
- vbc30148
helpviewer_keywords:
- BC30148
ms.assetid: 4426e8fc-cb39-4eb8-ba95-503cd32fcc89
ms.openlocfilehash: 160e4d512a1533b3c89a1af50b47600ca6df51c2
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64592055"
---
# <a name="first-statement-of-this-sub-new-must-be-a-call-to-mybasenew-or-myclassnew-no-accessible-constructor-without-parameters"></a><span data-ttu-id="8c092-102">この 'Sub New' の最初のステートメントは、'MyBase.New' または 'MyClass.New' への呼び出しでなければなりません (パラメーターのないアクセス可能なコンストラクターがありません)。</span><span class="sxs-lookup"><span data-stu-id="8c092-102">First statement of this 'Sub New' must be a call to 'MyBase.New' or 'MyClass.New' (No Accessible Constructor Without Parameters)</span></span>
<span data-ttu-id="8c092-103">この 'Sub New' の最初のステートメントは 'mybase.new' または 'myclass.new' への呼び出しをする必要がありますので、基本クラスの\<basename >' の'\<derivedname >' 引数なしで呼び出せるアクセス可能な ' Sub New' はありません。</span><span class="sxs-lookup"><span data-stu-id="8c092-103">First statement of this 'Sub New' must be a call to 'MyBase.New' or 'MyClass.New' because base class '\<basename>' of '\<derivedname>' does not have an accessible 'Sub New' that can be called with no arguments.</span></span>  
  
 <span data-ttu-id="8c092-104">派生クラスでは、すべてのコンス トラクターが基底クラスのコンス トラクターを呼び出す必要があります (`MyBase.New`)。</span><span class="sxs-lookup"><span data-stu-id="8c092-104">In a derived class, every constructor must call a base class constructor (`MyBase.New`).</span></span> <span data-ttu-id="8c092-105">基底クラスが派生クラスでアクセス可能なパラメーターなしのコンス トラクターを持つ場合`MyBase.New`自動的に呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="8c092-105">If the base class has a constructor with no parameters that is accessible to derived classes, `MyBase.New` can be called automatically.</span></span> <span data-ttu-id="8c092-106">できない場合は、パラメーターを持つ基底クラスのコンス トラクターを呼び出す必要があり、自動的に実行できません。</span><span class="sxs-lookup"><span data-stu-id="8c092-106">If not, a base class constructor must be called with parameters, and this cannot be done automatically.</span></span> <span data-ttu-id="8c092-107">この場合、すべての派生クラス コンス トラクターの最初のステートメントは、基本クラスをパラメーター化されたコンス トラクターを呼び出すか、呼び出す基底クラスのコンス トラクターを派生クラスで別のコンス トラクターを呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="8c092-107">In this case, the first statement of every derived class constructor must call a parameterized constructor on the base class, or call another constructor in the derived class that makes a base class constructor call.</span></span>  
  
 <span data-ttu-id="8c092-108">**エラー ID:** BC30148</span><span class="sxs-lookup"><span data-stu-id="8c092-108">**Error ID:** BC30148</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="8c092-109">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="8c092-109">To correct this error</span></span>  
  
- <span data-ttu-id="8c092-110">いずれかの呼び出し`MyBase.New`、必要なパラメーターを指定するか、ピア コンス トラクターが、このような呼び出しを行います。</span><span class="sxs-lookup"><span data-stu-id="8c092-110">Either call `MyBase.New` supplying the required parameters, or call a peer constructor that makes such a call.</span></span>  
  
     <span data-ttu-id="8c092-111">たとえば、基底クラスとして宣言されているコンス トラクターがある`Public Sub New(ByVal index as Integer)`、最初のステートメントで、派生クラスのコンス トラクターがあります`MyBase.New(100)`します。</span><span class="sxs-lookup"><span data-stu-id="8c092-111">For example, if the base class has a constructor that’s declared as `Public Sub New(ByVal index as Integer)`, the first statement in the derived class constructor might be `MyBase.New(100)`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c092-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="8c092-112">See also</span></span>

- [<span data-ttu-id="8c092-113">継承の基本</span><span class="sxs-lookup"><span data-stu-id="8c092-113">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
