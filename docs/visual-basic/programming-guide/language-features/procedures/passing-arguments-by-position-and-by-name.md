---
title: 位置と名前による引数渡し (Visual Basic)
ms.date: 02/01/2018
helpviewer_keywords:
- arguments [Visual Basic], passing by name
- procedures [Visual Basic], arguments
- := passing arguments
- procedure arguments
- Visual Basic code, procedures
- named arguments [Visual Basic], passing arguments
- arguments [Visual Basic], passing by position
- Function procedures [Visual Basic], passing arguments
- named parameters [Visual Basic], passing arguments
- named arguments
- passing parameters [Visual Basic], named parameter arguments
- passing parameters [Visual Basic], by position
- procedures [Visual Basic], calling
- named parameters
- Sub procedures [Visual Basic], passing arguments
- argument passing
- passing parameters [Visual Basic], by name
- argument passing [Visual Basic], by position
- arguments [Visual Basic], listing by name
ms.assetid: 1ad7358f-1da9-48da-a95b-f3c7ed41eff3
ms.openlocfilehash: 2fa07a4ecf31b9dc0fee91593e793f3b00c5a83b
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524436"
---
# <a name="passing-arguments-by-position-and-by-name-visual-basic"></a><span data-ttu-id="c544b-102">位置と名前による引数渡し (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c544b-102">Passing Arguments by Position and by Name (Visual Basic)</span></span>

<span data-ttu-id="c544b-103">@No__t_0 または `Function` プロシージャを呼び出すと、プロシージャの定義に出現する順序で*位置によって*引数を渡すことができます。また、位置に関係なく*名前で*渡すこともできます。</span><span class="sxs-lookup"><span data-stu-id="c544b-103">When you call a `Sub` or `Function` procedure, you can pass arguments *by position* — in the order in which they appear in the procedure's definition — or you can pass them *by name*, without regard to position.</span></span>

<span data-ttu-id="c544b-104">引数を名前で渡す場合は、引数の宣言名の後にコロンと等号 (`:=`) を指定し、その後に引数の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="c544b-104">When you pass an argument by name, you specify the argument's declared name followed by a colon and an equal sign (`:=`), followed by the argument value.</span></span> <span data-ttu-id="c544b-105">名前付き引数は任意の順序で指定できます。</span><span class="sxs-lookup"><span data-stu-id="c544b-105">You can supply named arguments in any order.</span></span>

<span data-ttu-id="c544b-106">たとえば、次の `Sub` プロシージャでは、3つの引数が使用されます。</span><span class="sxs-lookup"><span data-stu-id="c544b-106">For example, the following `Sub` procedure takes three arguments:</span></span>

[!code-vb[SampleProcedure](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#1)]

<span data-ttu-id="c544b-107">このプロシージャを呼び出すと、位置、名前、または両方の組み合わせを使用して引数を指定できます。</span><span class="sxs-lookup"><span data-stu-id="c544b-107">When you call this procedure, you can supply the arguments by position, by name, or by using a mixture of both.</span></span>

## <a name="passing-arguments-by-position"></a><span data-ttu-id="c544b-108">渡す (位置によって引数を)</span><span class="sxs-lookup"><span data-stu-id="c544b-108">Passing Arguments by Position</span></span>

<span data-ttu-id="c544b-109">@No__t_0 メソッドは、次の例に示すように、位置によって渡され、コンマで区切られた引数を使用して呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="c544b-109">You can call the `Display` method with its arguments passed by position and delimited by commas, as shown in the following example:</span></span>

[!code-vb[ByPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#2)]

<span data-ttu-id="c544b-110">位置指定引数リストで省略可能な引数を省略した場合は、コンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="c544b-110">If you omit an optional argument in a positional argument list, you must hold its place with a comma.</span></span> <span data-ttu-id="c544b-111">次の例では、`age` 引数を指定せずに `Display` メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="c544b-111">The following example calls the `Display` method without the `age` argument:</span></span>

[!code-vb[ByPositionWithOptionalArgument](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#3)]

## <a name="passing-arguments-by-name"></a><span data-ttu-id="c544b-112">引数を名前で渡す</span><span class="sxs-lookup"><span data-stu-id="c544b-112">Passing Arguments by Name</span></span>

<span data-ttu-id="c544b-113">または、次の例に示すように、名前によって渡された引数を使用して `Display` を呼び出すこともできます。また、コンマで区切ることもできます。</span><span class="sxs-lookup"><span data-stu-id="c544b-113">Alternatively, you can call `Display` with the arguments passed by name, also delimited by commas, as shown in the following example:</span></span>

[!code-vb[ByName](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#4)]

<span data-ttu-id="c544b-114">この方法で名前によって引数を渡すことは、複数の省略可能な引数を持つプロシージャを呼び出す場合に特に便利です。</span><span class="sxs-lookup"><span data-stu-id="c544b-114">Passing arguments by name in this way is especially useful when you call a procedure that has more than one optional argument.</span></span> <span data-ttu-id="c544b-115">名前で引数を指定する場合は、位置指定引数がないことを示すために連続するコンマを使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c544b-115">If you supply arguments by name, you do not have to use consecutive commas to denote missing positional arguments.</span></span> <span data-ttu-id="c544b-116">名前によって引数を渡すことにより、渡す引数と省略する引数を追跡しやすくなります。</span><span class="sxs-lookup"><span data-stu-id="c544b-116">Passing arguments by name also makes it easier to keep track of which arguments you are passing and which ones you are omitting.</span></span>

## <a name="mixing-arguments-by-position-and-by-name"></a><span data-ttu-id="c544b-117">位置と名前による引数の混在</span><span class="sxs-lookup"><span data-stu-id="c544b-117">Mixing Arguments by Position and by Name</span></span>

<span data-ttu-id="c544b-118">次の例に示すように、1つのプロシージャ呼び出しで位置と名前の両方を引数として指定できます。</span><span class="sxs-lookup"><span data-stu-id="c544b-118">You can supply arguments both by position and by name in a single procedure call, as shown in the following example:</span></span>

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#5)]

<span data-ttu-id="c544b-119">前の例では、`birth` が名前で渡されるため、省略された `age` 引数の代わりにコンマを追加する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c544b-119">In the preceding example, no extra comma is necessary to hold the place of the omitted `age` argument, since `birth` is passed by name.</span></span>

<span data-ttu-id="c544b-120">15.5 より前のバージョンの Visual Basic では、位置と名前の組み合わせによって引数を指定する場合は、位置引数をすべて先に指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c544b-120">In versions of Visual Basic before 15.5, when you supply arguments by a mixture of position and name, the positional arguments must all come first.</span></span> <span data-ttu-id="c544b-121">名前で引数を指定すると、残りの引数はすべて名前で渡される必要があります。</span><span class="sxs-lookup"><span data-stu-id="c544b-121">Once you supply an argument by name, any remaining arguments must all be passed by name.</span></span>  <span data-ttu-id="c544b-122">たとえば、次の `Display` メソッドの呼び出しでは、コンパイラエラー [BC30241: 名前付き引数が必要](../../../misc/bc30241.md)です。</span><span class="sxs-lookup"><span data-stu-id="c544b-122">For example, the following call to the `Display` method displays compiler error [BC30241: Named argument expected](../../../misc/bc30241.md).</span></span>

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#6)]

<span data-ttu-id="c544b-123">Visual Basic 15.5 以降では、位置指定引数は、終了位置引数が正しい位置にある場合に名前付き引数に従うことができます。</span><span class="sxs-lookup"><span data-stu-id="c544b-123">Starting with Visual Basic 15.5, positional arguments can follow named arguments if the ending positional arguments are in the correct position.</span></span> <span data-ttu-id="c544b-124">Visual Basic 15.5 の下でコンパイルした場合、`Display` メソッドの前の呼び出しが正常にコンパイルされ、コンパイラエラー [BC30241](../../../misc/bc30241.md)が生成されなくなります。</span><span class="sxs-lookup"><span data-stu-id="c544b-124">If compiled under Visual Basic 15.5, the previous call to the `Display` method compiles successfully and no longer generates compiler error [BC30241](../../../misc/bc30241.md).</span></span>

<span data-ttu-id="c544b-125">この機能は、名前付き引数と位置指定引数を任意の順序で組み合わせることができ、コードを読みやすくするために名前付き引数を使用する場合に特に便利です。</span><span class="sxs-lookup"><span data-stu-id="c544b-125">This ability to mix and match named and positional arguments in any order is particularly useful when you want to use a named argument to make your code more readable.</span></span> <span data-ttu-id="c544b-126">たとえば、次の `Person` クラスコンストラクターには、`Person` 型の2つの引数が必要です。どちらも `Nothing` できます。</span><span class="sxs-lookup"><span data-stu-id="c544b-126">For example, the following `Person` class constructor requires two arguments of type `Person`, both of which can be `Nothing`.</span></span>

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#7)]

<span data-ttu-id="c544b-127">名前付き引数と位置指定引数を混在させることで、`father` 引数と `mother` 引数の値が `Nothing` 場合に、コードの意図を明確にすることができます。</span><span class="sxs-lookup"><span data-stu-id="c544b-127">Using mixed named and positional arguments helps to make the intent of the code clear when the value of the `father` and `mother` arguments is `Nothing`:</span></span>

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#8)]

<span data-ttu-id="c544b-128">名前付き引数を使用して位置指定引数を実行するには、次の要素を Visual Basic プロジェクト (\* .vbproj) ファイルに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c544b-128">To follow positional arguments with named arguments, you must add the following element to your Visual Basic project (\*.vbproj) file:</span></span>

```xml
<PropertyGroup>
  <LangVersion>15.5</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="c544b-129">詳細について[は、「Visual Basic 言語バージョンの設定](../../../language-reference/configure-language-version.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c544b-129">For more information see [setting the Visual Basic language version](../../../language-reference/configure-language-version.md).</span></span>

## <a name="restrictions-on-supplying-arguments-by-name"></a><span data-ttu-id="c544b-130">名前による引数の指定に関する制限事項</span><span class="sxs-lookup"><span data-stu-id="c544b-130">Restrictions on Supplying Arguments by Name</span></span>

<span data-ttu-id="c544b-131">必須の引数を入力しないように、名前で引数を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="c544b-131">You cannot pass arguments by name to avoid entering required arguments.</span></span> <span data-ttu-id="c544b-132">省略可能な引数のみを省略できます。</span><span class="sxs-lookup"><span data-stu-id="c544b-132">You can omit only the optional arguments.</span></span>

<span data-ttu-id="c544b-133">パラメーター配列を名前で渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="c544b-133">You cannot pass a parameter array by name.</span></span> <span data-ttu-id="c544b-134">これは、プロシージャを呼び出すときに、パラメーター配列に対してコンマで区切られた少数の引数を指定し、コンパイラが1つの名前に複数の引数を関連付けることができないためです。</span><span class="sxs-lookup"><span data-stu-id="c544b-134">This is because when you call the procedure, you supply an indefinite number of comma-separated arguments for the parameter array, and the compiler cannot associate more than one argument with a single name.</span></span>

## <a name="see-also"></a><span data-ttu-id="c544b-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="c544b-135">See also</span></span>

- [<span data-ttu-id="c544b-136">手順</span><span class="sxs-lookup"><span data-stu-id="c544b-136">Procedures</span></span>](./index.md)
- [<span data-ttu-id="c544b-137">プロシージャのパラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="c544b-137">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="c544b-138">方法: プロシージャに引数を渡す</span><span class="sxs-lookup"><span data-stu-id="c544b-138">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="c544b-139">引数の値渡しと参照渡し</span><span class="sxs-lookup"><span data-stu-id="c544b-139">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="c544b-140">省略可能なパラメーター</span><span class="sxs-lookup"><span data-stu-id="c544b-140">Optional Parameters</span></span>](./optional-parameters.md)
- [<span data-ttu-id="c544b-141">パラメーター配列</span><span class="sxs-lookup"><span data-stu-id="c544b-141">Parameter Arrays</span></span>](./parameter-arrays.md)
- [<span data-ttu-id="c544b-142">Optional</span><span class="sxs-lookup"><span data-stu-id="c544b-142">Optional</span></span>](../../../../visual-basic/language-reference/modifiers/optional.md)
- [<span data-ttu-id="c544b-143">ParamArray</span><span class="sxs-lookup"><span data-stu-id="c544b-143">ParamArray</span></span>](../../../../visual-basic/language-reference/modifiers/paramarray.md)
