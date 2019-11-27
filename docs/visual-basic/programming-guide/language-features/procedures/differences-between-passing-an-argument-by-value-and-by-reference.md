---
title: 引数の値渡しと参照渡しの違い
ms.date: 07/20/2015
helpviewer_keywords:
- ByRef keyword [Visual Basic], passing arguments by reference
- Visual Basic code, procedures
- procedures [Visual Basic], passing arguments
- ByVal keyword [Visual Basic], passing arguments by value
- arguments [Visual Basic], passing by value or by reference
ms.assetid: 5f5c38fe-3e2d-494c-8fff-f4025b55ec93
ms.openlocfilehash: 84ec3bac2532b2cef72ddda347251bc987801c3b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74341230"
---
# <a name="differences-between-passing-an-argument-by-value-and-by-reference-visual-basic"></a><span data-ttu-id="8c227-102">引数の値渡しと参照渡しの違い (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8c227-102">Differences Between Passing an Argument By Value and By Reference (Visual Basic)</span></span>
<span data-ttu-id="8c227-103">プロシージャに1つ以上の引数を渡すと、各引数は、呼び出し元のコード内の基になるプログラミング要素に対応します。</span><span class="sxs-lookup"><span data-stu-id="8c227-103">When you pass one or more arguments to a procedure, each argument corresponds to an underlying programming element in the calling code.</span></span> <span data-ttu-id="8c227-104">この基になる要素の値、またはこの要素への参照を渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="8c227-104">You can pass either the value of this underlying element, or a reference to it.</span></span> <span data-ttu-id="8c227-105">これは、*引き渡しメカニズム*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="8c227-105">This is known as the *passing mechanism*.</span></span>  
  
## <a name="passing-by-value"></a><span data-ttu-id="8c227-106">値渡し</span><span class="sxs-lookup"><span data-stu-id="8c227-106">Passing by Value</span></span>  
 <span data-ttu-id="8c227-107">引数を*値で*渡すには、プロシージャ定義の対応するパラメーターに[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)キーワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="8c227-107">You pass an argument *by value* by specifying the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) keyword for the corresponding parameter in the procedure definition.</span></span> <span data-ttu-id="8c227-108">この引き渡し機構を使用すると、Visual Basic は、基になるプログラミング要素の値をプロシージャのローカル変数にコピーします。</span><span class="sxs-lookup"><span data-stu-id="8c227-108">When you use this passing mechanism, Visual Basic copies the value of the underlying programming element into a local variable in the procedure.</span></span> <span data-ttu-id="8c227-109">プロシージャコードには、呼び出し元のコード内の基になる要素へのアクセス権がありません。</span><span class="sxs-lookup"><span data-stu-id="8c227-109">The procedure code does not have any access to the underlying element in the calling code.</span></span>  
  
## <a name="passing-by-reference"></a><span data-ttu-id="8c227-110">渡す (参照渡しで)</span><span class="sxs-lookup"><span data-stu-id="8c227-110">Passing by Reference</span></span>  
 <span data-ttu-id="8c227-111">*参照で*引数を渡すには、プロシージャ定義の対応するパラメーターに[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)キーワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="8c227-111">You pass an argument *by reference* by specifying the [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) keyword for the corresponding parameter in the procedure definition.</span></span> <span data-ttu-id="8c227-112">この引き渡し機構を使用すると、Visual Basic は、呼び出し元のコード内の基になるプログラミング要素への直接参照をプロシージャに付与します。</span><span class="sxs-lookup"><span data-stu-id="8c227-112">When you use this passing mechanism, Visual Basic gives the procedure a direct reference to the underlying programming element in the calling code.</span></span>  
  
## <a name="passing-mechanism-and-element-type"></a><span data-ttu-id="8c227-113">渡す (機構と要素の型を)</span><span class="sxs-lookup"><span data-stu-id="8c227-113">Passing Mechanism and Element Type</span></span>  
 <span data-ttu-id="8c227-114">渡す機構の選択は、基になる要素型の分類と同じではありません。</span><span class="sxs-lookup"><span data-stu-id="8c227-114">The choice of passing mechanism is not the same as the classification of the underlying element type.</span></span> <span data-ttu-id="8c227-115">値渡しまたは参照渡しでは、プロシージャコードに提供される Visual Basic が参照されます。</span><span class="sxs-lookup"><span data-stu-id="8c227-115">Passing by value or by reference refers to what Visual Basic supplies to the procedure code.</span></span> <span data-ttu-id="8c227-116">値型または参照型は、プログラミング要素がどのようにメモリに格納されるかを示します。</span><span class="sxs-lookup"><span data-stu-id="8c227-116">A value type or reference type refers to how a programming element is stored in memory.</span></span>  
  
 <span data-ttu-id="8c227-117">ただし、渡すメカニズムと要素の型は相互に関連しています。</span><span class="sxs-lookup"><span data-stu-id="8c227-117">However, the passing mechanism and element type are interrelated.</span></span> <span data-ttu-id="8c227-118">参照型の値は、メモリ内の別の場所にあるデータへのポインターです。</span><span class="sxs-lookup"><span data-stu-id="8c227-118">The value of a reference type is a pointer to the data elsewhere in memory.</span></span> <span data-ttu-id="8c227-119">これは、参照型を値で渡す場合、基になる要素自体にアクセスできない場合でも、プロシージャコードには基になる要素のデータへのポインターがあることを意味します。</span><span class="sxs-lookup"><span data-stu-id="8c227-119">This means that when you pass a reference type by value, the procedure code has a pointer to the underlying element's data, even though it cannot access the underlying element itself.</span></span> <span data-ttu-id="8c227-120">たとえば、要素が配列変数の場合、プロシージャコードは変数自体にアクセスすることはできませんが、配列のメンバーにアクセスすることはできます。</span><span class="sxs-lookup"><span data-stu-id="8c227-120">For example, if the element is an array variable, the procedure code does not have access to the variable itself, but it can access the array members.</span></span>  
  
## <a name="ability-to-modify"></a><span data-ttu-id="8c227-121">変更する機能</span><span class="sxs-lookup"><span data-stu-id="8c227-121">Ability to Modify</span></span>  
 <span data-ttu-id="8c227-122">変更できない要素を引数として渡すと、その要素が `ByVal` または `ByRef`に渡されたかどうかにかかわらず、呼び出し元のコードでプロシージャを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="8c227-122">When you pass a nonmodifiable element as an argument, the procedure can never modify it in the calling code, whether it is passed `ByVal` or `ByRef`.</span></span>  
  
 <span data-ttu-id="8c227-123">変更可能な要素の場合、次の表は、要素の型と渡す機構の相互作用をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="8c227-123">For a modifiable element, the following table summarizes the interaction between the element type and the passing mechanism.</span></span>  
  
|<span data-ttu-id="8c227-124">要素型</span><span class="sxs-lookup"><span data-stu-id="8c227-124">Element type</span></span>|<span data-ttu-id="8c227-125">渡された `ByVal`</span><span class="sxs-lookup"><span data-stu-id="8c227-125">Passed `ByVal`</span></span>|<span data-ttu-id="8c227-126">渡された `ByRef`</span><span class="sxs-lookup"><span data-stu-id="8c227-126">Passed `ByRef`</span></span>|  
|------------------|--------------------|--------------------|  
|<span data-ttu-id="8c227-127">値の型 (値のみを含む)</span><span class="sxs-lookup"><span data-stu-id="8c227-127">Value type (contains only a value)</span></span>|<span data-ttu-id="8c227-128">プロシージャでは、変数またはそのメンバーを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="8c227-128">The procedure cannot change the variable or any of its members.</span></span>|<span data-ttu-id="8c227-129">プロシージャは、変数とそのメンバーを変更できます。</span><span class="sxs-lookup"><span data-stu-id="8c227-129">The procedure can change the variable and its members.</span></span>|  
|<span data-ttu-id="8c227-130">参照型 (クラスまたは構造体のインスタンスへのポインターを含む)</span><span class="sxs-lookup"><span data-stu-id="8c227-130">Reference type (contains a pointer to a class or structure instance)</span></span>|<span data-ttu-id="8c227-131">プロシージャは変数を変更できませんが、参照先のインスタンスのメンバーを変更することはできます。</span><span class="sxs-lookup"><span data-stu-id="8c227-131">The procedure cannot change the variable but can change members of the instance to which it points.</span></span>|<span data-ttu-id="8c227-132">プロシージャは、参照先のインスタンスの変数とメンバーを変更できます。</span><span class="sxs-lookup"><span data-stu-id="8c227-132">The procedure can change the variable and members of the instance to which it points.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8c227-133">参照</span><span class="sxs-lookup"><span data-stu-id="8c227-133">See also</span></span>

- [<span data-ttu-id="8c227-134">手順</span><span class="sxs-lookup"><span data-stu-id="8c227-134">Procedures</span></span>](./index.md)
- [<span data-ttu-id="8c227-135">プロシージャのパラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="8c227-135">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="8c227-136">方法: プロシージャに引数を渡す</span><span class="sxs-lookup"><span data-stu-id="8c227-136">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="8c227-137">引数の値渡しと参照渡し</span><span class="sxs-lookup"><span data-stu-id="8c227-137">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="8c227-138">変更できる引数と変更できない引数の違い</span><span class="sxs-lookup"><span data-stu-id="8c227-138">Differences Between Modifiable and Nonmodifiable Arguments</span></span>](./differences-between-modifiable-and-nonmodifiable-arguments.md)
- [<span data-ttu-id="8c227-139">方法: プロシージャ引数の値を変更する</span><span class="sxs-lookup"><span data-stu-id="8c227-139">How to: Change the Value of a Procedure Argument</span></span>](./how-to-change-the-value-of-a-procedure-argument.md)
- [<span data-ttu-id="8c227-140">方法: プロシージャ引数の値が変化しないようにする</span><span class="sxs-lookup"><span data-stu-id="8c227-140">How to: Protect a Procedure Argument Against Value Changes</span></span>](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [<span data-ttu-id="8c227-141">方法: 引数の値渡しを強制する</span><span class="sxs-lookup"><span data-stu-id="8c227-141">How to: Force an Argument to Be Passed by Value</span></span>](./how-to-force-an-argument-to-be-passed-by-value.md)
- [<span data-ttu-id="8c227-142">位置と名前による引数渡し</span><span class="sxs-lookup"><span data-stu-id="8c227-142">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)
- [<span data-ttu-id="8c227-143">値型と参照型</span><span class="sxs-lookup"><span data-stu-id="8c227-143">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
