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
ms.openlocfilehash: dd0a62b6567f3e74763b7f2e9b96803c193c7976
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403357"
---
# <a name="differences-between-parameters-and-arguments-visual-basic"></a><span data-ttu-id="e7004-102">パラメーターと引数の違い (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e7004-102">Differences Between Parameters and Arguments (Visual Basic)</span></span>
<span data-ttu-id="e7004-103">ほとんどの場合、プロシージャには呼び出された状況に関する情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="e7004-103">In most cases, a procedure must have some information about the circumstances in which it has been called.</span></span> <span data-ttu-id="e7004-104">反復的なタスクや共有タスクを実行するプロシージャでは、呼び出しごとに異なる情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="e7004-104">A procedure that performs repeated or shared tasks uses different information for each call.</span></span> <span data-ttu-id="e7004-105">この情報は、呼び出し時にプロシージャに渡す変数、定数、式で構成されます。</span><span class="sxs-lookup"><span data-stu-id="e7004-105">This information consists of variables, constants, and expressions that you pass to the procedure when you call it.</span></span>  
  
 <span data-ttu-id="e7004-106">この情報をプロシージャに伝えるために、プロシージャには "*パラメーター*" が定義されており、呼び出し元のコードからそのパラメーターに対して "*引数*" が渡されます。</span><span class="sxs-lookup"><span data-stu-id="e7004-106">To communicate this information to the procedure, the procedure defines a *parameter*, and the calling code passes an *argument* to that parameter.</span></span> <span data-ttu-id="e7004-107">パラメーターは駐車スペース、引数は自動車と考えることができます。</span><span class="sxs-lookup"><span data-stu-id="e7004-107">You can think of the parameter as a parking space and the argument as an automobile.</span></span> <span data-ttu-id="e7004-108">時間が異なれば、さまざまな自動車が 1 つの駐車スペースに駐車できるのと同じように、呼び出し元のコードからは、プロシージャを呼び出すたびに同じパラメーターに対して異なる引数を渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="e7004-108">Just as different automobiles can park in a parking space at different times, the calling code can pass a different argument to the same parameter every time that it calls the procedure.</span></span>  
  
## <a name="parameters"></a><span data-ttu-id="e7004-109">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e7004-109">Parameters</span></span>  
 <span data-ttu-id="e7004-110">"*パラメーター*" は、プロシージャを呼び出すときに渡す必要がある値を表します。</span><span class="sxs-lookup"><span data-stu-id="e7004-110">A *parameter* represents a value that the procedure expects you to pass when you call it.</span></span> <span data-ttu-id="e7004-111">プロシージャの宣言でパラメーターを定義します。</span><span class="sxs-lookup"><span data-stu-id="e7004-111">The procedure's declaration defines its parameters.</span></span>  
  
 <span data-ttu-id="e7004-112">`Function` または `Sub` プロシージャを定義するときは、プロシージャ名の直後にかっこで囲んだ "*パラメーター リスト*" を指定します。</span><span class="sxs-lookup"><span data-stu-id="e7004-112">When you define a `Function` or `Sub` procedure, you specify a *parameter list* in parentheses immediately following the procedure name.</span></span> <span data-ttu-id="e7004-113">パラメーターごとに、名前、データ型、および引渡し方法 ([ByVal](../../../language-reference/modifiers/byval.md) または [ByRef](../../../language-reference/modifiers/byref.md)) を指定します。</span><span class="sxs-lookup"><span data-stu-id="e7004-113">For each parameter, you specify a name, a data type, and a passing mechanism ([ByVal](../../../language-reference/modifiers/byval.md) or [ByRef](../../../language-reference/modifiers/byref.md)).</span></span> <span data-ttu-id="e7004-114">パラメーターが省略可能であることを示すこともできます。</span><span class="sxs-lookup"><span data-stu-id="e7004-114">You can also indicate that a parameter is optional.</span></span> <span data-ttu-id="e7004-115">これは、呼び出し元のコードから値を渡す必要がないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="e7004-115">This means that the calling code does not have to pass a value for it.</span></span>  
  
 <span data-ttu-id="e7004-116">各パラメーターの名前は、プロシージャ内で "*ローカル変数*" として機能します。</span><span class="sxs-lookup"><span data-stu-id="e7004-116">The name of each parameter serves as a *local variable* in the procedure.</span></span> <span data-ttu-id="e7004-117">パラメーター名は、他の変数を使用する場合と同じ方法で使用します。</span><span class="sxs-lookup"><span data-stu-id="e7004-117">You use the parameter name the same way you use any other variable.</span></span>  
  
## <a name="arguments"></a><span data-ttu-id="e7004-118">引数</span><span class="sxs-lookup"><span data-stu-id="e7004-118">Arguments</span></span>  
 <span data-ttu-id="e7004-119">"*引数*" は、プロシージャを呼び出すときにプロシージャ パラメーターに渡す値を表します。</span><span class="sxs-lookup"><span data-stu-id="e7004-119">An *argument* represents the value that you pass to a procedure parameter when you call the procedure.</span></span> <span data-ttu-id="e7004-120">呼び出し元のコードでは、プロシージャを呼び出すときに引数を指定します。</span><span class="sxs-lookup"><span data-stu-id="e7004-120">The calling code supplies the arguments when it calls the procedure.</span></span>  
  
 <span data-ttu-id="e7004-121">`Function` または `Sub` プロシージャを呼び出すときは、プロシージャ名の直後にかっこで囲んだ "*引数リスト*" を含めます。</span><span class="sxs-lookup"><span data-stu-id="e7004-121">When you call a `Function` or `Sub` procedure, you include an *argument list* in parentheses immediately following the procedure name.</span></span> <span data-ttu-id="e7004-122">各引数は、リスト内の同じ位置にあるパラメーターに対応しています。</span><span class="sxs-lookup"><span data-stu-id="e7004-122">Each argument corresponds to the parameter in the same position in the list.</span></span>  
  
 <span data-ttu-id="e7004-123">パラメーターの定義とは異なり、引数には名前がありません。</span><span class="sxs-lookup"><span data-stu-id="e7004-123">In contrast to parameter definition, arguments do not have names.</span></span> <span data-ttu-id="e7004-124">各引数は式であり、0 個以上の変数、定数、およびリテラルを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="e7004-124">Each argument is an expression, which can contain zero or more variables, constants, and literals.</span></span> <span data-ttu-id="e7004-125">評価される式のデータ型は、通常、対応するパラメーターに定義されているデータ型と一致する必要があり、いずれの場合でも、パラメーターの型に変換可能である必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7004-125">The data type of the evaluated expression should typically match the data type defined for the corresponding parameter, and in any case it must be convertible to the parameter type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7004-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="e7004-126">See also</span></span>

- [<span data-ttu-id="e7004-127">手順</span><span class="sxs-lookup"><span data-stu-id="e7004-127">Procedures</span></span>](./index.md)
- [<span data-ttu-id="e7004-128">Sub プロシージャ</span><span class="sxs-lookup"><span data-stu-id="e7004-128">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="e7004-129">Function プロシージャ</span><span class="sxs-lookup"><span data-stu-id="e7004-129">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="e7004-130">Property プロシージャ</span><span class="sxs-lookup"><span data-stu-id="e7004-130">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="e7004-131">演算子プロシージャ</span><span class="sxs-lookup"><span data-stu-id="e7004-131">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="e7004-132">方法: プロシージャのパラメーターを定義する</span><span class="sxs-lookup"><span data-stu-id="e7004-132">How to: Define a Parameter for a Procedure</span></span>](./how-to-define-a-parameter-for-a-procedure.md)
- [<span data-ttu-id="e7004-133">方法: プロシージャに引数を渡す</span><span class="sxs-lookup"><span data-stu-id="e7004-133">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="e7004-134">引数の値渡しと参照渡し</span><span class="sxs-lookup"><span data-stu-id="e7004-134">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="e7004-135">再帰プロシージャ</span><span class="sxs-lookup"><span data-stu-id="e7004-135">Recursive Procedures</span></span>](./recursive-procedures.md)
- [<span data-ttu-id="e7004-136">プロシージャのオーバーロード</span><span class="sxs-lookup"><span data-stu-id="e7004-136">Procedure Overloading</span></span>](./procedure-overloading.md)
