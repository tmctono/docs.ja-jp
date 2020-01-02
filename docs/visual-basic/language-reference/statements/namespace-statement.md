---
title: Namespace ステートメント
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
ms.openlocfilehash: 19207a42890640bd82ec547e53eb6d833668e4b5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74329644"
---
# <a name="namespace-statement"></a><span data-ttu-id="2f6c8-102">Namespace ステートメント</span><span class="sxs-lookup"><span data-stu-id="2f6c8-102">Namespace Statement</span></span>
<span data-ttu-id="2f6c8-103">名前空間の名前を宣言し、宣言に続くソースコードがその名前空間内でコンパイルされるようにします。</span><span class="sxs-lookup"><span data-stu-id="2f6c8-103">Declares the name of a namespace and causes the source code that follows the declaration to be compiled within that namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f6c8-104">構文</span><span class="sxs-lookup"><span data-stu-id="2f6c8-104">Syntax</span></span>  
  
```vb  
Namespace [Global.] { name | name.name }  
    [ componenttypes ]  
End Namespace  
```  
  
## <a name="parts"></a><span data-ttu-id="2f6c8-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="2f6c8-105">Parts</span></span>  
 <span data-ttu-id="2f6c8-106">グローバル</span><span class="sxs-lookup"><span data-stu-id="2f6c8-106">Global</span></span>  
 <span data-ttu-id="2f6c8-107">省略可。</span><span class="sxs-lookup"><span data-stu-id="2f6c8-107">Optional.</span></span> <span data-ttu-id="2f6c8-108">では、プロジェクトのルート名前空間から名前空間を定義できます。</span><span class="sxs-lookup"><span data-stu-id="2f6c8-108">Allows you to define a namespace out of the root namespace of your project.</span></span> <span data-ttu-id="2f6c8-109">[Visual Basic における名前空間](../../../visual-basic/programming-guide/program-structure/namespaces.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f6c8-109">See [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md).</span></span>  
  
 `name`  
 <span data-ttu-id="2f6c8-110">必須。</span><span class="sxs-lookup"><span data-stu-id="2f6c8-110">Required.</span></span> <span data-ttu-id="2f6c8-111">名前空間を識別する一意の名前。</span><span class="sxs-lookup"><span data-stu-id="2f6c8-111">A unique name that identifies the namespace.</span></span> <span data-ttu-id="2f6c8-112">有効な Visual Basic 識別子である必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f6c8-112">Must be a valid Visual Basic identifier.</span></span> <span data-ttu-id="2f6c8-113">詳細については、[宣言された要素の名前](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f6c8-113">For more information, see [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
 `componenttypes`  
 <span data-ttu-id="2f6c8-114">省略可。</span><span class="sxs-lookup"><span data-stu-id="2f6c8-114">Optional.</span></span> <span data-ttu-id="2f6c8-115">名前空間を構成する要素。</span><span class="sxs-lookup"><span data-stu-id="2f6c8-115">Elements that make up the namespace.</span></span> <span data-ttu-id="2f6c8-116">これらには、列挙体、構造体、インターフェイス、クラス、モジュール、デリゲート、およびその他の名前空間が含まれますが、これらに限定されるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="2f6c8-116">These include, but are not limited to, enumerations, structures, interfaces, classes, modules, delegates, and other namespaces.</span></span>  
  
 `End Namespace`  
 <span data-ttu-id="2f6c8-117">`Namespace` ブロックを終了します。</span><span class="sxs-lookup"><span data-stu-id="2f6c8-117">Terminates a `Namespace` block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2f6c8-118">コメント</span><span class="sxs-lookup"><span data-stu-id="2f6c8-118">Remarks</span></span>  
 <span data-ttu-id="2f6c8-119">名前空間は、組織のシステムとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="2f6c8-119">Namespaces are used as an organizational system.</span></span> <span data-ttu-id="2f6c8-120">これらのクラスは、他のプログラムやアプリケーションに公開されているプログラミング要素を分類して提示する手段を提供します。</span><span class="sxs-lookup"><span data-stu-id="2f6c8-120">They provide a way to classify and present programming elements that are exposed to other programs and applications.</span></span> <span data-ttu-id="2f6c8-121">名前空間は、クラスまたは構造体が意味を持つ*型*ではないことに注意してください。名前空間のデータ型を持つプログラミング要素を宣言することはできません。</span><span class="sxs-lookup"><span data-stu-id="2f6c8-121">Note that a namespace is not a *type* in the sense that a class or structure is—you cannot declare a programming element to have the data type of a namespace.</span></span>  
  
 <span data-ttu-id="2f6c8-122">`Namespace` ステートメントの後で宣言されたすべてのプログラミング要素は、その名前空間に属します。</span><span class="sxs-lookup"><span data-stu-id="2f6c8-122">All programming elements declared after a `Namespace` statement belong to that namespace.</span></span> <span data-ttu-id="2f6c8-123">Visual Basic は、`End Namespace` ステートメントまたは別の `Namespace` ステートメントが検出されるまで、最後に宣言された名前空間に要素をコンパイルし続けます。</span><span class="sxs-lookup"><span data-stu-id="2f6c8-123">Visual Basic continues to compile elements into the last declared namespace until it encounters either an `End Namespace` statement or another `Namespace` statement.</span></span>  
  
 <span data-ttu-id="2f6c8-124">名前空間が既に定義されている場合は、プロジェクトの外部でも、プログラミング要素を追加できます。</span><span class="sxs-lookup"><span data-stu-id="2f6c8-124">If a namespace is already defined, even outside your project, you can add programming elements to it.</span></span> <span data-ttu-id="2f6c8-125">これを行うには、`Namespace` ステートメントを使用して Visual Basic を、その名前空間に要素をコンパイルするように指示します。</span><span class="sxs-lookup"><span data-stu-id="2f6c8-125">To do this, you use a `Namespace` statement to direct Visual Basic to compile elements into that namespace.</span></span>  
  
 <span data-ttu-id="2f6c8-126">`Namespace` ステートメントは、ファイルまたは名前空間レベルでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="2f6c8-126">You can use a `Namespace` statement only at the file or namespace level.</span></span> <span data-ttu-id="2f6c8-127">つまり、名前空間の*宣言コンテキスト*は、ソースファイルまたは別の名前空間である必要があり、クラス、構造体、モジュール、インターフェイス、またはプロシージャにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="2f6c8-127">This means the *declaration context* for a namespace must be a source file or another namespace, and cannot be a class, structure, module, interface, or procedure.</span></span> <span data-ttu-id="2f6c8-128">詳細については、「[宣言コンテキストと既定のアクセス レベル](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f6c8-128">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="2f6c8-129">1つの名前空間を別の名前空間内で宣言できます。</span><span class="sxs-lookup"><span data-stu-id="2f6c8-129">You can declare one namespace within another.</span></span> <span data-ttu-id="2f6c8-130">宣言できる入れ子のレベルに厳密な制限はありませんが、最も内側の名前空間で宣言されている要素に他のコードがアクセスする場合は、入れ子階層内のすべての名前空間名を含む修飾文字列を使用する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="2f6c8-130">There is no strict limit to the levels of nesting you can declare, but remember that when other code accesses the elements declared in the innermost namespace, it must use a qualification string that contains all the namespace names in the nesting hierarchy.</span></span>  
  
## <a name="access-level"></a><span data-ttu-id="2f6c8-131">アクセスレベル</span><span class="sxs-lookup"><span data-stu-id="2f6c8-131">Access Level</span></span>  
 <span data-ttu-id="2f6c8-132">名前空間は、`Public` アクセスレベルがあるかのように扱われます。</span><span class="sxs-lookup"><span data-stu-id="2f6c8-132">Namespaces are treated as if they have a `Public` access level.</span></span> <span data-ttu-id="2f6c8-133">名前空間には、同じプロジェクト内の任意の場所のコード、プロジェクトを参照する他のプロジェクト、およびプロジェクトからビルドされた任意のアセンブリからアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="2f6c8-133">A namespace can be accessed from code anywhere in the same project, from other projects that reference the project, and from any assembly built from the project.</span></span>  
  
 <span data-ttu-id="2f6c8-134">名前空間レベルで宣言され、他の要素の内部には存在しないプログラミング要素は、`Public` または `Friend` アクセスを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="2f6c8-134">Programming elements declared at namespace level, meaning in a namespace but not inside any other element, can have `Public` or `Friend` access.</span></span> <span data-ttu-id="2f6c8-135">指定されていない場合、このような要素のアクセスレベルは既定で `Friend` を使用します。</span><span class="sxs-lookup"><span data-stu-id="2f6c8-135">If unspecified, the access level of such an element uses `Friend` by default.</span></span> <span data-ttu-id="2f6c8-136">名前空間レベルで宣言できる要素には、クラス、構造体、モジュール、インターフェイス、列挙型、およびデリゲートが含まれます。</span><span class="sxs-lookup"><span data-stu-id="2f6c8-136">Elements you can declare at namespace level include classes, structures, modules, interfaces, enumerations, and delegates.</span></span> <span data-ttu-id="2f6c8-137">詳細については、「[宣言コンテキストと既定のアクセス レベル](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f6c8-137">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
## <a name="root-namespace"></a><span data-ttu-id="2f6c8-138">ルート名前空間</span><span class="sxs-lookup"><span data-stu-id="2f6c8-138">Root Namespace</span></span>  
 <span data-ttu-id="2f6c8-139">プロジェクト内のすべての名前空間名は、*ルート名前空間*に基づいています。</span><span class="sxs-lookup"><span data-stu-id="2f6c8-139">All namespace names in your project are based on a *root namespace*.</span></span> <span data-ttu-id="2f6c8-140">Visual Studio では、プロジェクト内のすべてのコードで、既定のルート名前空間としてプロジェクト名が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="2f6c8-140">Visual Studio assigns your project name as the default root namespace for all code in your project.</span></span> <span data-ttu-id="2f6c8-141">たとえば、プロジェクト名が `Payroll`である場合、そのプログラミング要素は `Payroll`名前空間に属します。</span><span class="sxs-lookup"><span data-stu-id="2f6c8-141">For example, if your project is named `Payroll`, its programming elements belong to namespace `Payroll`.</span></span> <span data-ttu-id="2f6c8-142">`Namespace funding`を宣言すると、その名前空間の完全な名前が `Payroll.funding`ます。</span><span class="sxs-lookup"><span data-stu-id="2f6c8-142">If you declare `Namespace funding`, the full name of that namespace is `Payroll.funding`.</span></span>  
  
 <span data-ttu-id="2f6c8-143">ジェネリックリストクラスの例のように、`Namespace` ステートメントで既存の名前空間を指定する場合は、ルート名前空間を null 値に設定できます。</span><span class="sxs-lookup"><span data-stu-id="2f6c8-143">If you want to specify an existing namespace in a `Namespace` statement, such as in the generic list class example, you can set your root namespace to a null value.</span></span> <span data-ttu-id="2f6c8-144">これを行うには、 **[プロジェクト]** メニューの **[プロジェクトのプロパティ]** をクリックし、 **[ルート名前空間]** エントリをオフにして、ボックスが空になるようにします。</span><span class="sxs-lookup"><span data-stu-id="2f6c8-144">To do this, click **Project Properties** from the **Project** menu and then clear the **Root namespace** entry so that the box is empty.</span></span> <span data-ttu-id="2f6c8-145">ジェネリックリストクラスの例でこれを実行しなかった場合、Visual Basic コンパイラは、プロジェクト `Payroll`内の新しい名前空間として `System.Collections.Generic` します。完全な名前は `Payroll.System.Collections.Generic`です。</span><span class="sxs-lookup"><span data-stu-id="2f6c8-145">If you did not do this in the generic list class example, the Visual Basic compiler would take `System.Collections.Generic` as a new namespace within project `Payroll`, with the full name of `Payroll.System.Collections.Generic`.</span></span>  
  
 <span data-ttu-id="2f6c8-146">または、`Global` キーワードを使用して、プロジェクトの外部で定義されている名前空間の要素を参照することもできます。</span><span class="sxs-lookup"><span data-stu-id="2f6c8-146">Alternatively, you can use the `Global` keyword to refer to elements of namespaces defined outside your project.</span></span> <span data-ttu-id="2f6c8-147">そうすることで、プロジェクト名をルート名前空間として保持できます。</span><span class="sxs-lookup"><span data-stu-id="2f6c8-147">Doing so lets you retain your project name as the root namespace.</span></span> <span data-ttu-id="2f6c8-148">これにより、プログラミング要素を既存の名前空間のものと誤ってマージする可能性が低くなります。</span><span class="sxs-lookup"><span data-stu-id="2f6c8-148">This reduces the chance of unintentionally merging your programming elements together with those of existing namespaces.</span></span> <span data-ttu-id="2f6c8-149">詳細については、「[Visual Basic における名前空間](../../../visual-basic/programming-guide/program-structure/namespaces.md)」の「完全修飾名の Global キーワード」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f6c8-149">For more information, see the "Global Keyword in Fully Qualified Names" section in [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md).</span></span>  
  
 <span data-ttu-id="2f6c8-150">`Global` キーワードは、Namespace ステートメントでも使用できます。</span><span class="sxs-lookup"><span data-stu-id="2f6c8-150">The `Global` keyword can also be used in a Namespace statement.</span></span> <span data-ttu-id="2f6c8-151">これにより、プロジェクトのルート名前空間から名前空間を定義できます。</span><span class="sxs-lookup"><span data-stu-id="2f6c8-151">This lets you define a namespace out of the root namespace of your project.</span></span> <span data-ttu-id="2f6c8-152">詳細については、「[Visual Basic における名前空間](../../../visual-basic/programming-guide/program-structure/namespaces.md)」の「名前空間のステートメントでの Global キーワード」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f6c8-152">For more information, see the "Global Keyword in Namespace Statements" section in [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md).</span></span>  
  
 <span data-ttu-id="2f6c8-153">**行う.**</span><span class="sxs-lookup"><span data-stu-id="2f6c8-153">**Troubleshooting.**</span></span> <span data-ttu-id="2f6c8-154">ルート名前空間は、名前空間名の予期しない連結につながる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2f6c8-154">The root namespace can lead to unexpected concatenations of namespace names.</span></span> <span data-ttu-id="2f6c8-155">プロジェクトの外部で定義されている名前空間への参照を作成した場合、Visual Basic コンパイラは、ルート名前空間の入れ子になった名前空間としてそれらを construe できます。</span><span class="sxs-lookup"><span data-stu-id="2f6c8-155">If you make reference to namespaces defined outside your project, the Visual Basic compiler can construe them as nested namespaces in the root namespace.</span></span> <span data-ttu-id="2f6c8-156">このような場合、コンパイラは、外部名前空間で既に定義されている型を認識しません。</span><span class="sxs-lookup"><span data-stu-id="2f6c8-156">In such a case, the compiler does not recognize any types that have been already defined in the external namespaces.</span></span> <span data-ttu-id="2f6c8-157">これを回避するには、「ルート名前空間」で説明されているようにルート名前空間を null 値に設定するか、`Global` キーワードを使用して外部名前空間の要素にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="2f6c8-157">To avoid this, either set your root namespace to a null value as described in "Root Namespace," or use the `Global` keyword to access elements of external namespaces.</span></span>  
  
## <a name="attributes-and-modifiers"></a><span data-ttu-id="2f6c8-158">属性と修飾子</span><span class="sxs-lookup"><span data-stu-id="2f6c8-158">Attributes and Modifiers</span></span>  
 <span data-ttu-id="2f6c8-159">名前空間に属性を適用することはできません。</span><span class="sxs-lookup"><span data-stu-id="2f6c8-159">You cannot apply attributes to a namespace.</span></span> <span data-ttu-id="2f6c8-160">属性は、アセンブリのメタデータに情報を提供します。これは、名前空間などのソース分類子には意味がありません。</span><span class="sxs-lookup"><span data-stu-id="2f6c8-160">An attribute contributes information to the assembly's metadata, which is not meaningful for source classifiers such as namespaces.</span></span>  
  
 <span data-ttu-id="2f6c8-161">アクセス修飾子またはプロシージャ修飾子、またはその他の修飾子を名前空間に適用することはできません。</span><span class="sxs-lookup"><span data-stu-id="2f6c8-161">You cannot apply any access or procedure modifiers, or any other modifiers, to a namespace.</span></span> <span data-ttu-id="2f6c8-162">型ではないため、これらの修飾子は意味がありません。</span><span class="sxs-lookup"><span data-stu-id="2f6c8-162">Because it is not a type, these modifiers are not meaningful.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2f6c8-163">例</span><span class="sxs-lookup"><span data-stu-id="2f6c8-163">Example</span></span>  
 <span data-ttu-id="2f6c8-164">次の例では、2つの名前空間を宣言します。1つは他方に入れ子になっています。</span><span class="sxs-lookup"><span data-stu-id="2f6c8-164">The following example declares two namespaces, one nested in the other.</span></span>  
  
 [!code-vb[VbVbalrStatements#43](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#43)]  
  
## <a name="example"></a><span data-ttu-id="2f6c8-165">例</span><span class="sxs-lookup"><span data-stu-id="2f6c8-165">Example</span></span>  
 <span data-ttu-id="2f6c8-166">次の例では、1行に複数の入れ子になった名前空間を宣言しています。これは前の例と同じです。</span><span class="sxs-lookup"><span data-stu-id="2f6c8-166">The following example declares multiple nested namespaces on a single line, and it is equivalent to the previous example.</span></span>  
  
 [!code-vb[VbVbalrStatements#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#41)]  
  
## <a name="example"></a><span data-ttu-id="2f6c8-167">例</span><span class="sxs-lookup"><span data-stu-id="2f6c8-167">Example</span></span>  
 <span data-ttu-id="2f6c8-168">次の例では、前の例で定義したクラスにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="2f6c8-168">The following example accesses the class defined in the previous examples.</span></span>  
  
 [!code-vb[VbVbalrStatements#42](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#42)]  
  
## <a name="example"></a><span data-ttu-id="2f6c8-169">例</span><span class="sxs-lookup"><span data-stu-id="2f6c8-169">Example</span></span>  
 <span data-ttu-id="2f6c8-170">次の例では、新しいジェネリックリストクラスのスケルトンを定義し、それを <xref:System.Collections.Generic?displayProperty=nameWithType> 名前空間に追加します。</span><span class="sxs-lookup"><span data-stu-id="2f6c8-170">The following example defines the skeleton of a new generic list class and adds it to the <xref:System.Collections.Generic?displayProperty=nameWithType> namespace.</span></span>  
  
```vb  
Namespace System.Collections.Generic  
    Class specialSortedList(Of T)  
        Inherits List(Of T)  
        ' Insert code to define the special generic list class.  
    End Class  
End Namespace  
```  
  
## <a name="see-also"></a><span data-ttu-id="2f6c8-171">参照</span><span class="sxs-lookup"><span data-stu-id="2f6c8-171">See also</span></span>

- [<span data-ttu-id="2f6c8-172">Imports ステートメント (.NET 名前空間および型)</span><span class="sxs-lookup"><span data-stu-id="2f6c8-172">Imports Statement (.NET Namespace and Type)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [<span data-ttu-id="2f6c8-173">宣言された要素の名前</span><span class="sxs-lookup"><span data-stu-id="2f6c8-173">Declared Element Names</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="2f6c8-174">Visual Basic における名前空間</span><span class="sxs-lookup"><span data-stu-id="2f6c8-174">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)
