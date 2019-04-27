---
title: 引数の値渡しと参照渡しの違い (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- ByRef keyword [Visual Basic], passing arguments by reference
- Visual Basic code, procedures
- procedures [Visual Basic], passing arguments
- ByVal keyword [Visual Basic], passing arguments by value
- arguments [Visual Basic], passing by value or by reference
ms.assetid: 5f5c38fe-3e2d-494c-8fff-f4025b55ec93
ms.openlocfilehash: 1b85941c14721280a5025db442c4793930244ec8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61864547"
---
# <a name="differences-between-passing-an-argument-by-value-and-by-reference-visual-basic"></a><span data-ttu-id="d180d-102">引数の値渡しと参照渡しの違い (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d180d-102">Differences Between Passing an Argument By Value and By Reference (Visual Basic)</span></span>
<span data-ttu-id="d180d-103">プロシージャに 1 つまたは複数の引数を渡すと、ときに、各引数は、呼び出し元のコード内の基になるプログラミング要素に対応します。</span><span class="sxs-lookup"><span data-stu-id="d180d-103">When you pass one or more arguments to a procedure, each argument corresponds to an underlying programming element in the calling code.</span></span> <span data-ttu-id="d180d-104">この基になる要素の値またはへの参照を渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="d180d-104">You can pass either the value of this underlying element, or a reference to it.</span></span> <span data-ttu-id="d180d-105">これと呼ばれますが、*渡し*。</span><span class="sxs-lookup"><span data-stu-id="d180d-105">This is known as the *passing mechanism*.</span></span>  
  
## <a name="passing-by-value"></a><span data-ttu-id="d180d-106">値渡し</span><span class="sxs-lookup"><span data-stu-id="d180d-106">Passing by Value</span></span>  
 <span data-ttu-id="d180d-107">引数を渡す*値によって*指定することによって、 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)プロシージャの定義に対応するパラメーターのキーワード。</span><span class="sxs-lookup"><span data-stu-id="d180d-107">You pass an argument *by value* by specifying the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) keyword for the corresponding parameter in the procedure definition.</span></span> <span data-ttu-id="d180d-108">この渡すメカニズムを使用して、Visual Basic は、プロシージャ内のローカル変数に基になるプログラミング要素の値をコピーします。</span><span class="sxs-lookup"><span data-stu-id="d180d-108">When you use this passing mechanism, Visual Basic copies the value of the underlying programming element into a local variable in the procedure.</span></span> <span data-ttu-id="d180d-109">プロシージャのコードには、呼び出し元のコードで、基になる要素へのアクセスがありません。</span><span class="sxs-lookup"><span data-stu-id="d180d-109">The procedure code does not have any access to the underlying element in the calling code.</span></span>  
  
## <a name="passing-by-reference"></a><span data-ttu-id="d180d-110">参照渡しで渡す</span><span class="sxs-lookup"><span data-stu-id="d180d-110">Passing by Reference</span></span>  
 <span data-ttu-id="d180d-111">引数を渡す*参照によって*指定することによって、 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)プロシージャの定義に対応するパラメーターのキーワード。</span><span class="sxs-lookup"><span data-stu-id="d180d-111">You pass an argument *by reference* by specifying the [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) keyword for the corresponding parameter in the procedure definition.</span></span> <span data-ttu-id="d180d-112">この渡すメカニズムを使用して、Visual Basic により、プロシージャ基になるプログラミング要素への直接参照では呼び出し元のコード。</span><span class="sxs-lookup"><span data-stu-id="d180d-112">When you use this passing mechanism, Visual Basic gives the procedure a direct reference to the underlying programming element in the calling code.</span></span>  
  
## <a name="passing-mechanism-and-element-type"></a><span data-ttu-id="d180d-113">引き渡し方法および要素の型</span><span class="sxs-lookup"><span data-stu-id="d180d-113">Passing Mechanism and Element Type</span></span>  
 <span data-ttu-id="d180d-114">渡す機能の選択は、基になる要素型の分類と同じではありません。</span><span class="sxs-lookup"><span data-stu-id="d180d-114">The choice of passing mechanism is not the same as the classification of the underlying element type.</span></span> <span data-ttu-id="d180d-115">値渡しまたは参照によって渡すことは、プロシージャのコードを提供する Visual Basic を指します。</span><span class="sxs-lookup"><span data-stu-id="d180d-115">Passing by value or by reference refers to what Visual Basic supplies to the procedure code.</span></span> <span data-ttu-id="d180d-116">値型または参照型は、メモリ内プログラミング要素を格納する方法を参照します。</span><span class="sxs-lookup"><span data-stu-id="d180d-116">A value type or reference type refers to how a programming element is stored in memory.</span></span>  
  
 <span data-ttu-id="d180d-117">ただし、引き渡し方法および要素の型は相互にします。</span><span class="sxs-lookup"><span data-stu-id="d180d-117">However, the passing mechanism and element type are interrelated.</span></span> <span data-ttu-id="d180d-118">参照型の値は、メモリ内の他の場所でのデータへのポインターです。</span><span class="sxs-lookup"><span data-stu-id="d180d-118">The value of a reference type is a pointer to the data elsewhere in memory.</span></span> <span data-ttu-id="d180d-119">つまり、基になる要素自体にアクセスできない場合でも値渡しで参照型を渡すときにプロシージャ コードが、基になる要素のデータへのポインターを持っています。</span><span class="sxs-lookup"><span data-stu-id="d180d-119">This means that when you pass a reference type by value, the procedure code has a pointer to the underlying element's data, even though it cannot access the underlying element itself.</span></span> <span data-ttu-id="d180d-120">たとえば、要素が、配列変数の場合は、プロシージャのコードでは、変数自体にアクセスできないが、配列メンバーにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="d180d-120">For example, if the element is an array variable, the procedure code does not have access to the variable itself, but it can access the array members.</span></span>  
  
## <a name="ability-to-modify"></a><span data-ttu-id="d180d-121">変更する権限</span><span class="sxs-lookup"><span data-stu-id="d180d-121">Ability to Modify</span></span>  
 <span data-ttu-id="d180d-122">変更不可能な要素は、引数として渡す、ときに、プロシージャ変更できません呼び出し元のコードで渡されるかどうか`ByVal`または`ByRef`します。</span><span class="sxs-lookup"><span data-stu-id="d180d-122">When you pass a nonmodifiable element as an argument, the procedure can never modify it in the calling code, whether it is passed `ByVal` or `ByRef`.</span></span>  
  
 <span data-ttu-id="d180d-123">変更可能な要素では、次の表では、要素の型と渡し間の相互作用をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="d180d-123">For a modifiable element, the following table summarizes the interaction between the element type and the passing mechanism.</span></span>  
  
|<span data-ttu-id="d180d-124">要素型</span><span class="sxs-lookup"><span data-stu-id="d180d-124">Element type</span></span>|<span data-ttu-id="d180d-125">渡されました。 `ByVal`</span><span class="sxs-lookup"><span data-stu-id="d180d-125">Passed `ByVal`</span></span>|<span data-ttu-id="d180d-126">渡されました。 `ByRef`</span><span class="sxs-lookup"><span data-stu-id="d180d-126">Passed `ByRef`</span></span>|  
|------------------|--------------------|--------------------|  
|<span data-ttu-id="d180d-127">値の型 (値のみを含む)</span><span class="sxs-lookup"><span data-stu-id="d180d-127">Value type (contains only a value)</span></span>|<span data-ttu-id="d180d-128">プロシージャには、変数、またはそのメンバーのいずれかを変更できません。</span><span class="sxs-lookup"><span data-stu-id="d180d-128">The procedure cannot change the variable or any of its members.</span></span>|<span data-ttu-id="d180d-129">プロシージャには、変数とそのメンバーを変更できます。</span><span class="sxs-lookup"><span data-stu-id="d180d-129">The procedure can change the variable and its members.</span></span>|  
|<span data-ttu-id="d180d-130">参照の型 (クラスまたは構造体のインスタンスへのポインターが含まれています)</span><span class="sxs-lookup"><span data-stu-id="d180d-130">Reference type (contains a pointer to a class or structure instance)</span></span>|<span data-ttu-id="d180d-131">プロシージャは、変数を変更することはできませんが、ポイントするインスタンスのメンバーを変更できます。</span><span class="sxs-lookup"><span data-stu-id="d180d-131">The procedure cannot change the variable but can change members of the instance to which it points.</span></span>|<span data-ttu-id="d180d-132">プロシージャには、変数と、ポイントするインスタンスのメンバーを変更できます。</span><span class="sxs-lookup"><span data-stu-id="d180d-132">The procedure can change the variable and members of the instance to which it points.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d180d-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="d180d-133">See also</span></span>

- [<span data-ttu-id="d180d-134">プロシージャ</span><span class="sxs-lookup"><span data-stu-id="d180d-134">Procedures</span></span>](./index.md)
- [<span data-ttu-id="d180d-135">プロシージャのパラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="d180d-135">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="d180d-136">方法: プロシージャに引数を渡す</span><span class="sxs-lookup"><span data-stu-id="d180d-136">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="d180d-137">引数の値渡しと参照渡し</span><span class="sxs-lookup"><span data-stu-id="d180d-137">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="d180d-138">変更できる引数と変更できない引数の違い</span><span class="sxs-lookup"><span data-stu-id="d180d-138">Differences Between Modifiable and Nonmodifiable Arguments</span></span>](./differences-between-modifiable-and-nonmodifiable-arguments.md)
- [<span data-ttu-id="d180d-139">方法: プロシージャ引数の値を変更します。</span><span class="sxs-lookup"><span data-stu-id="d180d-139">How to: Change the Value of a Procedure Argument</span></span>](./how-to-change-the-value-of-a-procedure-argument.md)
- [<span data-ttu-id="d180d-140">方法: プロシージャ引数の値が変化しません。</span><span class="sxs-lookup"><span data-stu-id="d180d-140">How to: Protect a Procedure Argument Against Value Changes</span></span>](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [<span data-ttu-id="d180d-141">方法: 引数の値渡しを強制します。</span><span class="sxs-lookup"><span data-stu-id="d180d-141">How to: Force an Argument to Be Passed by Value</span></span>](./how-to-force-an-argument-to-be-passed-by-value.md)
- [<span data-ttu-id="d180d-142">位置と名前による引数渡し</span><span class="sxs-lookup"><span data-stu-id="d180d-142">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)
- [<span data-ttu-id="d180d-143">値型と参照型</span><span class="sxs-lookup"><span data-stu-id="d180d-143">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
