---
title: プロシージャのオーバーロード
ms.date: 07/20/2015
helpviewer_keywords:
- signatures
- Overloads keyword [Visual Basic]
- hiding by signature
- Visual Basic code, procedures
- procedures [Visual Basic], signatures for
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
- parameters [Visual Basic], lists
- signatures [Visual Basic], procedure
- parameter lists [Visual Basic]
- Visual Basic code, parameter lists
- Shadows keyword [Visual Basic]
- procedure overloading
- procedures [Visual Basic], parameter lists
ms.assetid: fbc7fb18-e3b2-48b6-b554-64c00ed09d2a
ms.openlocfilehash: 41a971896fe726cbe9849fd46334910e7288afe0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352598"
---
# <a name="procedure-overloading-visual-basic"></a><span data-ttu-id="45f8e-102">プロシージャのオーバーロード (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="45f8e-102">Procedure Overloading (Visual Basic)</span></span>

<span data-ttu-id="45f8e-103">*Overloading* a procedure means defining it in multiple versions, using the same name but different parameter lists.</span><span class="sxs-lookup"><span data-stu-id="45f8e-103">*Overloading* a procedure means defining it in multiple versions, using the same name but different parameter lists.</span></span> <span data-ttu-id="45f8e-104">The purpose of overloading is to define several closely related versions of a procedure without having to differentiate them by name.</span><span class="sxs-lookup"><span data-stu-id="45f8e-104">The purpose of overloading is to define several closely related versions of a procedure without having to differentiate them by name.</span></span> <span data-ttu-id="45f8e-105">You do this by varying the parameter list.</span><span class="sxs-lookup"><span data-stu-id="45f8e-105">You do this by varying the parameter list.</span></span>

## <a name="overloading-rules"></a><span data-ttu-id="45f8e-106">Overloading Rules</span><span class="sxs-lookup"><span data-stu-id="45f8e-106">Overloading Rules</span></span>

<span data-ttu-id="45f8e-107">When you overload a procedure, the following rules apply:</span><span class="sxs-lookup"><span data-stu-id="45f8e-107">When you overload a procedure, the following rules apply:</span></span>

- <span data-ttu-id="45f8e-108">**Same Name**.</span><span class="sxs-lookup"><span data-stu-id="45f8e-108">**Same Name**.</span></span> <span data-ttu-id="45f8e-109">Each overloaded version must use the same procedure name.</span><span class="sxs-lookup"><span data-stu-id="45f8e-109">Each overloaded version must use the same procedure name.</span></span>

- <span data-ttu-id="45f8e-110">**Different Signature**.</span><span class="sxs-lookup"><span data-stu-id="45f8e-110">**Different Signature**.</span></span> <span data-ttu-id="45f8e-111">Each overloaded version must differ from all other overloaded versions in at least one of the following respects:</span><span class="sxs-lookup"><span data-stu-id="45f8e-111">Each overloaded version must differ from all other overloaded versions in at least one of the following respects:</span></span>

  - <span data-ttu-id="45f8e-112">Number of parameters</span><span class="sxs-lookup"><span data-stu-id="45f8e-112">Number of parameters</span></span>

  - <span data-ttu-id="45f8e-113">Order of the parameters</span><span class="sxs-lookup"><span data-stu-id="45f8e-113">Order of the parameters</span></span>

  - <span data-ttu-id="45f8e-114">Data types of the parameters</span><span class="sxs-lookup"><span data-stu-id="45f8e-114">Data types of the parameters</span></span>

  - <span data-ttu-id="45f8e-115">Number of type parameters (for a generic procedure)</span><span class="sxs-lookup"><span data-stu-id="45f8e-115">Number of type parameters (for a generic procedure)</span></span>

  - <span data-ttu-id="45f8e-116">Return type (only for a conversion operator)</span><span class="sxs-lookup"><span data-stu-id="45f8e-116">Return type (only for a conversion operator)</span></span>

  <span data-ttu-id="45f8e-117">Together with the procedure name, the preceding items are collectively called the *signature* of the procedure.</span><span class="sxs-lookup"><span data-stu-id="45f8e-117">Together with the procedure name, the preceding items are collectively called the *signature* of the procedure.</span></span> <span data-ttu-id="45f8e-118">When you call an overloaded procedure, the compiler uses the signature to check that the call correctly matches the definition.</span><span class="sxs-lookup"><span data-stu-id="45f8e-118">When you call an overloaded procedure, the compiler uses the signature to check that the call correctly matches the definition.</span></span>

- <span data-ttu-id="45f8e-119">**Items Not Part of Signature**.</span><span class="sxs-lookup"><span data-stu-id="45f8e-119">**Items Not Part of Signature**.</span></span> <span data-ttu-id="45f8e-120">You cannot overload a procedure without varying the signature.</span><span class="sxs-lookup"><span data-stu-id="45f8e-120">You cannot overload a procedure without varying the signature.</span></span> <span data-ttu-id="45f8e-121">In particular, you cannot overload a procedure by varying only one or more of the following items:</span><span class="sxs-lookup"><span data-stu-id="45f8e-121">In particular, you cannot overload a procedure by varying only one or more of the following items:</span></span>

  - <span data-ttu-id="45f8e-122">Procedure modifier keywords, such as `Public`, `Shared`, and `Static`</span><span class="sxs-lookup"><span data-stu-id="45f8e-122">Procedure modifier keywords, such as `Public`, `Shared`, and `Static`</span></span>

  - <span data-ttu-id="45f8e-123">Parameter or type parameter names</span><span class="sxs-lookup"><span data-stu-id="45f8e-123">Parameter or type parameter names</span></span>

  - <span data-ttu-id="45f8e-124">Type parameter constraints (for a generic procedure)</span><span class="sxs-lookup"><span data-stu-id="45f8e-124">Type parameter constraints (for a generic procedure)</span></span>

  - <span data-ttu-id="45f8e-125">Parameter modifier keywords, such as `ByRef` and `Optional`</span><span class="sxs-lookup"><span data-stu-id="45f8e-125">Parameter modifier keywords, such as `ByRef` and `Optional`</span></span>

  - <span data-ttu-id="45f8e-126">Whether it returns a value</span><span class="sxs-lookup"><span data-stu-id="45f8e-126">Whether it returns a value</span></span>

  - <span data-ttu-id="45f8e-127">The data type of the return value (except for a conversion operator)</span><span class="sxs-lookup"><span data-stu-id="45f8e-127">The data type of the return value (except for a conversion operator)</span></span>

  <span data-ttu-id="45f8e-128">The items in the preceding list are not part of the signature.</span><span class="sxs-lookup"><span data-stu-id="45f8e-128">The items in the preceding list are not part of the signature.</span></span> <span data-ttu-id="45f8e-129">Although you cannot use them to differentiate between overloaded versions, you can vary them among overloaded versions that are properly differentiated by their signatures.</span><span class="sxs-lookup"><span data-stu-id="45f8e-129">Although you cannot use them to differentiate between overloaded versions, you can vary them among overloaded versions that are properly differentiated by their signatures.</span></span>

- <span data-ttu-id="45f8e-130">**Late-Bound Arguments**.</span><span class="sxs-lookup"><span data-stu-id="45f8e-130">**Late-Bound Arguments**.</span></span> <span data-ttu-id="45f8e-131">If you intend to pass a late bound object variable to an overloaded version, you must declare the appropriate parameter as <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="45f8e-131">If you intend to pass a late bound object variable to an overloaded version, you must declare the appropriate parameter as <xref:System.Object>.</span></span>

## <a name="multiple-versions-of-a-procedure"></a><span data-ttu-id="45f8e-132">Multiple Versions of a Procedure</span><span class="sxs-lookup"><span data-stu-id="45f8e-132">Multiple Versions of a Procedure</span></span>

<span data-ttu-id="45f8e-133">Suppose you are writing a `Sub` procedure to post a transaction against a customer's balance, and you want to be able to refer to the customer either by name or by account number.</span><span class="sxs-lookup"><span data-stu-id="45f8e-133">Suppose you are writing a `Sub` procedure to post a transaction against a customer's balance, and you want to be able to refer to the customer either by name or by account number.</span></span> <span data-ttu-id="45f8e-134">To accommodate this, you can define two different `Sub` procedures, as in the following example:</span><span class="sxs-lookup"><span data-stu-id="45f8e-134">To accommodate this, you can define two different `Sub` procedures, as in the following example:</span></span>

[!code-vb[VbVbcnProcedures#73](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#73)]

### <a name="overloaded-versions"></a><span data-ttu-id="45f8e-135">Overloaded Versions</span><span class="sxs-lookup"><span data-stu-id="45f8e-135">Overloaded Versions</span></span>

<span data-ttu-id="45f8e-136">An alternative is to overload a single procedure name.</span><span class="sxs-lookup"><span data-stu-id="45f8e-136">An alternative is to overload a single procedure name.</span></span> <span data-ttu-id="45f8e-137">You can use the [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) keyword to define a version of the procedure for each parameter list, as follows:</span><span class="sxs-lookup"><span data-stu-id="45f8e-137">You can use the [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) keyword to define a version of the procedure for each parameter list, as follows:</span></span>

[!code-vb[VbVbcnProcedures#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#72)]

#### <a name="additional-overloads"></a><span data-ttu-id="45f8e-138">Additional Overloads</span><span class="sxs-lookup"><span data-stu-id="45f8e-138">Additional Overloads</span></span>

<span data-ttu-id="45f8e-139">If you also wanted to accept a transaction amount in either `Decimal` or `Single`, you could further overload `post` to allow for this variation.</span><span class="sxs-lookup"><span data-stu-id="45f8e-139">If you also wanted to accept a transaction amount in either `Decimal` or `Single`, you could further overload `post` to allow for this variation.</span></span> <span data-ttu-id="45f8e-140">If you did this to each of the overloads in the preceding example, you would have four `Sub` procedures, all with the same name but with four different signatures.</span><span class="sxs-lookup"><span data-stu-id="45f8e-140">If you did this to each of the overloads in the preceding example, you would have four `Sub` procedures, all with the same name but with four different signatures.</span></span>

## <a name="advantages-of-overloading"></a><span data-ttu-id="45f8e-141">Advantages of Overloading</span><span class="sxs-lookup"><span data-stu-id="45f8e-141">Advantages of Overloading</span></span>

<span data-ttu-id="45f8e-142">The advantage of overloading a procedure is in the flexibility of the call.</span><span class="sxs-lookup"><span data-stu-id="45f8e-142">The advantage of overloading a procedure is in the flexibility of the call.</span></span> <span data-ttu-id="45f8e-143">To use the `post` procedure declared in the preceding example, the calling code can obtain the customer identification as either a `String` or an `Integer`, and then call the same procedure in either case.</span><span class="sxs-lookup"><span data-stu-id="45f8e-143">To use the `post` procedure declared in the preceding example, the calling code can obtain the customer identification as either a `String` or an `Integer`, and then call the same procedure in either case.</span></span> <span data-ttu-id="45f8e-144">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="45f8e-144">The following example illustrates this:</span></span>

[!code-vb[VbVbcnProcedures#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#56)]

[!code-vb[VbVbcnProcedures#57](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#57)]

## <a name="see-also"></a><span data-ttu-id="45f8e-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="45f8e-145">See also</span></span>

- [<span data-ttu-id="45f8e-146">手順</span><span class="sxs-lookup"><span data-stu-id="45f8e-146">Procedures</span></span>](./index.md)
- [<span data-ttu-id="45f8e-147">方法 : プロシージャの複数のバージョンを定義する</span><span class="sxs-lookup"><span data-stu-id="45f8e-147">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)
- [<span data-ttu-id="45f8e-148">方法 : オーバーロードされたプロシージャを呼び出す</span><span class="sxs-lookup"><span data-stu-id="45f8e-148">How to: Call an Overloaded Procedure</span></span>](./how-to-call-an-overloaded-procedure.md)
- [<span data-ttu-id="45f8e-149">方法 : 省略可能なパラメーターを受け取るプロシージャをオーバーロードする</span><span class="sxs-lookup"><span data-stu-id="45f8e-149">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [<span data-ttu-id="45f8e-150">方法 : 不特定数のパラメーターを受け取るプロシージャをオーバーロードする</span><span class="sxs-lookup"><span data-stu-id="45f8e-150">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [<span data-ttu-id="45f8e-151">プロシージャのオーバーロードに関する注意事項</span><span class="sxs-lookup"><span data-stu-id="45f8e-151">Considerations in Overloading Procedures</span></span>](./considerations-in-overloading-procedures.md)
- [<span data-ttu-id="45f8e-152">オーバーロードの解決</span><span class="sxs-lookup"><span data-stu-id="45f8e-152">Overload Resolution</span></span>](./overload-resolution.md)
- [<span data-ttu-id="45f8e-153">オーバーロード</span><span class="sxs-lookup"><span data-stu-id="45f8e-153">Overloads</span></span>](../../../../visual-basic/language-reference/modifiers/overloads.md)
- [<span data-ttu-id="45f8e-154">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="45f8e-154">Generic Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
