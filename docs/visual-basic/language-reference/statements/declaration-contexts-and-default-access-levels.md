---
title: 宣言コンテキストと既定のアクセス レベル
ms.date: 07/20/2015
helpviewer_keywords:
- module level, defined
- declaration contexts, Visual Basic
- procedure level, defined
- namespace level, defined
- access levels, Visual Basic
- access levels, default levels
ms.assetid: bf63b96e-e825-4745-88c8-5dae222728db
ms.openlocfilehash: a659481b34b8b44f1f387b464d5d9656ed98ab3f
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874951"
---
# <a name="declaration-contexts-and-default-access-levels-visual-basic"></a><span data-ttu-id="71578-102">宣言コンテキストと既定のアクセス レベル (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="71578-102">Declaration Contexts and Default Access Levels (Visual Basic)</span></span>

<span data-ttu-id="71578-103">このトピックでは、どの Visual Basic の型を他のどの型内に宣言できるか、およびそれらのアクセス レベルが指定されていない場合の既定値について説明します。</span><span class="sxs-lookup"><span data-stu-id="71578-103">This topic describes which Visual Basic types can be declared within which other types, and what their access levels default to if not specified.</span></span>  
  
## <a name="declaration-context-levels"></a><span data-ttu-id="71578-104">宣言コンテキスト レベル</span><span class="sxs-lookup"><span data-stu-id="71578-104">Declaration Context Levels</span></span>  

 <span data-ttu-id="71578-105">プログラミング要素の*宣言コンテキスト*は、それが宣言されているコードの領域です。</span><span class="sxs-lookup"><span data-stu-id="71578-105">The *declaration context* of a programming element is the region of code in which it is declared.</span></span> <span data-ttu-id="71578-106">これは、多くの場合、別のプログラミング要素であり、そのために*親要素*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="71578-106">This is often another programming element, which is then called the *containing element*.</span></span>  
  
 <span data-ttu-id="71578-107">宣言コンテキストのレベルは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="71578-107">The levels for declaration contexts are the following:</span></span>  
  
- <span data-ttu-id="71578-108">*名前空間レベル* - ソースファイルまたは名前空間内であり、クラス、構造体、モジュール、またはインターフェイス内ではありません</span><span class="sxs-lookup"><span data-stu-id="71578-108">*Namespace level* — within a source file or namespace but not within a class, structure, module, or interface</span></span>  
  
- <span data-ttu-id="71578-109">*モジュール レベル* - クラス、構造体、モジュール、またはインターフェイス内であり、プロシージャまたはブロック内ではありません</span><span class="sxs-lookup"><span data-stu-id="71578-109">*Module level* — within a class, structure, module, or interface but not within a procedure or block</span></span>  
  
- <span data-ttu-id="71578-110">*プロシージャ レベル* - プロシージャまたはブロック (`If` や `For` など) 内です</span><span class="sxs-lookup"><span data-stu-id="71578-110">*Procedure level* — within a procedure or block (such as `If` or `For`)</span></span>  
  
 <span data-ttu-id="71578-111">次の表に、宣言コンテキストに応じて、宣言されたさまざまなプログラミング要素の既定のアクセス レベルを示します。</span><span class="sxs-lookup"><span data-stu-id="71578-111">The following table shows the default access levels for various declared programming elements, depending on their declaration contexts.</span></span>  
  
|<span data-ttu-id="71578-112">宣言された要素</span><span class="sxs-lookup"><span data-stu-id="71578-112">Declared element</span></span>|<span data-ttu-id="71578-113">名前空間レベル</span><span class="sxs-lookup"><span data-stu-id="71578-113">Namespace level</span></span>|<span data-ttu-id="71578-114">モジュール レベル</span><span class="sxs-lookup"><span data-stu-id="71578-114">Module level</span></span>|<span data-ttu-id="71578-115">プロシージャ レベル</span><span class="sxs-lookup"><span data-stu-id="71578-115">Procedure level</span></span>|  
|----------------------|---------------------|------------------|---------------------|  
|<span data-ttu-id="71578-116">変数 ([Dim ステートメント](dim-statement.md))</span><span class="sxs-lookup"><span data-stu-id="71578-116">Variable ([Dim Statement](dim-statement.md))</span></span>|<span data-ttu-id="71578-117">使用できません</span><span class="sxs-lookup"><span data-stu-id="71578-117">Not allowed</span></span>|<span data-ttu-id="71578-118">`Private` (`Structure` 内の `Public`、`Interface` では使用できません)</span><span class="sxs-lookup"><span data-stu-id="71578-118">`Private` (`Public` in `Structure`, not allowed in `Interface`)</span></span>|`Public`|  
|<span data-ttu-id="71578-119">定数 ([Const ステートメント](const-statement.md))</span><span class="sxs-lookup"><span data-stu-id="71578-119">Constant ([Const Statement](const-statement.md))</span></span>|<span data-ttu-id="71578-120">使用できません</span><span class="sxs-lookup"><span data-stu-id="71578-120">Not allowed</span></span>|<span data-ttu-id="71578-121">`Private` (`Structure` 内の `Public`、`Interface` では使用できません)</span><span class="sxs-lookup"><span data-stu-id="71578-121">`Private` (`Public` in `Structure`, not allowed in `Interface`)</span></span>|`Public`|  
|<span data-ttu-id="71578-122">列挙型 ([Enum ステートメント](enum-statement.md))</span><span class="sxs-lookup"><span data-stu-id="71578-122">Enumeration ([Enum Statement](enum-statement.md))</span></span>|`Friend`|`Public`|<span data-ttu-id="71578-123">使用できません</span><span class="sxs-lookup"><span data-stu-id="71578-123">Not allowed</span></span>|  
|<span data-ttu-id="71578-124">クラス ([Class ステートメント](class-statement.md))</span><span class="sxs-lookup"><span data-stu-id="71578-124">Class ([Class Statement](class-statement.md))</span></span>|`Friend`|`Public`|<span data-ttu-id="71578-125">使用できません</span><span class="sxs-lookup"><span data-stu-id="71578-125">Not allowed</span></span>|  
|<span data-ttu-id="71578-126">構造体 ([Structure ステートメント](structure-statement.md))</span><span class="sxs-lookup"><span data-stu-id="71578-126">Structure ([Structure Statement](structure-statement.md))</span></span>|`Friend`|`Public`|<span data-ttu-id="71578-127">使用できません</span><span class="sxs-lookup"><span data-stu-id="71578-127">Not allowed</span></span>|  
|<span data-ttu-id="71578-128">モジュール ([Module ステートメント](module-statement.md))</span><span class="sxs-lookup"><span data-stu-id="71578-128">Module ([Module Statement](module-statement.md))</span></span>|`Friend`|<span data-ttu-id="71578-129">使用できません</span><span class="sxs-lookup"><span data-stu-id="71578-129">Not allowed</span></span>|<span data-ttu-id="71578-130">使用できません</span><span class="sxs-lookup"><span data-stu-id="71578-130">Not allowed</span></span>|  
|<span data-ttu-id="71578-131">インターフェイス ([Interface ステートメント](interface-statement.md))</span><span class="sxs-lookup"><span data-stu-id="71578-131">Interface ([Interface Statement](interface-statement.md))</span></span>|`Friend`|`Public`|<span data-ttu-id="71578-132">使用できません</span><span class="sxs-lookup"><span data-stu-id="71578-132">Not allowed</span></span>|  
|<span data-ttu-id="71578-133">プロシージャ ([Function ステートメント](function-statement.md)、[Sub ステートメント](sub-statement.md))</span><span class="sxs-lookup"><span data-stu-id="71578-133">Procedure ([Function Statement](function-statement.md), [Sub Statement](sub-statement.md))</span></span>|<span data-ttu-id="71578-134">使用できません</span><span class="sxs-lookup"><span data-stu-id="71578-134">Not allowed</span></span>|`Public`|<span data-ttu-id="71578-135">使用できません</span><span class="sxs-lookup"><span data-stu-id="71578-135">Not allowed</span></span>|  
|<span data-ttu-id="71578-136">外部参照 ([Declare ステートメント](declare-statement.md))</span><span class="sxs-lookup"><span data-stu-id="71578-136">External reference ([Declare Statement](declare-statement.md))</span></span>|<span data-ttu-id="71578-137">使用できません</span><span class="sxs-lookup"><span data-stu-id="71578-137">Not allowed</span></span>|<span data-ttu-id="71578-138">`Public` (`Interface` では使用できません)</span><span class="sxs-lookup"><span data-stu-id="71578-138">`Public` (not allowed in `Interface`)</span></span>|<span data-ttu-id="71578-139">使用できません</span><span class="sxs-lookup"><span data-stu-id="71578-139">Not allowed</span></span>|  
|<span data-ttu-id="71578-140">演算子 ([Operator ステートメント](operator-statement.md))</span><span class="sxs-lookup"><span data-stu-id="71578-140">Operator ([Operator Statement](operator-statement.md))</span></span>|<span data-ttu-id="71578-141">使用できません</span><span class="sxs-lookup"><span data-stu-id="71578-141">Not allowed</span></span>|<span data-ttu-id="71578-142">`Public` (`Interface` または `Module` では使用できません)</span><span class="sxs-lookup"><span data-stu-id="71578-142">`Public` (not allowed in `Interface` or `Module`)</span></span>|<span data-ttu-id="71578-143">使用できません</span><span class="sxs-lookup"><span data-stu-id="71578-143">Not allowed</span></span>|  
|<span data-ttu-id="71578-144">プロパティ ([Property ステートメント](property-statement.md))</span><span class="sxs-lookup"><span data-stu-id="71578-144">Property ([Property Statement](property-statement.md))</span></span>|<span data-ttu-id="71578-145">使用できません</span><span class="sxs-lookup"><span data-stu-id="71578-145">Not allowed</span></span>|`Public`|<span data-ttu-id="71578-146">使用できません</span><span class="sxs-lookup"><span data-stu-id="71578-146">Not allowed</span></span>|  
|<span data-ttu-id="71578-147">既定のプロパティ ([Default](../modifiers/default.md))</span><span class="sxs-lookup"><span data-stu-id="71578-147">Default property ([Default](../modifiers/default.md))</span></span>|<span data-ttu-id="71578-148">使用できません</span><span class="sxs-lookup"><span data-stu-id="71578-148">Not allowed</span></span>|<span data-ttu-id="71578-149">`Public` (`Module` では使用できません)</span><span class="sxs-lookup"><span data-stu-id="71578-149">`Public` (not allowed in `Module`)</span></span>|<span data-ttu-id="71578-150">使用できません</span><span class="sxs-lookup"><span data-stu-id="71578-150">Not allowed</span></span>|  
|<span data-ttu-id="71578-151">イベント ([Event ステートメント](event-statement.md))</span><span class="sxs-lookup"><span data-stu-id="71578-151">Event ([Event Statement](event-statement.md))</span></span>|<span data-ttu-id="71578-152">使用できません</span><span class="sxs-lookup"><span data-stu-id="71578-152">Not allowed</span></span>|`Public`|<span data-ttu-id="71578-153">使用できません</span><span class="sxs-lookup"><span data-stu-id="71578-153">Not allowed</span></span>|  
|<span data-ttu-id="71578-154">委任 ([Delegate ステートメント](delegate-statement.md))</span><span class="sxs-lookup"><span data-stu-id="71578-154">Delegate ([Delegate Statement](delegate-statement.md))</span></span>|`Friend`|`Public`|<span data-ttu-id="71578-155">使用できません</span><span class="sxs-lookup"><span data-stu-id="71578-155">Not allowed</span></span>|  
  
 <span data-ttu-id="71578-156">詳しくは、「[Visual Basic でのアクセス レベル](../../programming-guide/language-features/declared-elements/access-levels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="71578-156">For more information, see [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71578-157">関連項目</span><span class="sxs-lookup"><span data-stu-id="71578-157">See also</span></span>

- [<span data-ttu-id="71578-158">Friend</span><span class="sxs-lookup"><span data-stu-id="71578-158">Friend</span></span>](../modifiers/friend.md)
- [<span data-ttu-id="71578-159">Private</span><span class="sxs-lookup"><span data-stu-id="71578-159">Private</span></span>](../modifiers/private.md)
- [<span data-ttu-id="71578-160">Public</span><span class="sxs-lookup"><span data-stu-id="71578-160">Public</span></span>](../modifiers/public.md)
