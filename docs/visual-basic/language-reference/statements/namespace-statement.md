---
title: Namespace ステートメント (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Namespace
helpviewer_keywords:
- namespaces [Visual Basic], root
- Namespace statement [Visual Basic]
- namespaces [Visual Basic], nested
- declaring namespaces [Visual Basic], syntax
- namespaces [Visual Basic], declaring
- root namespaces
- declarations [Visual Basic], namespaces
ms.assetid: a31fbd95-9ace-4c3d-bbb1-51222a2272b2
ms.openlocfilehash: 7f6b976af7933b3895f6992488d2d1532a8fc2f7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "58820933"
---
# <a name="namespace-statement"></a><span data-ttu-id="46fc7-102">Namespace ステートメント</span><span class="sxs-lookup"><span data-stu-id="46fc7-102">Namespace Statement</span></span>
<span data-ttu-id="46fc7-103">名前空間の名前を宣言し、ソース コードがその名前空間内でコンパイルするように宣言します。</span><span class="sxs-lookup"><span data-stu-id="46fc7-103">Declares the name of a namespace and causes the source code that follows the declaration to be compiled within that namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46fc7-104">構文</span><span class="sxs-lookup"><span data-stu-id="46fc7-104">Syntax</span></span>  
  
```vb  
Namespace [Global.] { name | name.name }  
    [ componenttypes ]  
End Namespace  
```  
  
## <a name="parts"></a><span data-ttu-id="46fc7-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="46fc7-105">Parts</span></span>  
 <span data-ttu-id="46fc7-106">Global</span><span class="sxs-lookup"><span data-stu-id="46fc7-106">Global</span></span>  
 <span data-ttu-id="46fc7-107">任意。</span><span class="sxs-lookup"><span data-stu-id="46fc7-107">Optional.</span></span> <span data-ttu-id="46fc7-108">プロジェクトのルート名前空間から名前空間を定義することができます。</span><span class="sxs-lookup"><span data-stu-id="46fc7-108">Allows you to define a namespace out of the root namespace of your project.</span></span> <span data-ttu-id="46fc7-109">参照してください[Visual Basic における名前空間](../../../visual-basic/programming-guide/program-structure/namespaces.md)します。</span><span class="sxs-lookup"><span data-stu-id="46fc7-109">See [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md).</span></span>  
  
 `name`  
 <span data-ttu-id="46fc7-110">必須。</span><span class="sxs-lookup"><span data-stu-id="46fc7-110">Required.</span></span> <span data-ttu-id="46fc7-111">名前空間を識別する一意の名前。</span><span class="sxs-lookup"><span data-stu-id="46fc7-111">A unique name that identifies the namespace.</span></span> <span data-ttu-id="46fc7-112">有効な Visual Basic 識別子である必要があります。</span><span class="sxs-lookup"><span data-stu-id="46fc7-112">Must be a valid Visual Basic identifier.</span></span> <span data-ttu-id="46fc7-113">詳細については、次を参照してください。 [宣言された要素の名前](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)</span><span class="sxs-lookup"><span data-stu-id="46fc7-113">For more information, see [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
 `componenttypes`  
 <span data-ttu-id="46fc7-114">任意。</span><span class="sxs-lookup"><span data-stu-id="46fc7-114">Optional.</span></span> <span data-ttu-id="46fc7-115">名前空間を構成する要素。</span><span class="sxs-lookup"><span data-stu-id="46fc7-115">Elements that make up the namespace.</span></span> <span data-ttu-id="46fc7-116">これらは、含めるが、列挙体、構造体、インターフェイス、クラス、モジュール、デリゲート、および他の名前空間に限定されません。</span><span class="sxs-lookup"><span data-stu-id="46fc7-116">These include, but are not limited to, enumerations, structures, interfaces, classes, modules, delegates, and other namespaces.</span></span>  
  
 `End Namespace`  
 <span data-ttu-id="46fc7-117">終了、`Namespace`ブロックします。</span><span class="sxs-lookup"><span data-stu-id="46fc7-117">Terminates a `Namespace` block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="46fc7-118">Remarks</span><span class="sxs-lookup"><span data-stu-id="46fc7-118">Remarks</span></span>  
 <span data-ttu-id="46fc7-119">名前空間は、組織のシステムとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="46fc7-119">Namespaces are used as an organizational system.</span></span> <span data-ttu-id="46fc7-120">分類およびその他のプログラム、およびアプリケーションに公開されているプログラミング要素を表現する手段となります。</span><span class="sxs-lookup"><span data-stu-id="46fc7-120">They provide a way to classify and present programming elements that are exposed to other programs and applications.</span></span> <span data-ttu-id="46fc7-121">名前空間がないので注意、*型*クラスまたは構造体は、という意味で、名前空間のデータ型を持つプログラミング要素を宣言することはできません。</span><span class="sxs-lookup"><span data-stu-id="46fc7-121">Note that a namespace is not a *type* in the sense that a class or structure is—you cannot declare a programming element to have the data type of a namespace.</span></span>  
  
 <span data-ttu-id="46fc7-122">後で宣言されたすべてのプログラミング要素、`Namespace`ステートメントは、その名前空間に属しています。</span><span class="sxs-lookup"><span data-stu-id="46fc7-122">All programming elements declared after a `Namespace` statement belong to that namespace.</span></span> <span data-ttu-id="46fc7-123">Visual Basic がいずれかを検出するまで、最後の宣言された名前空間に要素をコンパイルするには引き続き、`End Namespace`ステートメントまたは別`Namespace`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="46fc7-123">Visual Basic continues to compile elements into the last declared namespace until it encounters either an `End Namespace` statement or another `Namespace` statement.</span></span>  
  
 <span data-ttu-id="46fc7-124">名前空間は既に定義されている場合、プロジェクト以外でもをプログラミング要素を追加できます。</span><span class="sxs-lookup"><span data-stu-id="46fc7-124">If a namespace is already defined, even outside your project, you can add programming elements to it.</span></span> <span data-ttu-id="46fc7-125">これを行うには、使用する、`Namespace`その名前空間に要素をコンパイルする Visual Basic を指示するステートメント。</span><span class="sxs-lookup"><span data-stu-id="46fc7-125">To do this, you use a `Namespace` statement to direct Visual Basic to compile elements into that namespace.</span></span>  
  
 <span data-ttu-id="46fc7-126">使用することができます、`Namespace`ファイルまたは名前空間レベルでのみステートメント。</span><span class="sxs-lookup"><span data-stu-id="46fc7-126">You can use a `Namespace` statement only at the file or namespace level.</span></span> <span data-ttu-id="46fc7-127">つまり、*宣言コンテキスト*名前空間は、ソース ファイルまたは別の名前空間にある必要があり、クラス、構造体、モジュール、インターフェイス、またはプロシージャにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="46fc7-127">This means the *declaration context* for a namespace must be a source file or another namespace, and cannot be a class, structure, module, interface, or procedure.</span></span> <span data-ttu-id="46fc7-128">詳細については、「[宣言コンテキストと既定のアクセス レベル](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="46fc7-128">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="46fc7-129">別の 1 つの名前空間を宣言することができます。</span><span class="sxs-lookup"><span data-stu-id="46fc7-129">You can declare one namespace within another.</span></span> <span data-ttu-id="46fc7-130">を宣言できますが、他のコードは、最も内側の名前空間で宣言された要素にアクセスするときに、入れ子の階層内のすべての名前空間名を含む修飾文字列を使用する必要があることに注意してください。 入れ子のレベルに厳密な制限はありません。</span><span class="sxs-lookup"><span data-stu-id="46fc7-130">There is no strict limit to the levels of nesting you can declare, but remember that when other code accesses the elements declared in the innermost namespace, it must use a qualification string that contains all the namespace names in the nesting hierarchy.</span></span>  
  
## <a name="access-level"></a><span data-ttu-id="46fc7-131">アクセス レベル</span><span class="sxs-lookup"><span data-stu-id="46fc7-131">Access Level</span></span>  
 <span data-ttu-id="46fc7-132">名前空間として扱われますがある、`Public`アクセス レベル。</span><span class="sxs-lookup"><span data-stu-id="46fc7-132">Namespaces are treated as if they have a `Public` access level.</span></span> <span data-ttu-id="46fc7-133">名前空間は、同じプロジェクト内、プロジェクトを参照する他のプロジェクトおよびプロジェクトからビルドされたアセンブリにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="46fc7-133">A namespace can be accessed from code anywhere in the same project, from other projects that reference the project, and from any assembly built from the project.</span></span>  
  
 <span data-ttu-id="46fc7-134">つまり、名前空間内の他の任意の要素内部ではなく、名前空間レベルで宣言されたプログラミング要素が`Public`または`Friend`アクセスします。</span><span class="sxs-lookup"><span data-stu-id="46fc7-134">Programming elements declared at namespace level, meaning in a namespace but not inside any other element, can have `Public` or `Friend` access.</span></span> <span data-ttu-id="46fc7-135">このようなアクセス レベルの要素を使用して指定しない場合、`Friend`既定。</span><span class="sxs-lookup"><span data-stu-id="46fc7-135">If unspecified, the access level of such an element uses `Friend` by default.</span></span> <span data-ttu-id="46fc7-136">要素名前空間レベルで宣言するにはには、クラス、構造体、モジュール、インターフェイス、列挙型、およびデリゲートが含まれます。</span><span class="sxs-lookup"><span data-stu-id="46fc7-136">Elements you can declare at namespace level include classes, structures, modules, interfaces, enumerations, and delegates.</span></span> <span data-ttu-id="46fc7-137">詳細については、「[宣言コンテキストと既定のアクセス レベル](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="46fc7-137">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
## <a name="root-namespace"></a><span data-ttu-id="46fc7-138">ルート Namespace</span><span class="sxs-lookup"><span data-stu-id="46fc7-138">Root Namespace</span></span>  
 <span data-ttu-id="46fc7-139">プロジェクト内のすべての名前空間名がに基づいて、*ルート名前空間*します。</span><span class="sxs-lookup"><span data-stu-id="46fc7-139">All namespace names in your project are based on a *root namespace*.</span></span> <span data-ttu-id="46fc7-140">Visual Studio では、プロジェクト内のすべてのコードで、既定のルート名前空間としてプロジェクト名が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="46fc7-140">Visual Studio assigns your project name as the default root namespace for all code in your project.</span></span> <span data-ttu-id="46fc7-141">たとえば、プロジェクト名が `Payroll`である場合、そのプログラミング要素は `Payroll`名前空間に属します。</span><span class="sxs-lookup"><span data-stu-id="46fc7-141">For example, if your project is named `Payroll`, its programming elements belong to namespace `Payroll`.</span></span> <span data-ttu-id="46fc7-142">宣言する場合`Namespace funding`、その名前空間の完全名は`Payroll.funding`します。</span><span class="sxs-lookup"><span data-stu-id="46fc7-142">If you declare `Namespace funding`, the full name of that namespace is `Payroll.funding`.</span></span>  
  
 <span data-ttu-id="46fc7-143">既存の名前空間を指定する場合、`Namespace`ステートメントなど、ジェネリック リスト クラスの例では、null 値に、ルート名前空間を設定できます。</span><span class="sxs-lookup"><span data-stu-id="46fc7-143">If you want to specify an existing namespace in a `Namespace` statement, such as in the generic list class example, you can set your root namespace to a null value.</span></span> <span data-ttu-id="46fc7-144">これを行うには、次のようにクリックします。**プロジェクト プロパティ**から、**プロジェクト**メニューと、消去、**ルート名前空間**エントリ、ボックスは空にします。</span><span class="sxs-lookup"><span data-stu-id="46fc7-144">To do this, click **Project Properties** from the **Project** menu and then clear the **Root namespace** entry so that the box is empty.</span></span> <span data-ttu-id="46fc7-145">ジェネリック リスト クラスの例ではこれを実行している場合、Visual Basic コンパイラが行う`System.Collections.Generic`プロジェクト内の新しい名前空間として`Payroll`の完全な名前を持つ`Payroll.System.Collections.Generic`します。</span><span class="sxs-lookup"><span data-stu-id="46fc7-145">If you did not do this in the generic list class example, the Visual Basic compiler would take `System.Collections.Generic` as a new namespace within project `Payroll`, with the full name of `Payroll.System.Collections.Generic`.</span></span>  
  
 <span data-ttu-id="46fc7-146">また、使用することができます、`Global`キーワードをプロジェクトの外部で定義された名前空間の要素を参照してください。</span><span class="sxs-lookup"><span data-stu-id="46fc7-146">Alternatively, you can use the `Global` keyword to refer to elements of namespaces defined outside your project.</span></span> <span data-ttu-id="46fc7-147">そうには、ルート名前空間としてプロジェクト名を保持することができます。</span><span class="sxs-lookup"><span data-stu-id="46fc7-147">Doing so lets you retain your project name as the root namespace.</span></span> <span data-ttu-id="46fc7-148">これにより、意図せずと共に既存の名前空間のプログラミング要素にマージされる可能性が減少します。</span><span class="sxs-lookup"><span data-stu-id="46fc7-148">This reduces the chance of unintentionally merging your programming elements together with those of existing namespaces.</span></span> <span data-ttu-id="46fc7-149">詳細については、「グローバル キーワードで完全修飾名」のセクションを参照してください。 [Visual Basic における名前空間](../../../visual-basic/programming-guide/program-structure/namespaces.md)します。</span><span class="sxs-lookup"><span data-stu-id="46fc7-149">For more information, see the "Global Keyword in Fully Qualified Names" section in [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md).</span></span>  
  
 <span data-ttu-id="46fc7-150">`Global` Namespace ステートメントでキーワードを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="46fc7-150">The `Global` keyword can also be used in a Namespace statement.</span></span> <span data-ttu-id="46fc7-151">これにより、プロジェクトのルート名前空間から名前空間を定義できます。</span><span class="sxs-lookup"><span data-stu-id="46fc7-151">This lets you define a namespace out of the root namespace of your project.</span></span> <span data-ttu-id="46fc7-152">詳細については、「グローバル キーワードに Namespace ステートメント」セクションを参照してください。 [Visual Basic における名前空間](../../../visual-basic/programming-guide/program-structure/namespaces.md)します。</span><span class="sxs-lookup"><span data-stu-id="46fc7-152">For more information, see the "Global Keyword in Namespace Statements" section in [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md).</span></span>  
  
 <span data-ttu-id="46fc7-153">**トラブルシューティングします。**</span><span class="sxs-lookup"><span data-stu-id="46fc7-153">**Troubleshooting.**</span></span> <span data-ttu-id="46fc7-154">ルート名前空間には、名前空間名の連結されたもので予期しないことがあります。</span><span class="sxs-lookup"><span data-stu-id="46fc7-154">The root namespace can lead to unexpected concatenations of namespace names.</span></span> <span data-ttu-id="46fc7-155">プロジェクトの外部で定義されている名前空間への参照を作成する場合、Visual Basic コンパイラとして解釈ルート名前空間内の入れ子になった名前空間。</span><span class="sxs-lookup"><span data-stu-id="46fc7-155">If you make reference to namespaces defined outside your project, the Visual Basic compiler can construe them as nested namespaces in the root namespace.</span></span> <span data-ttu-id="46fc7-156">このような場合は、コンパイラは、外部の名前空間で既に定義されているすべての型を認識しません。</span><span class="sxs-lookup"><span data-stu-id="46fc7-156">In such a case, the compiler does not recognize any types that have been already defined in the external namespaces.</span></span> <span data-ttu-id="46fc7-157">これを回避するには、設定、ルート名前空間"Root Namespace"で説明されていると null 値にするかを使用して、`Global`外部名前空間の要素にアクセスするキーワード。</span><span class="sxs-lookup"><span data-stu-id="46fc7-157">To avoid this, either set your root namespace to a null value as described in "Root Namespace," or use the `Global` keyword to access elements of external namespaces.</span></span>  
  
## <a name="attributes-and-modifiers"></a><span data-ttu-id="46fc7-158">属性と修飾子</span><span class="sxs-lookup"><span data-stu-id="46fc7-158">Attributes and Modifiers</span></span>  
 <span data-ttu-id="46fc7-159">名前空間には、属性を適用することはできません。</span><span class="sxs-lookup"><span data-stu-id="46fc7-159">You cannot apply attributes to a namespace.</span></span> <span data-ttu-id="46fc7-160">属性は、名前空間などのソースの分類器の意味はないアセンブリのメタデータに情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="46fc7-160">An attribute contributes information to the assembly's metadata, which is not meaningful for source classifiers such as namespaces.</span></span>  
  
 <span data-ttu-id="46fc7-161">名前空間には、すべてのアクセスまたはプロシージャ修飾子、またはその他の修飾子を適用できません。</span><span class="sxs-lookup"><span data-stu-id="46fc7-161">You cannot apply any access or procedure modifiers, or any other modifiers, to a namespace.</span></span> <span data-ttu-id="46fc7-162">型ではないためこれらの修飾子は意味がありません。</span><span class="sxs-lookup"><span data-stu-id="46fc7-162">Because it is not a type, these modifiers are not meaningful.</span></span>  
  
## <a name="example"></a><span data-ttu-id="46fc7-163">例</span><span class="sxs-lookup"><span data-stu-id="46fc7-163">Example</span></span>  
 <span data-ttu-id="46fc7-164">次の例では、もう一方の入れ子になった 2 つの名前空間を宣言します。</span><span class="sxs-lookup"><span data-stu-id="46fc7-164">The following example declares two namespaces, one nested in the other.</span></span>  
  
 [!code-vb[VbVbalrStatements#43](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#43)]  
  
## <a name="example"></a><span data-ttu-id="46fc7-165">例</span><span class="sxs-lookup"><span data-stu-id="46fc7-165">Example</span></span>  
 <span data-ttu-id="46fc7-166">次の例は、1 つの行に複数の入れ子になった名前空間を宣言し、これは、前の例に相当します。</span><span class="sxs-lookup"><span data-stu-id="46fc7-166">The following example declares multiple nested namespaces on a single line, and it is equivalent to the previous example.</span></span>  
  
 [!code-vb[VbVbalrStatements#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#41)]  
  
## <a name="example"></a><span data-ttu-id="46fc7-167">例</span><span class="sxs-lookup"><span data-stu-id="46fc7-167">Example</span></span>  
 <span data-ttu-id="46fc7-168">次の例では、前の例で定義されたクラスにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="46fc7-168">The following example accesses the class defined in the previous examples.</span></span>  
  
 [!code-vb[VbVbalrStatements#42](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#42)]  
  
## <a name="example"></a><span data-ttu-id="46fc7-169">例</span><span class="sxs-lookup"><span data-stu-id="46fc7-169">Example</span></span>  
 <span data-ttu-id="46fc7-170">次の例は、新しいジェネリック リスト クラスのスケルトンを定義しに追加します、<xref:System.Collections.Generic?displayProperty=nameWithType>名前空間。</span><span class="sxs-lookup"><span data-stu-id="46fc7-170">The following example defines the skeleton of a new generic list class and adds it to the <xref:System.Collections.Generic?displayProperty=nameWithType> namespace.</span></span>  
  
```vb  
Namespace System.Collections.Generic  
    Class specialSortedList(Of T)  
        Inherits List(Of T)  
        ' Insert code to define the special generic list class.  
    End Class  
End Namespace  
```  
  
## <a name="see-also"></a><span data-ttu-id="46fc7-171">関連項目</span><span class="sxs-lookup"><span data-stu-id="46fc7-171">See also</span></span>

- [<span data-ttu-id="46fc7-172">Imports ステートメント (.NET 名前空間および型)</span><span class="sxs-lookup"><span data-stu-id="46fc7-172">Imports Statement (.NET Namespace and Type)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [<span data-ttu-id="46fc7-173">Declared Element Names</span><span class="sxs-lookup"><span data-stu-id="46fc7-173">Declared Element Names</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="46fc7-174">Visual Basic における名前空間</span><span class="sxs-lookup"><span data-stu-id="46fc7-174">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)
