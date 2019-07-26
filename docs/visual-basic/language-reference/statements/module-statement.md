---
title: Module ステートメント (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- Module
- vb.Module
helpviewer_keywords:
- modules, classes
- modules
- Module statement [Visual Basic]
- modules, declaring
- standard modules
- classes [Visual Basic], vs. modules
- declarations [Visual Basic], modules
ms.assetid: a1243afc-14a5-45df-95d5-51118aeac362
ms.openlocfilehash: 08268fd473a3a916f41f2f46090e3245acda07dd
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/26/2019
ms.locfileid: "68513005"
---
# <a name="module-statement"></a><span data-ttu-id="51479-102">Module ステートメント</span><span class="sxs-lookup"><span data-stu-id="51479-102">Module Statement</span></span>
<span data-ttu-id="51479-103">モジュールの名前を宣言し、モジュールが構成する変数、プロパティ、イベント、およびプロシージャの定義を紹介します。</span><span class="sxs-lookup"><span data-stu-id="51479-103">Declares the name of a module and introduces the definition of the variables, properties, events, and procedures that the module comprises.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51479-104">構文</span><span class="sxs-lookup"><span data-stu-id="51479-104">Syntax</span></span>  
  
```vb 
[ <attributelist> ] [ accessmodifier ]  Module name  
    [ statements ]  
End Module  
```  
  
## <a name="parts"></a><span data-ttu-id="51479-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="51479-105">Parts</span></span>  
 `attributelist`  
 <span data-ttu-id="51479-106">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="51479-106">Optional.</span></span> <span data-ttu-id="51479-107">参照してください[属性リスト](../../../visual-basic/language-reference/statements/attribute-list.md)します。</span><span class="sxs-lookup"><span data-stu-id="51479-107">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>  
  
 `accessmodifier`  
 <span data-ttu-id="51479-108">任意。</span><span class="sxs-lookup"><span data-stu-id="51479-108">Optional.</span></span> <span data-ttu-id="51479-109">次のいずれかの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="51479-109">Can be one of the following:</span></span>  
  
- [<span data-ttu-id="51479-110">Public</span><span class="sxs-lookup"><span data-stu-id="51479-110">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
  
- [<span data-ttu-id="51479-111">Friend</span><span class="sxs-lookup"><span data-stu-id="51479-111">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
  
 <span data-ttu-id="51479-112">「 [Visual Basic でのアクセス レベル](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51479-112">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 `name`  
 <span data-ttu-id="51479-113">必須。</span><span class="sxs-lookup"><span data-stu-id="51479-113">Required.</span></span> <span data-ttu-id="51479-114">このモジュールの名前。</span><span class="sxs-lookup"><span data-stu-id="51479-114">Name of this module.</span></span> <span data-ttu-id="51479-115">「 [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51479-115">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
 `statements`  
 <span data-ttu-id="51479-116">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="51479-116">Optional.</span></span> <span data-ttu-id="51479-117">このモジュールの変数、プロパティ、イベント、プロシージャ、および入れ子にされた型を定義するステートメント。</span><span class="sxs-lookup"><span data-stu-id="51479-117">Statements which define the variables, properties, events, procedures, and nested types of this module.</span></span>  
  
 `End Module`  
 <span data-ttu-id="51479-118">`Module` の定義を終了します。</span><span class="sxs-lookup"><span data-stu-id="51479-118">Terminates the `Module` definition.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="51479-119">Remarks</span><span class="sxs-lookup"><span data-stu-id="51479-119">Remarks</span></span>  
 <span data-ttu-id="51479-120">`Module` ステートメントは、その名前空間全体で使用できる参照型を定義します。</span><span class="sxs-lookup"><span data-stu-id="51479-120">A `Module` statement defines a reference type available throughout its namespace.</span></span> <span data-ttu-id="51479-121">*モジュール*(*標準モジュール*と呼ばれることもあります) はクラスに似ていますが、重要な違いがいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="51479-121">A *module* (sometimes called a *standard module*) is similar to a class but with some important distinctions.</span></span> <span data-ttu-id="51479-122">すべてのモジュールにはインスタンスが1つだけあり、変数を作成したり、変数に割り当てたりする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="51479-122">Every module has exactly one instance and does not need to be created or assigned to a variable.</span></span> <span data-ttu-id="51479-123">モジュールは、継承をサポートしていないか、インターフェイスを実装していません。</span><span class="sxs-lookup"><span data-stu-id="51479-123">Modules do not support inheritance or implement interfaces.</span></span> <span data-ttu-id="51479-124">モジュールが、クラスまたは構造体の意味では*型*ではないことに注意してください。モジュールのデータ型を持つプログラミング要素を宣言することはできません。</span><span class="sxs-lookup"><span data-stu-id="51479-124">Notice that a module is not a *type* in the sense that a class or structure is — you cannot declare a programming element to have the data type of a module.</span></span>  
  
 <span data-ttu-id="51479-125">は、名前`Module`空間レベルでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="51479-125">You can use `Module` only at namespace level.</span></span> <span data-ttu-id="51479-126">つまり、モジュールの*宣言コンテキスト*はソースファイルまたは名前空間である必要があり、クラス、構造体、モジュール、インターフェイス、プロシージャ、またはブロックにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="51479-126">This means the *declaration context* for a module must be a source file or namespace, and cannot be a class, structure, module, interface, procedure, or block.</span></span> <span data-ttu-id="51479-127">モジュールは、別のモジュール内、または任意の型の中で入れ子にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="51479-127">You cannot nest a module within another module, or within any type.</span></span> <span data-ttu-id="51479-128">詳細については、「[宣言コンテキストと既定のアクセス レベル](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51479-128">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="51479-129">モジュールには、プログラムと同じ有効期間があります。</span><span class="sxs-lookup"><span data-stu-id="51479-129">A module has the same lifetime as your program.</span></span> <span data-ttu-id="51479-130">メンバーはすべて`Shared`のメンバーであるため、プログラムの有効期間と同じになります。</span><span class="sxs-lookup"><span data-stu-id="51479-130">Because its members are all `Shared`, they also have lifetimes equal to that of the program.</span></span>  
  
 <span data-ttu-id="51479-131">モジュールは既定で[フレンド](../../../visual-basic/language-reference/modifiers/friend.md)アクセスになります。</span><span class="sxs-lookup"><span data-stu-id="51479-131">Modules default to [Friend](../../../visual-basic/language-reference/modifiers/friend.md) access.</span></span> <span data-ttu-id="51479-132">アクセス修飾子を使用してこれらのアクセス レベルを調整できます。</span><span class="sxs-lookup"><span data-stu-id="51479-132">You can adjust their access levels with the access modifiers.</span></span> <span data-ttu-id="51479-133">詳細については、[ Visual Basic のアクセス レベル](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51479-133">For more information, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="51479-134">モジュールのすべてのメンバーが暗黙的`Shared`になります。</span><span class="sxs-lookup"><span data-stu-id="51479-134">All members of a module are implicitly `Shared`.</span></span>  
  
## <a name="classes-and-modules"></a><span data-ttu-id="51479-135">クラスとモジュール</span><span class="sxs-lookup"><span data-stu-id="51479-135">Classes and Modules</span></span>  
 <span data-ttu-id="51479-136">これらの要素には多くの類似点がありますが、重要な相違点もいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="51479-136">These elements have many similarities, but there are some important differences as well.</span></span>  
  
- <span data-ttu-id="51479-137">**関する.**</span><span class="sxs-lookup"><span data-stu-id="51479-137">**Terminology.**</span></span> <span data-ttu-id="51479-138">以前のバージョンの Visual Basic では、*クラスモジュール*(cls ファイル) と*標準モジュール*(.bas ファイル) という2種類のモジュールが認識されています。</span><span class="sxs-lookup"><span data-stu-id="51479-138">Previous versions of Visual Basic recognize two types of modules: *class modules* (.cls files) and *standard modules* (.bas files).</span></span> <span data-ttu-id="51479-139">現在のバージョンは、これらの*クラス*と*モジュール*をそれぞれ呼び出します。</span><span class="sxs-lookup"><span data-stu-id="51479-139">The current version calls these *classes* and *modules*, respectively.</span></span>  
  
- <span data-ttu-id="51479-140">**共有メンバー。**</span><span class="sxs-lookup"><span data-stu-id="51479-140">**Shared Members.**</span></span> <span data-ttu-id="51479-141">クラスのメンバーが共有メンバーまたはインスタンスメンバーであるかどうかを制御できます。</span><span class="sxs-lookup"><span data-stu-id="51479-141">You can control whether a member of a class is a shared or instance member.</span></span>  
  
- <span data-ttu-id="51479-142">**オブジェクトの向き。**</span><span class="sxs-lookup"><span data-stu-id="51479-142">**Object Orientation.**</span></span> <span data-ttu-id="51479-143">クラスはオブジェクト指向ですが、モジュールはそうではありません。</span><span class="sxs-lookup"><span data-stu-id="51479-143">Classes are object-oriented, but modules are not.</span></span> <span data-ttu-id="51479-144">したがって、オブジェクトとしてインスタンス化できるのはクラスだけです。</span><span class="sxs-lookup"><span data-stu-id="51479-144">So only classes can be instantiated as objects.</span></span> <span data-ttu-id="51479-145">詳細については、「[オブジェクトとクラス](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51479-145">For more information, see [Objects and Classes](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="51479-146">ルール</span><span class="sxs-lookup"><span data-stu-id="51479-146">Rules</span></span>  
  
- <span data-ttu-id="51479-147">**ド.**</span><span class="sxs-lookup"><span data-stu-id="51479-147">**Modifiers.**</span></span> <span data-ttu-id="51479-148">すべてのモジュールメンバーは暗黙的に[共有](../../../visual-basic/language-reference/modifiers/shared.md)されます。</span><span class="sxs-lookup"><span data-stu-id="51479-148">All module members are implicitly [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span> <span data-ttu-id="51479-149">メンバーを宣言する`Shared`ときにキーワードを使用することはできません。また、メンバーの共有ステータスを変更することもできません。</span><span class="sxs-lookup"><span data-stu-id="51479-149">You cannot use the `Shared` keyword when declaring a member, and you cannot alter the shared status of any member.</span></span>  
  
- <span data-ttu-id="51479-150">**継承。**</span><span class="sxs-lookup"><span data-stu-id="51479-150">**Inheritance.**</span></span> <span data-ttu-id="51479-151">モジュールは、すべてのモジュールが継承する<xref:System.Object>以外の型から継承することはできません。</span><span class="sxs-lookup"><span data-stu-id="51479-151">A module cannot inherit from any type other than <xref:System.Object>, from which all modules inherit.</span></span> <span data-ttu-id="51479-152">特に、1つのモジュールが別のモジュールから継承することはできません。</span><span class="sxs-lookup"><span data-stu-id="51479-152">In particular, one module cannot inherit from another.</span></span>  
  
     <span data-ttu-id="51479-153">を指定<xref:System.Object>する場合でも、モジュール定義で[Inherits ステートメント](../../../visual-basic/language-reference/statements/inherits-statement.md)を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="51479-153">You cannot use the [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md) in a module definition, even to specify <xref:System.Object>.</span></span>  
  
- <span data-ttu-id="51479-154">**既定のプロパティ。**</span><span class="sxs-lookup"><span data-stu-id="51479-154">**Default Property.**</span></span> <span data-ttu-id="51479-155">モジュールでは、既定のプロパティを定義することはできません。</span><span class="sxs-lookup"><span data-stu-id="51479-155">You cannot define any default properties in a module.</span></span> <span data-ttu-id="51479-156">詳細については、「 [Default](../../../visual-basic/language-reference/modifiers/default.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51479-156">For more information, see [Default](../../../visual-basic/language-reference/modifiers/default.md).</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="51479-157">動作</span><span class="sxs-lookup"><span data-stu-id="51479-157">Behavior</span></span>  
  
- <span data-ttu-id="51479-158">**アクセス レベル。**</span><span class="sxs-lookup"><span data-stu-id="51479-158">**Access Level.**</span></span> <span data-ttu-id="51479-159">モジュール内では、各メンバーを独自のアクセス レベルで宣言できます。</span><span class="sxs-lookup"><span data-stu-id="51479-159">Within a module, you can declare each member with its own access level.</span></span> <span data-ttu-id="51479-160">モジュール メンバーはデフォルトで[パブリック](../../../visual-basic/language-reference/modifiers/public.md)アクセスになりますが、変数および定数はデフォルトで[プライベート](../../../visual-basic/language-reference/modifiers/private.md)アクセスになります。</span><span class="sxs-lookup"><span data-stu-id="51479-160">Module members default to [Public](../../../visual-basic/language-reference/modifiers/public.md) access, except variables and constants, which default to [Private](../../../visual-basic/language-reference/modifiers/private.md) access.</span></span> <span data-ttu-id="51479-161">モジュールがそのメンバーの 1 つ以上のアクセス権を持っている場合、指定されたモジュールへのアクセス レベルが優先されます。</span><span class="sxs-lookup"><span data-stu-id="51479-161">When a module has more restricted access than one of its members, the specified module access level takes precedence.</span></span>  
  
- <span data-ttu-id="51479-162">**検索.**</span><span class="sxs-lookup"><span data-stu-id="51479-162">**Scope.**</span></span> <span data-ttu-id="51479-163">モジュールは、名前空間全体でスコープ内にあります。</span><span class="sxs-lookup"><span data-stu-id="51479-163">A module is in scope throughout its namespace.</span></span>  
  
     <span data-ttu-id="51479-164">すべてのモジュールメンバーのスコープは、モジュール全体です。</span><span class="sxs-lookup"><span data-stu-id="51479-164">The scope of every module member is the entire module.</span></span> <span data-ttu-id="51479-165">すべてのメンバーに*型の上位変換*が適用されていることに注意してください。これにより、そのスコープがモジュールを含む名前空間に昇格します。</span><span class="sxs-lookup"><span data-stu-id="51479-165">Notice that all members undergo *type promotion*, which causes their scope to be promoted to the namespace containing the module.</span></span> <span data-ttu-id="51479-166">詳細については、「[型の上位変換](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51479-166">For more information, see [Type Promotion](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md).</span></span>  
  
- <span data-ttu-id="51479-167">**修飾。**</span><span class="sxs-lookup"><span data-stu-id="51479-167">**Qualification.**</span></span> <span data-ttu-id="51479-168">プロジェクトには複数のモジュールを含めることができます。また、2 つ以上の複数のモジュールで同じ名前を持つメンバーを宣言することができます。</span><span class="sxs-lookup"><span data-stu-id="51479-168">You can have multiple modules in a project, and you can declare members with the same name in two or more modules.</span></span> <span data-ttu-id="51479-169">ただし、そのようなメンバーへの参照がそのモジュールの外部からのものである場合は、適切なモジュール名を使用して修飾する必要があります。</span><span class="sxs-lookup"><span data-stu-id="51479-169">However, you must qualify any reference to such a member with the appropriate module name if the reference is from outside that module.</span></span> <span data-ttu-id="51479-170">詳細については、「 [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51479-170">For more information, see [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="51479-171">例</span><span class="sxs-lookup"><span data-stu-id="51479-171">Example</span></span>  
 [!code-vb[VbVbalrStatements#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#69)]  
  
## <a name="see-also"></a><span data-ttu-id="51479-172">関連項目</span><span class="sxs-lookup"><span data-stu-id="51479-172">See also</span></span>

- [<span data-ttu-id="51479-173">Class ステートメント</span><span class="sxs-lookup"><span data-stu-id="51479-173">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)
- [<span data-ttu-id="51479-174">Namespace ステートメント</span><span class="sxs-lookup"><span data-stu-id="51479-174">Namespace Statement</span></span>](../../../visual-basic/language-reference/statements/namespace-statement.md)
- [<span data-ttu-id="51479-175">Structure ステートメント</span><span class="sxs-lookup"><span data-stu-id="51479-175">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="51479-176">Interface ステートメント</span><span class="sxs-lookup"><span data-stu-id="51479-176">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)
- [<span data-ttu-id="51479-177">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="51479-177">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="51479-178">型の上位変換</span><span class="sxs-lookup"><span data-stu-id="51479-178">Type Promotion</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md)
