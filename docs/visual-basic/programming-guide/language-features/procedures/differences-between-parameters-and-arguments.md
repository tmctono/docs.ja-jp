---
title: パラメーターと引数の違い
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedures [Visual Basic], parameters
- parameters [Visual Basic], and arguments
- procedure arguments
- Visual Basic code, procedures
- arguments [Visual Basic], and parameters
- procedure parameters
- parameters [Visual Basic], definition
ms.assetid: c237c056-74f4-4749-9f2c-15864f139a31
ms.openlocfilehash: c4249dbf86bd1bfa7ef08e94059d2880333e9a92
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74341375"
---
# <a name="differences-between-parameters-and-arguments-visual-basic"></a><span data-ttu-id="44b29-102">パラメーターと引数の違い (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="44b29-102">Differences Between Parameters and Arguments (Visual Basic)</span></span>
<span data-ttu-id="44b29-103">ほとんどの場合、プロシージャには、呼び出された状況に関する情報が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="44b29-103">In most cases, a procedure must have some information about the circumstances in which it has been called.</span></span> <span data-ttu-id="44b29-104">繰り返しまたは共有タスクを実行するプロシージャは、呼び出しごとに異なる情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="44b29-104">A procedure that performs repeated or shared tasks uses different information for each call.</span></span> <span data-ttu-id="44b29-105">この情報は、呼び出し時にプロシージャに渡す変数、定数、および式で構成されます。</span><span class="sxs-lookup"><span data-stu-id="44b29-105">This information consists of variables, constants, and expressions that you pass to the procedure when you call it.</span></span>  
  
 <span data-ttu-id="44b29-106">プロシージャにこの情報を伝えるために、プロシージャは*パラメーター*を定義し、呼び出し元のコードはそのパラメーターに*引数*を渡します。</span><span class="sxs-lookup"><span data-stu-id="44b29-106">To communicate this information to the procedure, the procedure defines a *parameter*, and the calling code passes an *argument* to that parameter.</span></span> <span data-ttu-id="44b29-107">パラメーターは、駐車スペースおよび自動車としての引数と考えることができます。</span><span class="sxs-lookup"><span data-stu-id="44b29-107">You can think of the parameter as a parking space and the argument as an automobile.</span></span> <span data-ttu-id="44b29-108">さまざまな自動車が駐車スペースで異なるタイミングでパークできるのと同様に、呼び出し元のコードは、プロシージャを呼び出すたびに、同じパラメーターに別の引数を渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="44b29-108">Just as different automobiles can park in a parking space at different times, the calling code can pass a different argument to the same parameter every time that it calls the procedure.</span></span>  
  
## <a name="parameters"></a><span data-ttu-id="44b29-109">パラメーター</span><span class="sxs-lookup"><span data-stu-id="44b29-109">Parameters</span></span>  
 <span data-ttu-id="44b29-110">*パラメーター*は、プロシージャが呼び出し時に渡すことを予期している値を表します。</span><span class="sxs-lookup"><span data-stu-id="44b29-110">A *parameter* represents a value that the procedure expects you to pass when you call it.</span></span> <span data-ttu-id="44b29-111">プロシージャの宣言では、パラメーターを定義します。</span><span class="sxs-lookup"><span data-stu-id="44b29-111">The procedure's declaration defines its parameters.</span></span>  
  
 <span data-ttu-id="44b29-112">`Function` または `Sub` プロシージャを定義する場合は、プロシージャ名の直後にかっこで囲まれた*パラメーターリスト*を指定します。</span><span class="sxs-lookup"><span data-stu-id="44b29-112">When you define a `Function` or `Sub` procedure, you specify a *parameter list* in parentheses immediately following the procedure name.</span></span> <span data-ttu-id="44b29-113">各パラメーターには、名前、データ型、および渡す機構 ([ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)または[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)) を指定します。</span><span class="sxs-lookup"><span data-stu-id="44b29-113">For each parameter, you specify a name, a data type, and a passing mechanism ([ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)).</span></span> <span data-ttu-id="44b29-114">また、パラメーターが省略可能であることを示すこともできます。</span><span class="sxs-lookup"><span data-stu-id="44b29-114">You can also indicate that a parameter is optional.</span></span> <span data-ttu-id="44b29-115">これは、呼び出し元のコードが値を渡す必要がないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="44b29-115">This means that the calling code does not have to pass a value for it.</span></span>  
  
 <span data-ttu-id="44b29-116">各パラメーターの名前は、プロシージャの*ローカル変数*として機能します。</span><span class="sxs-lookup"><span data-stu-id="44b29-116">The name of each parameter serves as a *local variable* in the procedure.</span></span> <span data-ttu-id="44b29-117">パラメーター名は、他の変数を使用する場合と同じ方法で使用します。</span><span class="sxs-lookup"><span data-stu-id="44b29-117">You use the parameter name the same way you use any other variable.</span></span>  
  
## <a name="arguments"></a><span data-ttu-id="44b29-118">引数</span><span class="sxs-lookup"><span data-stu-id="44b29-118">Arguments</span></span>  
 <span data-ttu-id="44b29-119">*引数*は、プロシージャを呼び出すときにプロシージャパラメーターに渡す値を表します。</span><span class="sxs-lookup"><span data-stu-id="44b29-119">An *argument* represents the value that you pass to a procedure parameter when you call the procedure.</span></span> <span data-ttu-id="44b29-120">呼び出し元のコードは、プロシージャを呼び出すときに引数を指定します。</span><span class="sxs-lookup"><span data-stu-id="44b29-120">The calling code supplies the arguments when it calls the procedure.</span></span>  
  
 <span data-ttu-id="44b29-121">`Function` または `Sub` プロシージャを呼び出すときには、プロシージャ名の直後に*引数リスト*をかっこで囲んで指定します。</span><span class="sxs-lookup"><span data-stu-id="44b29-121">When you call a `Function` or `Sub` procedure, you include an *argument list* in parentheses immediately following the procedure name.</span></span> <span data-ttu-id="44b29-122">各引数は、リスト内の同じ位置にあるパラメーターに対応します。</span><span class="sxs-lookup"><span data-stu-id="44b29-122">Each argument corresponds to the parameter in the same position in the list.</span></span>  
  
 <span data-ttu-id="44b29-123">パラメーターの定義とは異なり、引数には名前がありません。</span><span class="sxs-lookup"><span data-stu-id="44b29-123">In contrast to parameter definition, arguments do not have names.</span></span> <span data-ttu-id="44b29-124">各引数は式であり、0個以上の変数、定数、およびリテラルを含むことができます。</span><span class="sxs-lookup"><span data-stu-id="44b29-124">Each argument is an expression, which can contain zero or more variables, constants, and literals.</span></span> <span data-ttu-id="44b29-125">評価された式のデータ型は、通常、対応するパラメーターに対して定義されているデータ型と一致し、任意の場合はパラメーターの型に変換可能である必要があります。</span><span class="sxs-lookup"><span data-stu-id="44b29-125">The data type of the evaluated expression should typically match the data type defined for the corresponding parameter, and in any case it must be convertible to the parameter type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44b29-126">参照</span><span class="sxs-lookup"><span data-stu-id="44b29-126">See also</span></span>

- [<span data-ttu-id="44b29-127">Visual Basic におけるプロシージャ</span><span class="sxs-lookup"><span data-stu-id="44b29-127">Procedures</span></span>](./index.md)
- [<span data-ttu-id="44b29-128">Sub プロシージャ</span><span class="sxs-lookup"><span data-stu-id="44b29-128">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="44b29-129">Function プロシージャ</span><span class="sxs-lookup"><span data-stu-id="44b29-129">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="44b29-130">Property プロシージャ</span><span class="sxs-lookup"><span data-stu-id="44b29-130">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="44b29-131">演算子プロシージャ</span><span class="sxs-lookup"><span data-stu-id="44b29-131">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="44b29-132">方法 : プロシージャにパラメーターを定義する</span><span class="sxs-lookup"><span data-stu-id="44b29-132">How to: Define a Parameter for a Procedure</span></span>](./how-to-define-a-parameter-for-a-procedure.md)
- [<span data-ttu-id="44b29-133">方法: プロシージャに引数を渡す</span><span class="sxs-lookup"><span data-stu-id="44b29-133">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="44b29-134">引数の値渡しと参照渡し</span><span class="sxs-lookup"><span data-stu-id="44b29-134">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="44b29-135">再帰プロシージャ</span><span class="sxs-lookup"><span data-stu-id="44b29-135">Recursive Procedures</span></span>](./recursive-procedures.md)
- [<span data-ttu-id="44b29-136">プロシージャのオーバーロード</span><span class="sxs-lookup"><span data-stu-id="44b29-136">Procedure Overloading</span></span>](./procedure-overloading.md)
