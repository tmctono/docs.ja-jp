---
title: 定数の概要
ms.date: 07/20/2015
helpviewer_keywords:
- constants [Visual Basic]
ms.assetid: 29016fe8-78b3-4dc8-90b8-1cfec2fa8ac9
ms.openlocfilehash: 7f2a2dc140352588246d80a7feb46ce1f609b358
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "91086284"
---
# <a name="constants-overview-visual-basic"></a><span data-ttu-id="b3cf2-102">定数の概要 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b3cf2-102">Constants Overview (Visual Basic)</span></span>

<span data-ttu-id="b3cf2-103">定数とは、不変の数値または文字列の代わりとなるわかりやすい名前です。</span><span class="sxs-lookup"><span data-stu-id="b3cf2-103">A constant is a meaningful name that takes the place of a number or string that does not change.</span></span> <span data-ttu-id="b3cf2-104">定数に格納された値は、その名が示すとおり、アプリケーションの実行中に変わることはありません。</span><span class="sxs-lookup"><span data-stu-id="b3cf2-104">Constants store values that, as the name implies, remain the same throughout the execution of an application.</span></span> <span data-ttu-id="b3cf2-105">定数を使用することで、コードの可読性を大きく高め、管理を容易にすることができます。</span><span class="sxs-lookup"><span data-stu-id="b3cf2-105">You can greatly improve the readability of your code and make it easier to maintain by using constants.</span></span> <span data-ttu-id="b3cf2-106">これらは、繰り返し現れる値を含むコードや、覚えにくい数値または意味のわかりにくい数値に依存するコードで使用します。</span><span class="sxs-lookup"><span data-stu-id="b3cf2-106">Use them in code that contains values that reappear or that depends on certain numbers that are difficult to remember or have no obvious meaning.</span></span>  
  
## <a name="how-to-create-and-use-constants"></a><span data-ttu-id="b3cf2-107">定数の作成方法と使用方法</span><span class="sxs-lookup"><span data-stu-id="b3cf2-107">How to Create and Use Constants</span></span>  

 <span data-ttu-id="b3cf2-108">Visual には定義済みの定数が多数含まれており、その大部分は印刷や表示に使用されています。</span><span class="sxs-lookup"><span data-stu-id="b3cf2-108">Visual Basic contains a number of predefined constants, mainly using for printing and displaying.</span></span> <span data-ttu-id="b3cf2-109">変数名を作成するときと同じガイドラインに従い、`Const` ステートメントによって独自の定数を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="b3cf2-109">You can also create your own constants with the `Const` statement, using the same guidelines you would for creating a variable name.</span></span> <span data-ttu-id="b3cf2-110">`Option Strict` に `On` を指定した場合、定数の型を明示的に宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b3cf2-110">If `Option Strict` is `On`, you must explicitly declare the constant type.</span></span>  
  
 <span data-ttu-id="b3cf2-111">定数のスコープは、定数の名前を修飾しなくても参照可能なすべてのコードであり、同一の場所で宣言された変数のものと同じになります。</span><span class="sxs-lookup"><span data-stu-id="b3cf2-111">A constant's scope, which is the set of all code that can refer to it without qualifying its name, is the same as that of a variable declared in the same location.</span></span> <span data-ttu-id="b3cf2-112">特定のプロシージャのスコープ内に存在する定数を作成するには、該当するプロシージャ内で宣言します。</span><span class="sxs-lookup"><span data-stu-id="b3cf2-112">To create a constant that exists within the scope of a particular procedure, declare it inside that procedure.</span></span> <span data-ttu-id="b3cf2-113">アプリケーション全体で利用可能な定数を作成するには、クラスの宣言セクションで `Public` キーワードを使用して宣言します。</span><span class="sxs-lookup"><span data-stu-id="b3cf2-113">To create a constant that is available throughout an application, declare it using the `Public` keyword in the declarations section of the class.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b3cf2-114">定数は変数にやや似ていますが、定数を変更したり、変数のように新しい値を割り当てたりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="b3cf2-114">Although constants somewhat resemble variables, you cannot modify them or assign new values to them as you can to variables.</span></span>  
  
 <span data-ttu-id="b3cf2-115">コードで使用する定数は、利用するコントロールまたはコンポーネントのオブジェクト モデルにより定義できます。また、ユーザー定義定数 (つまり、独自に作成した定数) を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="b3cf2-115">The constants you use in your code can be defined by the object model for controls or components you work with, or they can be user-defined (that is, those you create yourself).</span></span>  
  
## <a name="compile-time-and-run-time-constants"></a><span data-ttu-id="b3cf2-116">コンパイル時定数と実行時定数</span><span class="sxs-lookup"><span data-stu-id="b3cf2-116">Compile-time and Run-time Constants</span></span>  

 <span data-ttu-id="b3cf2-117">コンパイル時定数はコードのコンパイル時に計算されますが、実行時定数はアプリケーションの実行中にしか計算できません。</span><span class="sxs-lookup"><span data-stu-id="b3cf2-117">A compile-time constant is computed at the time the code is compiled, while a run-time constant can only be computed while the application is running.</span></span> <span data-ttu-id="b3cf2-118">コンパイル時定数には、アプリケーションを実行するたびに同じ値が割り当てられますが、実行時定数は実行のたびに変わる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b3cf2-118">A compile-time constant will have the same value each time an application runs, while a run-time constant may change each time.</span></span> <span data-ttu-id="b3cf2-119">配列の範囲、Case 式、列挙子の初期化子などにはコンパイル時定数を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b3cf2-119">Compile-time constants are required for cases such as array bounds, case expressions, or enumerator initializers.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b3cf2-120">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="b3cf2-120">In This Section</span></span>  
  
|<span data-ttu-id="b3cf2-121">定義</span><span class="sxs-lookup"><span data-stu-id="b3cf2-121">Definition</span></span>|<span data-ttu-id="b3cf2-122">用語</span><span class="sxs-lookup"><span data-stu-id="b3cf2-122">Term</span></span>|  
|---|---|  
|[<span data-ttu-id="b3cf2-123">方法: 定数を宣言する</span><span class="sxs-lookup"><span data-stu-id="b3cf2-123">How to: Declare A Constant</span></span>](how-to-declare-a-constant.md)|<span data-ttu-id="b3cf2-124">`Const` ステートメントを使用して定数とその値を宣言する方法について説明します。定数を宣言することで、値にわかりやすい名前を付けることができます。</span><span class="sxs-lookup"><span data-stu-id="b3cf2-124">Explains how to use the `Const` statement to declare a constant and set its value; by declaring a constant, you assign a meaningful name to the value.</span></span>|  
|[<span data-ttu-id="b3cf2-125">ユーザー定義定数</span><span class="sxs-lookup"><span data-stu-id="b3cf2-125">User-Defined Constants</span></span>](user-defined-constants.md)|<span data-ttu-id="b3cf2-126">独自の定数の作成方法について、スコープの設定や循環参照の回避方法なども含めて説明します。</span><span class="sxs-lookup"><span data-stu-id="b3cf2-126">Describes how to create your own constants, including information on scoping and how to avoid circular references.</span></span>|  
|[<span data-ttu-id="b3cf2-127">定数とリテラルのデータ型</span><span class="sxs-lookup"><span data-stu-id="b3cf2-127">Constant and Literal Data Types</span></span>](constant-and-literal-data-types.md)|<span data-ttu-id="b3cf2-128">`Option Explicit` が Off の場合に Visual Basic コンパイラが定数を初期化するしくみについて説明します。</span><span class="sxs-lookup"><span data-stu-id="b3cf2-128">Provides information on how the Visual Basic compiler initializes constants when `Option Explicit` is turned off.</span></span>|  
|[<span data-ttu-id="b3cf2-129">方法: 関連する定数値をまとめてグループ化する</span><span class="sxs-lookup"><span data-stu-id="b3cf2-129">How to: Group Related Constant Values Together</span></span>](how-to-group-related-constant-values-together.md)|<span data-ttu-id="b3cf2-130">関連する定数の値をグループ化する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b3cf2-130">Demonstrates how to group constant values that are related.</span></span>|  
  
## <a name="reference"></a><span data-ttu-id="b3cf2-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="b3cf2-131">Reference</span></span>  
  
|<span data-ttu-id="b3cf2-132">定義</span><span class="sxs-lookup"><span data-stu-id="b3cf2-132">Definition</span></span>|<span data-ttu-id="b3cf2-133">用語</span><span class="sxs-lookup"><span data-stu-id="b3cf2-133">Term</span></span>|  
|---|---|  
|[<span data-ttu-id="b3cf2-134">定数と列挙体</span><span class="sxs-lookup"><span data-stu-id="b3cf2-134">Constants and Enumerations</span></span>](../../../language-reference/constants-and-enumerations.md)|<span data-ttu-id="b3cf2-135">Visual Basic の事前定義定数の一覧を紹介します。</span><span class="sxs-lookup"><span data-stu-id="b3cf2-135">Lists the constants predefined by Visual Basic.</span></span>|  
|[<span data-ttu-id="b3cf2-136">Const ステートメント</span><span class="sxs-lookup"><span data-stu-id="b3cf2-136">Const Statement</span></span>](../../../language-reference/statements/const-statement.md)|<span data-ttu-id="b3cf2-137">`Const` ステートメントとその使用法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b3cf2-137">Describes the `Const` statement and its use.</span></span>|  
|[<span data-ttu-id="b3cf2-138">Option Strict ステートメント</span><span class="sxs-lookup"><span data-stu-id="b3cf2-138">Option Strict Statement</span></span>](../../../language-reference/statements/option-strict-statement.md)|<span data-ttu-id="b3cf2-139">`Option Strict` ステートメントとその使用法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b3cf2-139">Describes the `Option Strict` statement and its use.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b3cf2-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="b3cf2-140">See also</span></span>

- [<span data-ttu-id="b3cf2-141">列挙型の概要</span><span class="sxs-lookup"><span data-stu-id="b3cf2-141">Enumerations Overview</span></span>](enumerations-overview.md)
- [<span data-ttu-id="b3cf2-142">方法: Visual Basic で配列変数を初期化する</span><span class="sxs-lookup"><span data-stu-id="b3cf2-142">How to: Initialize an Array Variable in Visual Basic</span></span>](../arrays/how-to-initialize-an-array-variable.md)
