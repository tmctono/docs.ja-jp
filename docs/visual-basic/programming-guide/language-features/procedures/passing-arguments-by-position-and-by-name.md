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
ms.openlocfilehash: b872eda97d1e349ad781b12810e4b166d6e46fe1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61791886"
---
# <a name="passing-arguments-by-position-and-by-name-visual-basic"></a><span data-ttu-id="1951f-102">位置と名前による引数渡し (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1951f-102">Passing Arguments by Position and by Name (Visual Basic)</span></span>
<span data-ttu-id="1951f-103">呼び出すと、`Sub`または`Function`プロシージャの引数を渡すことができます*位置によって*: プロシージャの定義で出現する順序で-渡すことができますか*名前で*、なし配置を考慮します。</span><span class="sxs-lookup"><span data-stu-id="1951f-103">When you call a `Sub` or `Function` procedure, you can pass arguments *by position* — in the order in which they appear in the procedure's definition — or you can pass them *by name*, without regard to position.</span></span>  
  
 <span data-ttu-id="1951f-104">引数には、名の後にコロンと等号 (=) が宣言されているのかを指定する引数を名前で渡す場合 (`:=`)、その後に、引数の値。</span><span class="sxs-lookup"><span data-stu-id="1951f-104">When you pass an argument by name, you specify the argument's declared name followed by a colon and an equal sign (`:=`), followed by the argument value.</span></span> <span data-ttu-id="1951f-105">任意の順序で名前付き引数を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="1951f-105">You can supply named arguments in any order.</span></span>  
  
 <span data-ttu-id="1951f-106">たとえば、次`Sub`手順は次の 3 つの引数を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="1951f-106">For example, the following `Sub` procedure takes three arguments:</span></span>  
  
 [!code-vb[SampleProcedure](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#1)]  
  
 <span data-ttu-id="1951f-107">このプロシージャを呼び出すときに、位置、名前、またはその両方の組み合わせを使用して引数を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="1951f-107">When you call this procedure, you can supply the arguments by position, by name, or by using a mixture of both.</span></span>  
  
## <a name="passing-arguments-by-position"></a><span data-ttu-id="1951f-108">位置による引数渡し</span><span class="sxs-lookup"><span data-stu-id="1951f-108">Passing Arguments by Position</span></span>  
 <span data-ttu-id="1951f-109">呼び出すことができます、`Display`メソッドとその引数が位置によって渡され、次の例に示すように、コンマで区切られます。</span><span class="sxs-lookup"><span data-stu-id="1951f-109">You can call the `Display` method with its arguments passed by position and delimited by commas, as shown in the following example:</span></span>  
  
[!code-vb[ByPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#2)] 
  
 <span data-ttu-id="1951f-110">位置指定引数リストで省略可能な引数を省略した場合、コンマでは、その場所を保持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1951f-110">If you omit an optional argument in a positional argument list, you must hold its place with a comma.</span></span> <span data-ttu-id="1951f-111">次の例では、`Display`メソッドなし、`age`引数。</span><span class="sxs-lookup"><span data-stu-id="1951f-111">The following example calls the `Display` method without the `age` argument:</span></span>  
  
[!code-vb[ByPositionWithOptionalArgument](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#3)] 
  
## <a name="passing-arguments-by-name"></a><span data-ttu-id="1951f-112">名前による引数渡し</span><span class="sxs-lookup"><span data-stu-id="1951f-112">Passing Arguments by Name</span></span>  
 <span data-ttu-id="1951f-113">代わりに、呼び出すことができます`Display`名前によって渡される引数にもコンマで区切られた、次の例に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="1951f-113">Alternatively, you can call `Display` with the arguments passed by name, also delimited by commas, as shown in the following example:</span></span>  
  
[!code-vb[ByName](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#4)] 

 <span data-ttu-id="1951f-114">この方法で名前による引数渡しは、1 つ以上の省略可能な引数を持つプロシージャを呼び出す場合に特に便利です。</span><span class="sxs-lookup"><span data-stu-id="1951f-114">Passing arguments by name in this way is especially useful when you call a procedure that has more than one optional argument.</span></span> <span data-ttu-id="1951f-115">引数を名前で指定する場合は、引数の位置を示すために連続するコンマを使用する必要ありません。</span><span class="sxs-lookup"><span data-stu-id="1951f-115">If you supply arguments by name, you do not have to use consecutive commas to denote missing positional arguments.</span></span> <span data-ttu-id="1951f-116">名前による引数渡しやすく引数を渡し、省略しているものを追跡します。</span><span class="sxs-lookup"><span data-stu-id="1951f-116">Passing arguments by name also makes it easier to keep track of which arguments you are passing and which ones you are omitting.</span></span>  
  
## <a name="mixing-arguments-by-position-and-by-name"></a><span data-ttu-id="1951f-117">位置と名前による引数の混在</span><span class="sxs-lookup"><span data-stu-id="1951f-117">Mixing Arguments by Position and by Name</span></span>  

<span data-ttu-id="1951f-118">次の例に示すように、両方の位置と、1 つのプロシージャ呼び出しで名前による引数を指定できます。</span><span class="sxs-lookup"><span data-stu-id="1951f-118">You can supply arguments both by position and by name in a single procedure call, as shown in the following example:</span></span>  
  
[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#5)] 
  
 <span data-ttu-id="1951f-119">前の例では、余分なコンマは省略された場所を保持するために必要な`age`引数のため`birth`は名前によって渡されます。</span><span class="sxs-lookup"><span data-stu-id="1951f-119">In the preceding example, no extra comma is necessary to hold the place of the omitted `age` argument, since `birth` is passed by name.</span></span>  
  
<span data-ttu-id="1951f-120">15.5 前に、のバージョンの Visual Basic での位置と名前、位置指定引数の組み合わせで引数を指定するときにすべてあります最初。</span><span class="sxs-lookup"><span data-stu-id="1951f-120">In versions of Visual Basic before 15.5, when you supply arguments by a mixture of position and name, the positional arguments must all come first.</span></span> <span data-ttu-id="1951f-121">名前で引数を指定すると、残りの引数する必要がありますすべてが名前によって渡されます。</span><span class="sxs-lookup"><span data-stu-id="1951f-121">Once you supply an argument by name, any remaining arguments must all be passed by name.</span></span>  <span data-ttu-id="1951f-122">たとえば、次の呼び出し、`Display`メソッドには、コンパイラ エラーが表示されます[BC30241:。名前付き引数が想定](../../../misc/bc30241.md)します。</span><span class="sxs-lookup"><span data-stu-id="1951f-122">For example, the following call to the `Display` method displays compiler error [BC30241: Named argument expected](../../../misc/bc30241.md).</span></span>

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#6)] 

<span data-ttu-id="1951f-123">Visual Basic 15.5 以降では、位置指定引数は、名前付き引数終了位置指定引数が正しい位置にある場合。</span><span class="sxs-lookup"><span data-stu-id="1951f-123">Starting with Visual Basic 15.5, positional arguments can follow named arguments if the ending positional arguments are in the correct position.</span></span> <span data-ttu-id="1951f-124">Visual Basic 15.5 では、以前の呼び出しでコンパイルされた場合、`Display`メソッドが正常にコンパイルし、コンパイラ エラーを生成しなく[BC30241](../../../misc/bc30241.md)します。</span><span class="sxs-lookup"><span data-stu-id="1951f-124">If compiled under Visual Basic 15.5, the previous call to the `Display` method compiles successfully and no longer generates compiler error [BC30241](../../../misc/bc30241.md).</span></span>  

<span data-ttu-id="1951f-125">混在させるし、任意の順序で名前付きの位置指定引数と一致するこの機能は、コードを読みやすくする名前付き引数を使用する場合に特に便利です。</span><span class="sxs-lookup"><span data-stu-id="1951f-125">This ability to mix and match named and positional arguments in any order is particularly useful when you want to use a named argument to make your code more readable.</span></span> <span data-ttu-id="1951f-126">たとえば、次`Person`クラスのコンス トラクターには、型の 2 つの引数が必要です。 `Person`、どちらも指定できます`Nothing`します。</span><span class="sxs-lookup"><span data-stu-id="1951f-126">For example, the following `Person` class constructor requires two arguments of type `Person`, both of which can be `Nothing`.</span></span> 

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#7)] 

<span data-ttu-id="1951f-127">コードの意図をオフにときに混合の名前付きの位置指定引数を使用して、値の`father`と`mother`引数が`Nothing`:</span><span class="sxs-lookup"><span data-stu-id="1951f-127">Using mixed named and positional arguments helps to make the intent of the code clear when the value of the `father` and `mother` arguments is `Nothing`:</span></span>

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#8)] 

<span data-ttu-id="1951f-128">名前付き引数を位置指定引数を実行するには、Visual Basic プロジェクトに次の要素を追加する必要があります (\*.vbproj) ファイル。</span><span class="sxs-lookup"><span data-stu-id="1951f-128">To follow positional arguments with named arguments, you must add the following element to your Visual Basic project (\*.vbproj) file:</span></span>

```xml
<PropertyGroup>
  <LangVersion>15.5</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="1951f-129">詳細については、次を参照してください。 [Visual Basic の言語バージョンを設定](../../../language-reference/configure-language-version.md)します。</span><span class="sxs-lookup"><span data-stu-id="1951f-129">For more information see [setting the Visual Basic language version](../../../language-reference/configure-language-version.md).</span></span>

## <a name="restrictions-on-supplying-arguments-by-name"></a><span data-ttu-id="1951f-130">名前による引数渡しに関する制限事項</span><span class="sxs-lookup"><span data-stu-id="1951f-130">Restrictions on Supplying Arguments by Name</span></span>  

<span data-ttu-id="1951f-131">必須の引数を入力せずに名前では、引数を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="1951f-131">You cannot pass arguments by name to avoid entering required arguments.</span></span> <span data-ttu-id="1951f-132">省略可能な引数のみを省略することができます。</span><span class="sxs-lookup"><span data-stu-id="1951f-132">You can omit only the optional arguments.</span></span>  
  
<span data-ttu-id="1951f-133">名前では、パラメーター配列を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="1951f-133">You cannot pass a parameter array by name.</span></span> <span data-ttu-id="1951f-134">これは、プロシージャを呼び出すときに、不特定数のパラメーター配列のコンマ区切りの引数を指定して、コンパイラは 1 つ以上の引数を 1 つの名前に関連付けることはできません。</span><span class="sxs-lookup"><span data-stu-id="1951f-134">This is because when you call the procedure, you supply an indefinite number of comma-separated arguments for the parameter array, and the compiler cannot associate more than one argument with a single name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1951f-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="1951f-135">See also</span></span>

- [<span data-ttu-id="1951f-136">プロシージャ</span><span class="sxs-lookup"><span data-stu-id="1951f-136">Procedures</span></span>](./index.md)
- [<span data-ttu-id="1951f-137">プロシージャのパラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="1951f-137">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="1951f-138">方法: プロシージャに引数を渡す</span><span class="sxs-lookup"><span data-stu-id="1951f-138">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="1951f-139">引数の値渡しと参照渡し</span><span class="sxs-lookup"><span data-stu-id="1951f-139">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="1951f-140">省略可能なパラメーター</span><span class="sxs-lookup"><span data-stu-id="1951f-140">Optional Parameters</span></span>](./optional-parameters.md)
- [<span data-ttu-id="1951f-141">パラメーター配列</span><span class="sxs-lookup"><span data-stu-id="1951f-141">Parameter Arrays</span></span>](./parameter-arrays.md)
- [<span data-ttu-id="1951f-142">Optional</span><span class="sxs-lookup"><span data-stu-id="1951f-142">Optional</span></span>](../../../../visual-basic/language-reference/modifiers/optional.md)
- [<span data-ttu-id="1951f-143">ParamArray</span><span class="sxs-lookup"><span data-stu-id="1951f-143">ParamArray</span></span>](../../../../visual-basic/language-reference/modifiers/paramarray.md)
