---
title: 名前空間
ms.date: 07/20/2015
f1_keywords:
- vb.global
helpviewer_keywords:
- assemblies [Visual Basic], namespaces
- name collisions
- Global keyword [Visual Basic]
- namespace pollution
- names [Visual Basic], avoiding conflicts
- naming conflicts [Visual Basic], namespaces
- namespaces [Visual Basic], assemblies
- Visual Basic code, namespaces
- fully qualified names [Visual Basic]
- naming conventions [Visual Basic], naming conflicts
- namespaces
ms.assetid: cffac744-ab8c-4f1f-ba50-732c22ab4b88
ms.openlocfilehash: ec892167f30a7ded739dc188ab4096cb3a5d154c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347331"
---
# <a name="namespaces-in-visual-basic"></a><span data-ttu-id="24df0-102">Visual Basic における名前空間</span><span class="sxs-lookup"><span data-stu-id="24df0-102">Namespaces in Visual Basic</span></span>
<span data-ttu-id="24df0-103">アセンブリ内で定義されているオブジェクトは、名前空間によって編成されています。</span><span class="sxs-lookup"><span data-stu-id="24df0-103">Namespaces organize the objects defined in an assembly.</span></span> <span data-ttu-id="24df0-104">アセンブリには複数の名前空間を含めることができます。さらに、名前空間の中に他の名前空間を含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="24df0-104">Assemblies can contain multiple namespaces, which can in turn contain other namespaces.</span></span> <span data-ttu-id="24df0-105">名前空間を使用するとあいまいさがなくなるため、クラス ライブラリを使用する場合など、多数のオブジェクトを使用する場合に参照が簡単になります。</span><span class="sxs-lookup"><span data-stu-id="24df0-105">Namespaces prevent ambiguity and simplify references when using large groups of objects such as class libraries.</span></span>  
  
 <span data-ttu-id="24df0-106">For example, the .NET Framework defines the <xref:System.Windows.Forms.ListBox> class in the <xref:System.Windows.Forms?displayProperty=nameWithType> namespace.</span><span class="sxs-lookup"><span data-stu-id="24df0-106">For example, the .NET Framework defines the <xref:System.Windows.Forms.ListBox> class in the <xref:System.Windows.Forms?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="24df0-107">次のコードは、このクラスの完全修飾名を使用して変数を宣言する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="24df0-107">The following code fragment shows how to declare a variable using the fully qualified name for this class:</span></span>  
  
 [!code-vb[VbVbalrApplication#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#6)]  
  
## <a name="avoiding-name-collisions"></a><span data-ttu-id="24df0-108">名前の競合の回避</span><span class="sxs-lookup"><span data-stu-id="24df0-108">Avoiding Name Collisions</span></span>  
 <span data-ttu-id="24df0-109">.NET Framework namespaces address a problem sometimes called *namespace pollution*, in which the developer of a class library is hampered by the use of similar names in another library.</span><span class="sxs-lookup"><span data-stu-id="24df0-109">.NET Framework namespaces address a problem sometimes called *namespace pollution*, in which the developer of a class library is hampered by the use of similar names in another library.</span></span> <span data-ttu-id="24df0-110">このような既存コンポーネントとの競合は、 *名前の競合*とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="24df0-110">These conflicts with existing components are sometimes called *name collisions*.</span></span>  
  
 <span data-ttu-id="24df0-111">たとえば、 `ListBox`という名前の新しいクラスを作成した場合、プロジェクト内ではこのクラスを修飾子を付けずに使用できます。</span><span class="sxs-lookup"><span data-stu-id="24df0-111">For example, if you create a new class named `ListBox`, you can use it inside your project without qualification.</span></span> <span data-ttu-id="24df0-112">However, if you want to use the .NET Framework <xref:System.Windows.Forms.ListBox> class in the same project, you must use a fully qualified reference to make the reference unique.</span><span class="sxs-lookup"><span data-stu-id="24df0-112">However, if you want to use the .NET Framework <xref:System.Windows.Forms.ListBox> class in the same project, you must use a fully qualified reference to make the reference unique.</span></span> <span data-ttu-id="24df0-113">If the reference is not unique, Visual Basic produces an error stating that the name is ambiguous.</span><span class="sxs-lookup"><span data-stu-id="24df0-113">If the reference is not unique, Visual Basic produces an error stating that the name is ambiguous.</span></span> <span data-ttu-id="24df0-114">次のコード例では、これらのオブジェクトを宣言する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="24df0-114">The following code example demonstrates how to declare these objects:</span></span>  
  
 [!code-vb[VbVbalrApplication#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#7)]  
  
 <span data-ttu-id="24df0-115">The following illustration shows two namespace hierarchies, both containing an object named `ListBox`:</span><span class="sxs-lookup"><span data-stu-id="24df0-115">The following illustration shows two namespace hierarchies, both containing an object named `ListBox`:</span></span>  
  
 ![Screenshot that shows two namespace hierarchies.](./media/namespaces/visual-basic-namespace-hierarchy.gif)  
  
 <span data-ttu-id="24df0-117">By default, every executable file you create with Visual Basic contains a namespace with the same name as your project.</span><span class="sxs-lookup"><span data-stu-id="24df0-117">By default, every executable file you create with Visual Basic contains a namespace with the same name as your project.</span></span> <span data-ttu-id="24df0-118">たとえば、 `ListBoxProject`という名前のプロジェクト内でオブジェクトを定義した場合、実行可能ファイル ListBoxProject.exe には `ListBoxProject`という名前空間が含まれます。</span><span class="sxs-lookup"><span data-stu-id="24df0-118">For example, if you define an object within a project named `ListBoxProject`, the executable file ListBoxProject.exe contains a namespace called `ListBoxProject`.</span></span>  
  
 <span data-ttu-id="24df0-119">複数のアセンブリで同じ名前空間を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="24df0-119">Multiple assemblies can use the same namespace.</span></span> <span data-ttu-id="24df0-120">Visual Basic treats them as a single set of names.</span><span class="sxs-lookup"><span data-stu-id="24df0-120">Visual Basic treats them as a single set of names.</span></span> <span data-ttu-id="24df0-121">たとえば、 `SomeNameSpace` というアセンブリの `Assemb1`という名前空間のクラスを定義した後に、 `Assemb2`というアセンブリの同じ名前空間のクラスを定義できます。</span><span class="sxs-lookup"><span data-stu-id="24df0-121">For example, you can define classes for a namespace called `SomeNameSpace` in an assembly named `Assemb1`, and define additional classes for the same namespace from an assembly named `Assemb2`.</span></span>  
  
## <a name="fully-qualified-names"></a><span data-ttu-id="24df0-122">完全修飾名</span><span class="sxs-lookup"><span data-stu-id="24df0-122">Fully Qualified Names</span></span>  
 <span data-ttu-id="24df0-123">完全修飾名は、オブジェクトが定義されている名前空間の名前で始まるオブジェクト参照です。</span><span class="sxs-lookup"><span data-stu-id="24df0-123">Fully qualified names are object references that are prefixed with the name of the namespace in which the object is defined.</span></span> <span data-ttu-id="24df0-124">他のプロジェクトで定義されているオブジェクトを使用するには、 **[プロジェクト]** メニューの **[参照の追加]** をクリックしてそのクラスへの参照を作成し、コード内でそのオブジェクトの完全修飾名を使用します。</span><span class="sxs-lookup"><span data-stu-id="24df0-124">You can use objects defined in other projects if you create a reference to the class (by choosing **Add Reference** from the **Project** menu) and then use the fully qualified name for the object in your code.</span></span> <span data-ttu-id="24df0-125">次のコードは、別のプロジェクトの名前空間のオブジェクトを使用して完全修飾名を使用する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="24df0-125">The following code fragment shows how to use the fully qualified name for an object from another project's namespace:</span></span>  
  
 [!code-vb[VbVbalrApplication#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#8)]  
  
 <span data-ttu-id="24df0-126">完全修飾名を使用すると、どのオブジェクトを使用するかをコンパイラが認識できるため、名前の競合を防止できます。</span><span class="sxs-lookup"><span data-stu-id="24df0-126">Fully qualified names prevent naming conflicts because they make it possible for the compiler to determine which object is being used.</span></span> <span data-ttu-id="24df0-127">ただし、名前自体が長くなるため、使いにくくなります。</span><span class="sxs-lookup"><span data-stu-id="24df0-127">However, the names themselves can get long and cumbersome.</span></span> <span data-ttu-id="24df0-128">この問題を回避するには、 `Imports` ステートメントを使って *エイリアス*を定義します。エイリアスとは、完全修飾名の代わりに使用できる短い名前です。</span><span class="sxs-lookup"><span data-stu-id="24df0-128">To get around this, you can use the `Imports` statement to define an *alias*—an abbreviated name you can use in place of a fully qualified name.</span></span> <span data-ttu-id="24df0-129">たとえば、次のコード例では、2 つの完全修飾名に対してエイリアスを作成し、作成したエイリアスを使って 2 つのオブジェクトを定義しています。</span><span class="sxs-lookup"><span data-stu-id="24df0-129">For example, the following code example creates aliases for two fully qualified names, and uses these aliases to define two objects.</span></span>  
  
 [!code-vb[VbVbalrApplication#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#9)]  
  
 [!code-vb[VbVbalrApplication#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#10)]  
  
 <span data-ttu-id="24df0-130">エイリアスを指定せずに `Imports` ステートメントを使用すると、インポートした名前空間のすべての名前を修飾子を付けずに使用できます。ただし、それらの名前がプロジェクト内で一意であることが必要です。</span><span class="sxs-lookup"><span data-stu-id="24df0-130">If you use the `Imports` statement without an alias, you can use all the names in that namespace without qualification, provided they are unique to the project.</span></span> <span data-ttu-id="24df0-131">プロジェクトに、同じ名前の複数の項目を持つ名前空間をインポートする `Imports` ステートメントがある場合は、それらの名前を使用するときに完全修飾名を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="24df0-131">If your project contains `Imports` statements for namespaces that contain items with the same name, you must fully qualify that name when you use it.</span></span> <span data-ttu-id="24df0-132">たとえば、プロジェクトに次の 2 つの `Imports` ステートメントがあるとします。</span><span class="sxs-lookup"><span data-stu-id="24df0-132">Suppose, for example, your project contained the following two `Imports` statements:</span></span>  
  
 [!code-vb[VbVbalrApplication#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#11)]  
  
 <span data-ttu-id="24df0-133">If you attempt to use `Class1` without fully qualifying it, Visual Basic produces an error stating that the name `Class1` is ambiguous.</span><span class="sxs-lookup"><span data-stu-id="24df0-133">If you attempt to use `Class1` without fully qualifying it, Visual Basic produces an error stating that the name `Class1` is ambiguous.</span></span>  
  
## <a name="namespace-level-statements"></a><span data-ttu-id="24df0-134">名前空間レベルのステートメント</span><span class="sxs-lookup"><span data-stu-id="24df0-134">Namespace Level Statements</span></span>  
 <span data-ttu-id="24df0-135">名前空間内では、モジュール、インターフェイス、クラス、デリゲート、列挙体、構造体、他の名前空間などの項目を定義できます。</span><span class="sxs-lookup"><span data-stu-id="24df0-135">Within a namespace, you can define items such as modules, interfaces, classes, delegates, enumerations, structures, and other namespaces.</span></span> <span data-ttu-id="24df0-136">プロパティ、プロシージャ、変数、イベントなどの項目を名前空間のレベルで定義することはできません。</span><span class="sxs-lookup"><span data-stu-id="24df0-136">You cannot define items such as properties, procedures, variables and events at the namespace level.</span></span> <span data-ttu-id="24df0-137">これらの項目は、モジュール、構造体、クラスなどのコンテナー内で宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="24df0-137">These items must be declared within containers such as modules, structures, or classes.</span></span>  
  
## <a name="global-keyword-in-fully-qualified-names"></a><span data-ttu-id="24df0-138">完全修飾名の Global キーワード</span><span class="sxs-lookup"><span data-stu-id="24df0-138">Global Keyword in Fully Qualified Names</span></span>  
 <span data-ttu-id="24df0-139">入れ子になった階層構造の名前空間を定義すると、その階層構造の内部にあるコードが .NET Framework の <xref:System?displayProperty=nameWithType> 名前空間にアクセスできない場合があります。</span><span class="sxs-lookup"><span data-stu-id="24df0-139">If you have defined a nested hierarchy of namespaces, code inside that hierarchy might be blocked from accessing the <xref:System?displayProperty=nameWithType> namespace of the .NET Framework.</span></span> <span data-ttu-id="24df0-140">次の例は、 `SpecialSpace.System` 名前空間から <xref:System?displayProperty=nameWithType>にアクセスできない階層構造を示しています。</span><span class="sxs-lookup"><span data-stu-id="24df0-140">The following example illustrates a hierarchy in which the `SpecialSpace.System` namespace blocks access to <xref:System?displayProperty=nameWithType>.</span></span>  
  
```vb  
Namespace SpecialSpace  
    Namespace System  
        Class abc  
            Function getValue() As System.Int32  
                Dim n As System.Int32  
                Return n  
            End Function  
        End Class  
    End Namespace  
End Namespace  
```  
  
 <span data-ttu-id="24df0-141">この場合、 <xref:System.Int32?displayProperty=nameWithType>に `SpecialSpace.System` が定義されていないため、Visual Basic コンパイラは `Int32`への参照を正しく解決できません。</span><span class="sxs-lookup"><span data-stu-id="24df0-141">As a result, the Visual Basic compiler cannot successfully resolve the reference to <xref:System.Int32?displayProperty=nameWithType>, because `SpecialSpace.System` does not define `Int32`.</span></span> <span data-ttu-id="24df0-142">`Global` キーワードを使用すると、修飾チェーンを .NET Framework クラス ライブラリの最も外側のレベルで開始できます。</span><span class="sxs-lookup"><span data-stu-id="24df0-142">You can use the `Global` keyword to start the qualification chain at the outermost level of the .NET Framework class library.</span></span> <span data-ttu-id="24df0-143">これにより、クラス ライブラリの <xref:System?displayProperty=nameWithType> 名前空間や、その他のあらゆる名前空間を指定できるようになります。</span><span class="sxs-lookup"><span data-stu-id="24df0-143">This allows you to specify the <xref:System?displayProperty=nameWithType> namespace or any other namespace in the class library.</span></span> <span data-ttu-id="24df0-144">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="24df0-144">The following example illustrates this.</span></span>  
  
```vb  
Namespace SpecialSpace  
    Namespace System  
        Class abc  
            Function getValue() As Global.System.Int32  
                Dim n As Global.System.Int32  
                Return n  
            End Function  
        End Class  
    End Namespace  
End Namespace  
```  
  
 <span data-ttu-id="24df0-145">`Global` を使用して、 <xref:Microsoft.VisualBasic?displayProperty=nameWithType>などの他のルート レベルの名前空間、およびプロジェクトに関連する任意の名前空間にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="24df0-145">You can use `Global` to access other root-level namespaces, such as <xref:Microsoft.VisualBasic?displayProperty=nameWithType>, and any namespace associated with your project.</span></span>  
  
## <a name="global-keyword-in-namespace-statements"></a><span data-ttu-id="24df0-146">名前空間のステートメントでの Global キーワード</span><span class="sxs-lookup"><span data-stu-id="24df0-146">Global Keyword in Namespace Statements</span></span>  
 <span data-ttu-id="24df0-147">You can also use the `Global` keyword in a [Namespace Statement](../../../visual-basic/language-reference/statements/namespace-statement.md).</span><span class="sxs-lookup"><span data-stu-id="24df0-147">You can also use the `Global` keyword in a [Namespace Statement](../../../visual-basic/language-reference/statements/namespace-statement.md).</span></span> <span data-ttu-id="24df0-148">これにより、プロジェクトのルート名前空間から名前空間を定義できます。</span><span class="sxs-lookup"><span data-stu-id="24df0-148">This lets you define a namespace out of the root namespace of your project.</span></span>  
  
 <span data-ttu-id="24df0-149">プロジェクト内のすべての名前空間は、プロジェクトのルート名前空間に基づいています。</span><span class="sxs-lookup"><span data-stu-id="24df0-149">All namespaces in your project are based on the root namespace for the project.</span></span>  <span data-ttu-id="24df0-150">Visual Studio では、プロジェクト内のすべてのコードで、既定のルート名前空間としてプロジェクト名が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="24df0-150">Visual Studio assigns your project name as the default root namespace for all code in your project.</span></span> <span data-ttu-id="24df0-151">たとえば、プロジェクト名が `ConsoleApplication1`である場合、そのプログラミング要素は `ConsoleApplication1`名前空間に属します。</span><span class="sxs-lookup"><span data-stu-id="24df0-151">For example, if your project is named `ConsoleApplication1`, its programming elements belong to namespace `ConsoleApplication1`.</span></span> <span data-ttu-id="24df0-152">`Namespace Magnetosphere`を宣言すると、プロジェクトの `Magnetosphere` への参照は `ConsoleApplication1.Magnetosphere`にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="24df0-152">If you declare `Namespace Magnetosphere`, references to `Magnetosphere` in the project will access `ConsoleApplication1.Magnetosphere`.</span></span>  
  
 <span data-ttu-id="24df0-153">次の例では、プロジェクトのルート名前空間から名前空間を宣言するために `Global` キーワードを使用しています。</span><span class="sxs-lookup"><span data-stu-id="24df0-153">The following examples use the `Global` keyword to declare a namespace out of the root namespace for the project.</span></span>  
  
 [!code-vb[VbVbalrApplication#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/module1.vb#22)]  
  
 <span data-ttu-id="24df0-154">名前空間宣言では、 `Global` を別の名前空間に入れ子にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="24df0-154">In a namespace declaration, `Global` cannot be nested in another namespace.</span></span>  
  
 <span data-ttu-id="24df0-155">[Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic) を使用して、プロジェクトの **ルート名前空間** を表示および変更できます。</span><span class="sxs-lookup"><span data-stu-id="24df0-155">You can use the [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic) to view and modify the **Root Namespace** of the project.</span></span>  <span data-ttu-id="24df0-156">新しいプロジェクトの場合、 **ルート名前空間** の既定値は、プロジェクト名です。</span><span class="sxs-lookup"><span data-stu-id="24df0-156">For new projects, the **Root Namespace** defaults to the project name.</span></span> <span data-ttu-id="24df0-157">`Global` を最上位レベルの名前空間にするには、 **ルート名前空間** のエントリを消去して、ボックスを空にします。</span><span class="sxs-lookup"><span data-stu-id="24df0-157">To cause `Global` to be the top-level namespace, you can clear the **Root Namespace** entry so that the box is empty.</span></span> <span data-ttu-id="24df0-158">**ルート名前空間** を消去すると、名前空間の宣言で `Global` キーワードの必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="24df0-158">Clearing **Root Namespace** removes the need for the `Global` keyword in namespace declarations.</span></span>  
  
 <span data-ttu-id="24df0-159">`Namespace` ステートメントで .NET framework の名前空間にもなっている名前を宣言する場合、 `Global` キーワードが完全修飾名で使用されていない場合、.NET Framework 名前空間は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="24df0-159">If a `Namespace` statement declares a name that is also a namespace in the .NET Framework, the .NET Framework namespace becomes unavailable if the `Global` keyword is not used in a fully qualified name.</span></span> <span data-ttu-id="24df0-160">`Global` キーワードを使用せずに、.NET Framework 名前空間へのアクセスを有効にするには、 `Global` キーワードを `Namespace` ステートメントに含めます。</span><span class="sxs-lookup"><span data-stu-id="24df0-160">To enable access to that .NET Framework namespace without using the `Global` keyword, you can include the `Global` keyword in the `Namespace` statement.</span></span>  
  
 <span data-ttu-id="24df0-161">次の例では、 `Global` 名前空間の宣言で、 `System.Text` キーワードを使用しています。</span><span class="sxs-lookup"><span data-stu-id="24df0-161">The following example has the `Global` keyword in the `System.Text` namespace declaration.</span></span>  
  
 <span data-ttu-id="24df0-162">名前空間の宣言に `Global` キーワードが含まれていない場合、 <xref:System.Text.StringBuilder> にアクセスするには、 `Global.System.Text.StringBuilder`を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="24df0-162">If the `Global` keyword was not present in the namespace declaration, <xref:System.Text.StringBuilder> could not be accessed without specifying `Global.System.Text.StringBuilder`.</span></span> <span data-ttu-id="24df0-163">`ConsoleApplication1`という名前のプロジェクトで、 `System.Text` キーワードが使用されていない場合、 `ConsoleApplication1.System.Text` を参照すると、 `Global` にアクセスすることになります。</span><span class="sxs-lookup"><span data-stu-id="24df0-163">For a project named `ConsoleApplication1`, references to `System.Text` would access `ConsoleApplication1.System.Text` if the `Global` keyword was not used.</span></span>  
  
 [!code-vb[VbVbalrApplication#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/module1.vb#21)]  
  
## <a name="see-also"></a><span data-ttu-id="24df0-164">関連項目</span><span class="sxs-lookup"><span data-stu-id="24df0-164">See also</span></span>

- <xref:System.Windows.Forms.ListBox>
- <xref:System.Windows.Forms?displayProperty=nameWithType>
- [<span data-ttu-id="24df0-165">.NET のアセンブリ</span><span class="sxs-lookup"><span data-stu-id="24df0-165">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
- [<span data-ttu-id="24df0-166">参照と Imports ステートメント</span><span class="sxs-lookup"><span data-stu-id="24df0-166">References and the Imports Statement</span></span>](references-and-the-imports-statement.md)
- [<span data-ttu-id="24df0-167">Imports ステートメント (.NET 名前空間および型)</span><span class="sxs-lookup"><span data-stu-id="24df0-167">Imports Statement (.NET Namespace and Type)</span></span>](../../language-reference/statements/imports-statement-net-namespace-and-type.md)
- [<span data-ttu-id="24df0-168">Office ソリューションのコードの記述</span><span class="sxs-lookup"><span data-stu-id="24df0-168">Writing Code in Office Solutions</span></span>](/visualstudio/vsto/writing-code-in-office-solutions)
