---
title: 定数と列挙体
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic]
- Visual Basic code, constants
- constants [Visual Basic]
- object libraries, Object Browser
- Visual Basic code, enumerations
- declaring constants [Visual Basic], enumerations
- naming conventions [Visual Basic], constants
- Visual Basic code, improving readability with constants
ms.assetid: c8aba36e-fa47-4a33-8b68-cb2009218270
ms.openlocfilehash: 7d15c46c0f6bb00c23dd98e464f61a5f94b0773a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "85503837"
---
# <a name="constants-and-enumerations-in-visual-basic"></a><span data-ttu-id="279e9-102">Visual Basic の定数と列挙体</span><span class="sxs-lookup"><span data-stu-id="279e9-102">Constants and Enumerations in Visual Basic</span></span>
<span data-ttu-id="279e9-103">定数は、変化しない値の代わりにわかりやすい名前を使用するための方法です。</span><span class="sxs-lookup"><span data-stu-id="279e9-103">Constants are a way to use meaningful names in place of a value that does not change.</span></span> <span data-ttu-id="279e9-104">定数に格納された値は、その名が示すとおり、アプリケーションの実行中に変わることはありません。</span><span class="sxs-lookup"><span data-stu-id="279e9-104">Constants store values that, as the name implies, remain constant throughout the execution of an application.</span></span> <span data-ttu-id="279e9-105">定数を使用すると、数値の代わりにわかりやすい名前を指定できるので、コードが読みやすくなります。</span><span class="sxs-lookup"><span data-stu-id="279e9-105">You can use constants to provide meaningful names, instead of numbers, making your code more readable.</span></span>  
  
 <span data-ttu-id="279e9-106">一連の関連する定数を操作する場合や、定数値に名前を関連付ける場合は、列挙型を使うと便利です。</span><span class="sxs-lookup"><span data-stu-id="279e9-106">Enumerations provide a convenient way to work with sets of related constants, and to associate constant values with names.</span></span> <span data-ttu-id="279e9-107">たとえば、一連の整数型の定数を曜日に関連付けて列挙型として宣言すると、コードで整数値ではなく曜日名を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="279e9-107">For example, you can declare an enumeration for a set of integer constants associated with the days of the week, and then use the names of the days rather than their integer values in your code.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="279e9-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="279e9-108">In This Section</span></span>  
  
|<span data-ttu-id="279e9-109">用語</span><span class="sxs-lookup"><span data-stu-id="279e9-109">Term</span></span>|<span data-ttu-id="279e9-110">定義</span><span class="sxs-lookup"><span data-stu-id="279e9-110">Definition</span></span>|  
|---|---|  
|[<span data-ttu-id="279e9-111">定数の概要</span><span class="sxs-lookup"><span data-stu-id="279e9-111">Constants Overview</span></span>](constants-overview.md)|<span data-ttu-id="279e9-112">このセクションのトピックでは定数とその使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="279e9-112">Topics in this section describe constants and their uses.</span></span>|  
|[<span data-ttu-id="279e9-113">列挙型の概要</span><span class="sxs-lookup"><span data-stu-id="279e9-113">Enumerations Overview</span></span>](enumerations-overview.md)|<span data-ttu-id="279e9-114">このセクションのトピックでは列挙型とその使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="279e9-114">Topics in this section describe enumerations and their uses.</span></span>|  
  
## <a name="related-sections"></a><span data-ttu-id="279e9-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="279e9-115">Related Sections</span></span>  
  
|<span data-ttu-id="279e9-116">用語</span><span class="sxs-lookup"><span data-stu-id="279e9-116">Term</span></span>|<span data-ttu-id="279e9-117">定義</span><span class="sxs-lookup"><span data-stu-id="279e9-117">Definition</span></span>|  
|---|---|  
|[<span data-ttu-id="279e9-118">Const ステートメント</span><span class="sxs-lookup"><span data-stu-id="279e9-118">Const Statement</span></span>](../../../language-reference/statements/const-statement.md)|<span data-ttu-id="279e9-119">整数の宣言に使用される、`Const` ステートメントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="279e9-119">Describes the `Const` statement, which is used to declare constants.</span></span>|  
|[<span data-ttu-id="279e9-120">Enum ステートメント</span><span class="sxs-lookup"><span data-stu-id="279e9-120">Enum Statement</span></span>](../../../language-reference/statements/enum-statement.md)|<span data-ttu-id="279e9-121">列挙型の作成に使用される、`Enum` ステートメントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="279e9-121">Describes the `Enum` statement, which is used to create enumerations.</span></span>|  
|[<span data-ttu-id="279e9-122">Option Explicit ステートメント</span><span class="sxs-lookup"><span data-stu-id="279e9-122">Option Explicit Statement</span></span>](../../../language-reference/statements/option-explicit-statement.md)|<span data-ttu-id="279e9-123">`Option Explicit` ステートメントについて説明します。このステートメントはモジュール レベルで使用され、そのモジュール内のすべての変数の明示的な宣言を強制します。</span><span class="sxs-lookup"><span data-stu-id="279e9-123">Describes the `Option Explicit` statement, which is used at module level to force explicit declaration of all variables in that module.</span></span>|  
|[<span data-ttu-id="279e9-124">Option Infer ステートメント</span><span class="sxs-lookup"><span data-stu-id="279e9-124">Option Infer Statement</span></span>](../../../language-reference/statements/option-infer-statement.md)|<span data-ttu-id="279e9-125">`Option Infer` ステートメントについて説明します。このステートメントは、変数の宣言でローカル型推論を使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="279e9-125">Describes the `Option Infer` statement, which enables the use of local type inference in declaring variables.</span></span>|  
|[<span data-ttu-id="279e9-126">Option Strict ステートメント</span><span class="sxs-lookup"><span data-stu-id="279e9-126">Option Strict Statement</span></span>](../../../language-reference/statements/option-strict-statement.md)|<span data-ttu-id="279e9-127">`Object` ステートメントについて説明します。このステートメントは、暗黙的なデータ型変換を拡大変換のみに制限し、遅延バインディングを許可せず、`Option Strict` 型になる暗黙的な型指定も許可しません。</span><span class="sxs-lookup"><span data-stu-id="279e9-127">Describes the `Option Strict` statement, which restricts implicit data type conversions to only widening conversions, disallows late binding, and disallows implicit typing that results in an `Object` type.</span></span>|
