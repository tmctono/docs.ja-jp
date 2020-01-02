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
# <a name="procedure-overloading-visual-basic"></a><span data-ttu-id="fa2b6-102">プロシージャのオーバーロード (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fa2b6-102">Procedure Overloading (Visual Basic)</span></span>

<span data-ttu-id="fa2b6-103">プロシージャを*オーバーロード*することは、同じ名前でパラメーターリストが異なる複数のバージョンで定義することを意味します。</span><span class="sxs-lookup"><span data-stu-id="fa2b6-103">*Overloading* a procedure means defining it in multiple versions, using the same name but different parameter lists.</span></span> <span data-ttu-id="fa2b6-104">オーバーロードの目的は、プロシージャの名前を区別せずに、密接に関連する複数のバージョンを定義することです。</span><span class="sxs-lookup"><span data-stu-id="fa2b6-104">The purpose of overloading is to define several closely related versions of a procedure without having to differentiate them by name.</span></span> <span data-ttu-id="fa2b6-105">これを行うには、パラメーターリストを変更します。</span><span class="sxs-lookup"><span data-stu-id="fa2b6-105">You do this by varying the parameter list.</span></span>

## <a name="overloading-rules"></a><span data-ttu-id="fa2b6-106">オーバーロード (規則を)</span><span class="sxs-lookup"><span data-stu-id="fa2b6-106">Overloading Rules</span></span>

<span data-ttu-id="fa2b6-107">プロシージャをオーバーロードすると、次の規則が適用されます。</span><span class="sxs-lookup"><span data-stu-id="fa2b6-107">When you overload a procedure, the following rules apply:</span></span>

- <span data-ttu-id="fa2b6-108">**同じ名前**です。</span><span class="sxs-lookup"><span data-stu-id="fa2b6-108">**Same Name**.</span></span> <span data-ttu-id="fa2b6-109">オーバーロードされた各バージョンは、同じプロシージャ名を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa2b6-109">Each overloaded version must use the same procedure name.</span></span>

- <span data-ttu-id="fa2b6-110">**署名が異なり**ます。</span><span class="sxs-lookup"><span data-stu-id="fa2b6-110">**Different Signature**.</span></span> <span data-ttu-id="fa2b6-111">オーバーロードされた各バージョンは、次のいずれかの点で、他のすべてのオーバーロードされたバージョンと異なる必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa2b6-111">Each overloaded version must differ from all other overloaded versions in at least one of the following respects:</span></span>

  - <span data-ttu-id="fa2b6-112">パラメーターの数</span><span class="sxs-lookup"><span data-stu-id="fa2b6-112">Number of parameters</span></span>

  - <span data-ttu-id="fa2b6-113">パラメーターの順序</span><span class="sxs-lookup"><span data-stu-id="fa2b6-113">Order of the parameters</span></span>

  - <span data-ttu-id="fa2b6-114">パラメーターのデータ型</span><span class="sxs-lookup"><span data-stu-id="fa2b6-114">Data types of the parameters</span></span>

  - <span data-ttu-id="fa2b6-115">型パラメーターの数 (ジェネリックプロシージャの場合)</span><span class="sxs-lookup"><span data-stu-id="fa2b6-115">Number of type parameters (for a generic procedure)</span></span>

  - <span data-ttu-id="fa2b6-116">戻り値の型 (変換演算子の場合のみ)</span><span class="sxs-lookup"><span data-stu-id="fa2b6-116">Return type (only for a conversion operator)</span></span>

  <span data-ttu-id="fa2b6-117">プロシージャ名と共に、前の項目は総称してプロシージャの*シグネチャ*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="fa2b6-117">Together with the procedure name, the preceding items are collectively called the *signature* of the procedure.</span></span> <span data-ttu-id="fa2b6-118">オーバーロードされたプロシージャを呼び出すと、コンパイラはシグネチャを使用して、呼び出しが定義と正しく一致することを確認します。</span><span class="sxs-lookup"><span data-stu-id="fa2b6-118">When you call an overloaded procedure, the compiler uses the signature to check that the call correctly matches the definition.</span></span>

- <span data-ttu-id="fa2b6-119">**項目はシグネチャの一部ではありません**。</span><span class="sxs-lookup"><span data-stu-id="fa2b6-119">**Items Not Part of Signature**.</span></span> <span data-ttu-id="fa2b6-120">シグネチャを変更せずにプロシージャをオーバーロードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="fa2b6-120">You cannot overload a procedure without varying the signature.</span></span> <span data-ttu-id="fa2b6-121">特に、次の項目のうち1つ以上を変更してプロシージャをオーバーロードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="fa2b6-121">In particular, you cannot overload a procedure by varying only one or more of the following items:</span></span>

  - <span data-ttu-id="fa2b6-122">プロシージャ修飾子キーワード (`Public`、`Shared`、`Static` など)</span><span class="sxs-lookup"><span data-stu-id="fa2b6-122">Procedure modifier keywords, such as `Public`, `Shared`, and `Static`</span></span>

  - <span data-ttu-id="fa2b6-123">パラメーターまたは型パラメーター名</span><span class="sxs-lookup"><span data-stu-id="fa2b6-123">Parameter or type parameter names</span></span>

  - <span data-ttu-id="fa2b6-124">型パラメーターの制約 (ジェネリックプロシージャの場合)</span><span class="sxs-lookup"><span data-stu-id="fa2b6-124">Type parameter constraints (for a generic procedure)</span></span>

  - <span data-ttu-id="fa2b6-125">`ByRef` や `Optional` などのパラメーター修飾子キーワード</span><span class="sxs-lookup"><span data-stu-id="fa2b6-125">Parameter modifier keywords, such as `ByRef` and `Optional`</span></span>

  - <span data-ttu-id="fa2b6-126">値を返すかどうか</span><span class="sxs-lookup"><span data-stu-id="fa2b6-126">Whether it returns a value</span></span>

  - <span data-ttu-id="fa2b6-127">戻り値のデータ型 (変換演算子を除く)</span><span class="sxs-lookup"><span data-stu-id="fa2b6-127">The data type of the return value (except for a conversion operator)</span></span>

  <span data-ttu-id="fa2b6-128">前の一覧の項目は、署名に含まれていません。</span><span class="sxs-lookup"><span data-stu-id="fa2b6-128">The items in the preceding list are not part of the signature.</span></span> <span data-ttu-id="fa2b6-129">オーバーロードされたバージョンを区別するために使用することはできませんが、シグネチャによって適切に区別されるオーバーロードされたバージョン間で変更することはできます。</span><span class="sxs-lookup"><span data-stu-id="fa2b6-129">Although you cannot use them to differentiate between overloaded versions, you can vary them among overloaded versions that are properly differentiated by their signatures.</span></span>

- <span data-ttu-id="fa2b6-130">**遅延**バインディングされた引数。</span><span class="sxs-lookup"><span data-stu-id="fa2b6-130">**Late-Bound Arguments**.</span></span> <span data-ttu-id="fa2b6-131">遅延バインディングされたオブジェクト変数をオーバーロードされたバージョンに渡す場合は、適切なパラメーターを <xref:System.Object>として宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa2b6-131">If you intend to pass a late bound object variable to an overloaded version, you must declare the appropriate parameter as <xref:System.Object>.</span></span>

## <a name="multiple-versions-of-a-procedure"></a><span data-ttu-id="fa2b6-132">プロシージャの複数のバージョン</span><span class="sxs-lookup"><span data-stu-id="fa2b6-132">Multiple Versions of a Procedure</span></span>

<span data-ttu-id="fa2b6-133">顧客の残高に対してトランザクションを投稿するための `Sub` プロシージャを記述していて、名前またはアカウント番号で顧客を参照できるようにするとします。</span><span class="sxs-lookup"><span data-stu-id="fa2b6-133">Suppose you are writing a `Sub` procedure to post a transaction against a customer's balance, and you want to be able to refer to the customer either by name or by account number.</span></span> <span data-ttu-id="fa2b6-134">これに対応するために、次の例に示すように、2つの異なる `Sub` プロシージャを定義できます。</span><span class="sxs-lookup"><span data-stu-id="fa2b6-134">To accommodate this, you can define two different `Sub` procedures, as in the following example:</span></span>

[!code-vb[VbVbcnProcedures#73](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#73)]

### <a name="overloaded-versions"></a><span data-ttu-id="fa2b6-135">オーバーロードされたバージョン</span><span class="sxs-lookup"><span data-stu-id="fa2b6-135">Overloaded Versions</span></span>

<span data-ttu-id="fa2b6-136">別の方法として、1つのプロシージャ名をオーバーロードする方法があります。</span><span class="sxs-lookup"><span data-stu-id="fa2b6-136">An alternative is to overload a single procedure name.</span></span> <span data-ttu-id="fa2b6-137">次のように、 [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md)キーワードを使用して、各パラメーターリストのプロシージャのバージョンを定義できます。</span><span class="sxs-lookup"><span data-stu-id="fa2b6-137">You can use the [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) keyword to define a version of the procedure for each parameter list, as follows:</span></span>

[!code-vb[VbVbcnProcedures#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#72)]

#### <a name="additional-overloads"></a><span data-ttu-id="fa2b6-138">追加のオーバーロード</span><span class="sxs-lookup"><span data-stu-id="fa2b6-138">Additional Overloads</span></span>

<span data-ttu-id="fa2b6-139">また、`Decimal` または `Single`でトランザクション量を受け入れる場合は、`post` をオーバーロードして、このバリエーションに対応できるようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="fa2b6-139">If you also wanted to accept a transaction amount in either `Decimal` or `Single`, you could further overload `post` to allow for this variation.</span></span> <span data-ttu-id="fa2b6-140">前の例の各オーバーロードに対してこれを行った場合は、4つの `Sub` プロシージャがありますが、これらはすべて同じ名前ですが、4つの異なるシグネチャを持ちます。</span><span class="sxs-lookup"><span data-stu-id="fa2b6-140">If you did this to each of the overloads in the preceding example, you would have four `Sub` procedures, all with the same name but with four different signatures.</span></span>

## <a name="advantages-of-overloading"></a><span data-ttu-id="fa2b6-141">オーバーロードの利点</span><span class="sxs-lookup"><span data-stu-id="fa2b6-141">Advantages of Overloading</span></span>

<span data-ttu-id="fa2b6-142">プロシージャをオーバーロードする利点は、呼び出しの柔軟性です。</span><span class="sxs-lookup"><span data-stu-id="fa2b6-142">The advantage of overloading a procedure is in the flexibility of the call.</span></span> <span data-ttu-id="fa2b6-143">前の例で宣言した `post` プロシージャを使用するには、呼び出し元のコードが `String` または `Integer`として顧客 id を取得し、どちらの場合でも同じプロシージャを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="fa2b6-143">To use the `post` procedure declared in the preceding example, the calling code can obtain the customer identification as either a `String` or an `Integer`, and then call the same procedure in either case.</span></span> <span data-ttu-id="fa2b6-144">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="fa2b6-144">The following example illustrates this:</span></span>

[!code-vb[VbVbcnProcedures#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#56)]

[!code-vb[VbVbcnProcedures#57](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#57)]

## <a name="see-also"></a><span data-ttu-id="fa2b6-145">参照</span><span class="sxs-lookup"><span data-stu-id="fa2b6-145">See also</span></span>

- [<span data-ttu-id="fa2b6-146">Visual Basic におけるプロシージャ</span><span class="sxs-lookup"><span data-stu-id="fa2b6-146">Procedures</span></span>](./index.md)
- [<span data-ttu-id="fa2b6-147">方法 : プロシージャの複数のバージョンを定義する</span><span class="sxs-lookup"><span data-stu-id="fa2b6-147">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)
- [<span data-ttu-id="fa2b6-148">方法 : オーバーロードされたプロシージャを呼び出す</span><span class="sxs-lookup"><span data-stu-id="fa2b6-148">How to: Call an Overloaded Procedure</span></span>](./how-to-call-an-overloaded-procedure.md)
- [<span data-ttu-id="fa2b6-149">方法 : 省略可能なパラメーターを受け取るプロシージャをオーバーロードする</span><span class="sxs-lookup"><span data-stu-id="fa2b6-149">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [<span data-ttu-id="fa2b6-150">方法 : 不特定数のパラメーターを受け取るプロシージャをオーバーロードする</span><span class="sxs-lookup"><span data-stu-id="fa2b6-150">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [<span data-ttu-id="fa2b6-151">プロシージャのオーバーロードに関する注意事項</span><span class="sxs-lookup"><span data-stu-id="fa2b6-151">Considerations in Overloading Procedures</span></span>](./considerations-in-overloading-procedures.md)
- [<span data-ttu-id="fa2b6-152">オーバーロードの解決</span><span class="sxs-lookup"><span data-stu-id="fa2b6-152">Overload Resolution</span></span>](./overload-resolution.md)
- [<span data-ttu-id="fa2b6-153">Overloads</span><span class="sxs-lookup"><span data-stu-id="fa2b6-153">Overloads</span></span>](../../../../visual-basic/language-reference/modifiers/overloads.md)
- [<span data-ttu-id="fa2b6-154">Visual Basic におけるジェネリック型</span><span class="sxs-lookup"><span data-stu-id="fa2b6-154">Generic Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
