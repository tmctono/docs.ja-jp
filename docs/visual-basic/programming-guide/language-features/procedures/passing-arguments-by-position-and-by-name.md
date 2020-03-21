---
title: 位置と名前による引数渡し
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
ms.openlocfilehash: b6588335f7634cc87a9fc14cbfc4ba80baad1abb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401437"
---
# <a name="passing-arguments-by-position-and-by-name-visual-basic"></a><span data-ttu-id="056c9-102">位置と名前による引数渡し (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="056c9-102">Passing Arguments by Position and by Name (Visual Basic)</span></span>

<span data-ttu-id="056c9-103">または`Sub``Function`プロシージャを呼び出すときは、プロシージャの定義に表示される順序で引数を*位置*によって渡したり、位置に関係なく*名前で*渡したりできます。</span><span class="sxs-lookup"><span data-stu-id="056c9-103">When you call a `Sub` or `Function` procedure, you can pass arguments *by position* — in the order in which they appear in the procedure's definition — or you can pass them *by name*, without regard to position.</span></span>

<span data-ttu-id="056c9-104">引数を名前で渡す場合は、引数の宣言名の後にコロンと等号 ( )`:=`を指定し、その後に引数値を指定します。</span><span class="sxs-lookup"><span data-stu-id="056c9-104">When you pass an argument by name, you specify the argument's declared name followed by a colon and an equal sign (`:=`), followed by the argument value.</span></span> <span data-ttu-id="056c9-105">名前付き引数は任意の順序で指定できます。</span><span class="sxs-lookup"><span data-stu-id="056c9-105">You can supply named arguments in any order.</span></span>

<span data-ttu-id="056c9-106">たとえば、次`Sub`のプロシージャは 3 つの引数をとります。</span><span class="sxs-lookup"><span data-stu-id="056c9-106">For example, the following `Sub` procedure takes three arguments:</span></span>

[!code-vb[SampleProcedure](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#1)]

<span data-ttu-id="056c9-107">このプロシージャを呼び出すときは、位置、名前、または両方を組み合わせて使用して引数を指定できます。</span><span class="sxs-lookup"><span data-stu-id="056c9-107">When you call this procedure, you can supply the arguments by position, by name, or by using a mixture of both.</span></span>

## <a name="passing-arguments-by-position"></a><span data-ttu-id="056c9-108">位置による引数の引き渡し</span><span class="sxs-lookup"><span data-stu-id="056c9-108">Passing Arguments by Position</span></span>

<span data-ttu-id="056c9-109">次の例に`Display`示すように、引数を位置によって渡し、コンマで区切ってメソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="056c9-109">You can call the `Display` method with its arguments passed by position and delimited by commas, as shown in the following example:</span></span>

[!code-vb[ByPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#2)]

<span data-ttu-id="056c9-110">位置指定引数リストで省略可能な引数を省略する場合は、その位置をコンマで保持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="056c9-110">If you omit an optional argument in a positional argument list, you must hold its place with a comma.</span></span> <span data-ttu-id="056c9-111">次の例では、`Display`引数なしでメソッド`age`を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="056c9-111">The following example calls the `Display` method without the `age` argument:</span></span>

[!code-vb[ByPositionWithOptionalArgument](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#3)]

## <a name="passing-arguments-by-name"></a><span data-ttu-id="056c9-112">名前による引数の引き渡し</span><span class="sxs-lookup"><span data-stu-id="056c9-112">Passing Arguments by Name</span></span>

<span data-ttu-id="056c9-113">または、次の例に`Display`示すように、名前で渡される引数をコンマで区切って呼び出すこともできます。</span><span class="sxs-lookup"><span data-stu-id="056c9-113">Alternatively, you can call `Display` with the arguments passed by name, also delimited by commas, as shown in the following example:</span></span>

[!code-vb[ByName](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#4)]

<span data-ttu-id="056c9-114">この方法で引数を名前で渡すと、複数の省略可能な引数を持つプロシージャを呼び出す場合に特に便利です。</span><span class="sxs-lookup"><span data-stu-id="056c9-114">Passing arguments by name in this way is especially useful when you call a procedure that has more than one optional argument.</span></span> <span data-ttu-id="056c9-115">引数を名前で指定する場合は、連続したコンマを使用して、位置引数が欠落していないことを示す必要はありません。</span><span class="sxs-lookup"><span data-stu-id="056c9-115">If you supply arguments by name, you do not have to use consecutive commas to denote missing positional arguments.</span></span> <span data-ttu-id="056c9-116">引数を名前で渡すと、渡す引数と省略する引数を簡単に追跡できます。</span><span class="sxs-lookup"><span data-stu-id="056c9-116">Passing arguments by name also makes it easier to keep track of which arguments you are passing and which ones you are omitting.</span></span>

## <a name="mixing-arguments-by-position-and-by-name"></a><span data-ttu-id="056c9-117">位置と名前による引数の混在</span><span class="sxs-lookup"><span data-stu-id="056c9-117">Mixing Arguments by Position and by Name</span></span>

<span data-ttu-id="056c9-118">次の例に示すように、1 回のプロシージャ呼び出しで、位置と名前の両方で引数を指定できます。</span><span class="sxs-lookup"><span data-stu-id="056c9-118">You can supply arguments both by position and by name in a single procedure call, as shown in the following example:</span></span>

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#5)]

<span data-ttu-id="056c9-119">前の例では、省略された`age`引数の場所を保持するために余分なコンマ`birth`は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="056c9-119">In the preceding example, no extra comma is necessary to hold the place of the omitted `age` argument, since `birth` is passed by name.</span></span>

<span data-ttu-id="056c9-120">15.5 より前のバージョンの Visual Basic では、位置と名前を組み合わせて引数を指定する場合は、すべて最初に位置引数を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="056c9-120">In versions of Visual Basic before 15.5, when you supply arguments by a mixture of position and name, the positional arguments must all come first.</span></span> <span data-ttu-id="056c9-121">引数を名前で指定したら、残りの引数はすべて名前で渡す必要があります。</span><span class="sxs-lookup"><span data-stu-id="056c9-121">Once you supply an argument by name, any remaining arguments must all be passed by name.</span></span>  <span data-ttu-id="056c9-122">たとえば、次のメソッドの呼び`Display`出しは、コンパイラ エラー [BC30241: 名前付き引数が必要です](../../../misc/bc30241.md)。</span><span class="sxs-lookup"><span data-stu-id="056c9-122">For example, the following call to the `Display` method displays compiler error [BC30241: Named argument expected](../../../misc/bc30241.md).</span></span>

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#6)]

<span data-ttu-id="056c9-123">Visual Basic 15.5 以降では、位置引数の末尾が正しい位置にある場合は、位置指定引数を名前付き引数に続けることができます。</span><span class="sxs-lookup"><span data-stu-id="056c9-123">Starting with Visual Basic 15.5, positional arguments can follow named arguments if the ending positional arguments are in the correct position.</span></span> <span data-ttu-id="056c9-124">Visual Basic 15.5 でコンパイルすると、メソッドの前`Display`の呼び出しは正常にコンパイルされ、コンパイラ エラー [BC30241](../../../misc/bc30241.md)が生成されなくなります。</span><span class="sxs-lookup"><span data-stu-id="056c9-124">If compiled under Visual Basic 15.5, the previous call to the `Display` method compiles successfully and no longer generates compiler error [BC30241](../../../misc/bc30241.md).</span></span>

<span data-ttu-id="056c9-125">名前付き引数と位置指定引数を任意の順序で組み合わせてマッチングする機能は、コードを読みやすくするために名前付き引数を使用する場合に特に便利です。</span><span class="sxs-lookup"><span data-stu-id="056c9-125">This ability to mix and match named and positional arguments in any order is particularly useful when you want to use a named argument to make your code more readable.</span></span> <span data-ttu-id="056c9-126">たとえば、次`Person`のクラス コンストラクターには、 の両方`Person`を使用できる 2`Nothing`つの型の引数が必要です。</span><span class="sxs-lookup"><span data-stu-id="056c9-126">For example, the following `Person` class constructor requires two arguments of type `Person`, both of which can be `Nothing`.</span></span>

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#7)]

<span data-ttu-id="056c9-127">名前付き引数と位置引数を混在させると、`father`と`mother`引数の値が : `Nothing`</span><span class="sxs-lookup"><span data-stu-id="056c9-127">Using mixed named and positional arguments helps to make the intent of the code clear when the value of the `father` and `mother` arguments is `Nothing`:</span></span>

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#8)]

<span data-ttu-id="056c9-128">名前付き引数を使用して位置指定引数に従うには、Visual Basic プロジェクト (.vbproj)\*ファイルに次の要素を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="056c9-128">To follow positional arguments with named arguments, you must add the following element to your Visual Basic project (\*.vbproj) file:</span></span>

```xml
<PropertyGroup>
  <LangVersion>15.5</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="056c9-129">詳細については、「 [Visual Basic 言語バージョンの設定](../../../language-reference/configure-language-version.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="056c9-129">For more information see [setting the Visual Basic language version](../../../language-reference/configure-language-version.md).</span></span>

## <a name="restrictions-on-supplying-arguments-by-name"></a><span data-ttu-id="056c9-130">名前による引数の指定に関する制限</span><span class="sxs-lookup"><span data-stu-id="056c9-130">Restrictions on Supplying Arguments by Name</span></span>

<span data-ttu-id="056c9-131">引数を名前で渡して、必須の引数を入力しないようにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="056c9-131">You cannot pass arguments by name to avoid entering required arguments.</span></span> <span data-ttu-id="056c9-132">省略可能な引数のみを省略できます。</span><span class="sxs-lookup"><span data-stu-id="056c9-132">You can omit only the optional arguments.</span></span>

<span data-ttu-id="056c9-133">パラメータ配列を名前で渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="056c9-133">You cannot pass a parameter array by name.</span></span> <span data-ttu-id="056c9-134">これは、プロシージャを呼び出すときに、パラメーター配列に対してコンマ区切りの引数を不特定多数指定し、コンパイラが 1 つの名前に複数の引数を関連付けることができないためです。</span><span class="sxs-lookup"><span data-stu-id="056c9-134">This is because when you call the procedure, you supply an indefinite number of comma-separated arguments for the parameter array, and the compiler cannot associate more than one argument with a single name.</span></span>

## <a name="see-also"></a><span data-ttu-id="056c9-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="056c9-135">See also</span></span>

- [<span data-ttu-id="056c9-136">手順</span><span class="sxs-lookup"><span data-stu-id="056c9-136">Procedures</span></span>](./index.md)
- [<span data-ttu-id="056c9-137">プロシージャのパラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="056c9-137">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="056c9-138">方法: プロシージャに引数を渡す</span><span class="sxs-lookup"><span data-stu-id="056c9-138">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="056c9-139">引数の値渡しと参照渡し</span><span class="sxs-lookup"><span data-stu-id="056c9-139">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="056c9-140">オプションのパラメータ</span><span class="sxs-lookup"><span data-stu-id="056c9-140">Optional Parameters</span></span>](./optional-parameters.md)
- [<span data-ttu-id="056c9-141">パラメータ配列</span><span class="sxs-lookup"><span data-stu-id="056c9-141">Parameter Arrays</span></span>](./parameter-arrays.md)
- [<span data-ttu-id="056c9-142">オプション</span><span class="sxs-lookup"><span data-stu-id="056c9-142">Optional</span></span>](../../../../visual-basic/language-reference/modifiers/optional.md)
- [<span data-ttu-id="056c9-143">ParamArray</span><span class="sxs-lookup"><span data-stu-id="056c9-143">ParamArray</span></span>](../../../../visual-basic/language-reference/modifiers/paramarray.md)
