---
title: 宣言された要素の参照
ms.date: 07/20/2015
helpviewer_keywords:
- declared elements [Visual Basic]
- references [Visual Basic], declared elements
- qualified names [Visual Basic]
ms.assetid: d6301709-f4cc-4b7a-b8ba-80898f14ab46
ms.openlocfilehash: a6477a9f0abaf8eb9176f4f6ab2a920af6c8f500
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345304"
---
# <a name="references-to-declared-elements-visual-basic"></a><span data-ttu-id="2888d-102">宣言された要素の参照 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2888d-102">References to Declared Elements (Visual Basic)</span></span>
<span data-ttu-id="2888d-103">宣言された要素をコードが参照する場合、Visual Basic コンパイラは参照内の名前を、その名前の適切な宣言に一致させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="2888d-103">When your code refers to a declared element, the Visual Basic compiler matches the name in your reference to the appropriate declaration of that name.</span></span> <span data-ttu-id="2888d-104">複数の要素が同じ名前で宣言されている場合は、その名前を*修飾*することによって、これらの要素のうちどれを参照するかを制御できます。</span><span class="sxs-lookup"><span data-stu-id="2888d-104">If more than one element is declared with the same name, you can control which of those elements is to be referenced by *qualifying* its name.</span></span>  
  
 <span data-ttu-id="2888d-105">コンパイラは、名前の参照を最も*狭いスコープ*の名前宣言と照合しようとします。</span><span class="sxs-lookup"><span data-stu-id="2888d-105">The compiler attempts to match a name reference to a name declaration with the *narrowest scope*.</span></span> <span data-ttu-id="2888d-106">これは、参照を行うコードから開始し、それを含んでいる要素のレベルを通じて外部で動作することを意味します。</span><span class="sxs-lookup"><span data-stu-id="2888d-106">This means it starts with the code making the reference and works outward through successive levels of containing elements.</span></span>  
  
 <span data-ttu-id="2888d-107">次の例では、同じ名前を持つ2つの変数への参照を示します。</span><span class="sxs-lookup"><span data-stu-id="2888d-107">The following example shows references to two variables with the same name.</span></span> <span data-ttu-id="2888d-108">この例では、`totalCount`という名前の2つの変数を、モジュール `container`のさまざまなレベルのスコープで宣言しています。</span><span class="sxs-lookup"><span data-stu-id="2888d-108">The example declares two variables, each named `totalCount`, at different levels of scope in module `container`.</span></span> <span data-ttu-id="2888d-109">プロシージャ `showCount` が修飾なしで `totalCount` 表示される場合、Visual Basic コンパイラは、最も狭いスコープ (つまり、`showCount`内のローカル宣言) への参照を解決します。</span><span class="sxs-lookup"><span data-stu-id="2888d-109">When the procedure `showCount` displays `totalCount` without qualification, the Visual Basic compiler resolves the reference to the declaration with the narrowest scope, namely the local declaration inside `showCount`.</span></span> <span data-ttu-id="2888d-110">親モジュール `container`で `totalCount` を修飾すると、コンパイラは、より広いスコープの宣言への参照を解決します。</span><span class="sxs-lookup"><span data-stu-id="2888d-110">When it qualifies `totalCount` with the containing module `container`, the compiler resolves the reference to the declaration with the broader scope.</span></span>  
  
```vb  
' Assume these two modules are both in the same assembly.  
Module container  
    Public totalCount As Integer = 1  
    Public Sub showCount()  
        Dim totalCount As Integer = 6000  
        ' The following statement displays the local totalCount (6000).  
        MsgBox("Unqualified totalCount is " & CStr(totalCount))  
        ' The following statement displays the module's totalCount (1).  
        MsgBox("container.totalCount is " & CStr(container.totalCount))  
    End Sub  
End Module  
Module callingModule  
    Public Sub displayCount()  
        container.showCount()  
        ' The following statement displays the containing module's totalCount (1).  
        MsgBox("container.totalCount is " & CStr(container.totalCount))  
    End Sub  
End Module  
```  
  
## <a name="qualifying-an-element-name"></a><span data-ttu-id="2888d-111">要素名を修飾する</span><span class="sxs-lookup"><span data-stu-id="2888d-111">Qualifying an Element Name</span></span>  
 <span data-ttu-id="2888d-112">この検索プロセスをオーバーライドして、より広範なスコープで宣言された名前を指定する場合は、より広いスコープのコンテナー要素を使用して名前を*修飾*する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2888d-112">If you want to override this search process and specify a name declared in a broader scope, you must *qualify* the name with the containing element of the broader scope.</span></span> <span data-ttu-id="2888d-113">場合によっては、コンテナー要素を修飾する必要がある場合もあります。</span><span class="sxs-lookup"><span data-stu-id="2888d-113">In some cases, you might also have to qualify the containing element.</span></span>  
  
 <span data-ttu-id="2888d-114">名前を修飾すると、source ステートメントの前に、ターゲット要素が定義されている場所を識別する情報が含まれることを意味します。</span><span class="sxs-lookup"><span data-stu-id="2888d-114">Qualifying a name means preceding it in your source statement with information that identifies where the target element is defined.</span></span> <span data-ttu-id="2888d-115">この情報は、*修飾文字列*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="2888d-115">This information is called a *qualification string*.</span></span> <span data-ttu-id="2888d-116">1つ以上の名前空間、およびモジュール、クラス、または構造体を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="2888d-116">It can include one or more namespaces and a module, class, or structure.</span></span>  
  
 <span data-ttu-id="2888d-117">修飾文字列では、ターゲット要素を含むモジュール、クラス、または構造体を明確に指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2888d-117">The qualification string should unambiguously specify the module, class, or structure containing the target element.</span></span> <span data-ttu-id="2888d-118">コンテナーは、別の親要素 (通常は名前空間) に配置される場合があります。</span><span class="sxs-lookup"><span data-stu-id="2888d-118">The container might in turn be located in another containing element, usually a namespace.</span></span> <span data-ttu-id="2888d-119">修飾文字列に複数の要素を含めることが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="2888d-119">You might need to include several containing elements in the qualification string.</span></span>  
  
#### <a name="to-access-a-declared-element-by-qualifying-its-name"></a><span data-ttu-id="2888d-120">宣言された要素に名前を修飾してアクセスするには</span><span class="sxs-lookup"><span data-stu-id="2888d-120">To access a declared element by qualifying its name</span></span>  
  
1. <span data-ttu-id="2888d-121">要素が定義されている場所を確認します。</span><span class="sxs-lookup"><span data-stu-id="2888d-121">Determine the location in which the element has been defined.</span></span> <span data-ttu-id="2888d-122">これには、名前空間、または名前空間の階層が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2888d-122">This might include a namespace, or even a hierarchy of namespaces.</span></span> <span data-ttu-id="2888d-123">最下位レベルの名前空間内では、要素はモジュール、クラス、または構造体に含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="2888d-123">Within the lowest-level namespace, the element must be contained in a module, class, or structure.</span></span>  
  
    ```vb  
    ' Assume the following hierarchy exists outside your code.  
    Namespace outerSpace  
        Namespace innerSpace  
            Module holdsTotals  
                Public Structure totals  
                    Public thisTotal As Integer  
                    Public Shared grandTotal As Long  
                End Structure  
            End Module  
        End Namespace  
    End Namespace  
    ```  
  
2. <span data-ttu-id="2888d-124">ターゲット要素の場所に基づいて、修飾パスを決定します。</span><span class="sxs-lookup"><span data-stu-id="2888d-124">Determine a qualification path based on the target element's location.</span></span> <span data-ttu-id="2888d-125">最上位レベルの名前空間から開始し、最下位レベルの名前空間に進み、target 要素を含むモジュール、クラス、または構造体で終了します。</span><span class="sxs-lookup"><span data-stu-id="2888d-125">Start with the highest-level namespace, proceed to the lowest-level namespace, and end with the module, class, or structure containing the target element.</span></span> <span data-ttu-id="2888d-126">パス内の各要素には、その後に続く要素が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="2888d-126">Each element in the path must contain the element that follows it.</span></span>  
  
     <span data-ttu-id="2888d-127">`outerSpace` → `innerSpace` → `holdsTotals` → `totals`</span><span class="sxs-lookup"><span data-stu-id="2888d-127">`outerSpace` → `innerSpace` → `holdsTotals` → `totals`</span></span>  
  
3. <span data-ttu-id="2888d-128">ターゲット要素の修飾文字列を準備します。</span><span class="sxs-lookup"><span data-stu-id="2888d-128">Prepare the qualification string for the target element.</span></span> <span data-ttu-id="2888d-129">パス内のすべての要素の後にピリオド (`.`) を配置します。</span><span class="sxs-lookup"><span data-stu-id="2888d-129">Place a period (`.`) after every element in the path.</span></span> <span data-ttu-id="2888d-130">アプリケーションは、修飾文字列内のすべての要素にアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="2888d-130">Your application must have access to every element in your qualification string.</span></span>  
  
    ```vb  
    outerSpace.innerSpace.holdsTotals.totals.  
    ```  
  
4. <span data-ttu-id="2888d-131">通常の方法で、ターゲット要素を参照する式または代入ステートメントを記述します。</span><span class="sxs-lookup"><span data-stu-id="2888d-131">Write the expression or assignment statement referring to the target element in the normal way.</span></span>  
  
    ```vb  
    grandTotal = 9000  
    ```  
  
5. <span data-ttu-id="2888d-132">ターゲット要素名の前に修飾文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="2888d-132">Precede the target element name with the qualification string.</span></span> <span data-ttu-id="2888d-133">名前は、要素が含まれているモジュール、クラス、または構造体の後のピリオド (`.`) の直後に記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2888d-133">The name should immediately follow the period (`.`) that follows the module, class, or structure that contains the element.</span></span>  
  
    ```vb  
    ' Assume the following module is part of your code.  
    Module accessGrandTotal  
        Public Sub setGrandTotal()  
            outerSpace.innerSpace.holdsTotals.totals.grandTotal = 9000  
        End Sub  
    End Module  
    ```  
  
6. <span data-ttu-id="2888d-134">コンパイラは、修飾文字列を使用して、ターゲット要素参照と一致させる明確で明確な宣言を検索します。</span><span class="sxs-lookup"><span data-stu-id="2888d-134">The compiler uses the qualification string to find a clear, unambiguous declaration to which it can match the target element reference.</span></span>  
  
 <span data-ttu-id="2888d-135">また、アプリケーションが同じ名前を持つ複数のプログラミング要素にアクセスできる場合は、名前参照を修飾する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2888d-135">You might also have to qualify a name reference if your application has access to more than one programming element that has the same name.</span></span> <span data-ttu-id="2888d-136">たとえば、<xref:System.Windows.Forms> と <xref:System.Web.UI.WebControls> の名前空間にはどちらも `Label` クラス (<xref:System.Windows.Forms.Label?displayProperty=nameWithType> および <xref:System.Web.UI.WebControls.Label?displayProperty=nameWithType>) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="2888d-136">For example, the <xref:System.Windows.Forms> and <xref:System.Web.UI.WebControls> namespaces both contain a `Label` class (<xref:System.Windows.Forms.Label?displayProperty=nameWithType> and <xref:System.Web.UI.WebControls.Label?displayProperty=nameWithType>).</span></span> <span data-ttu-id="2888d-137">アプリケーションで両方を使用する場合、または独自の `Label` クラスを定義する場合は、異なる `Label` オブジェクトを区別する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2888d-137">If your application uses both, or if it defines its own `Label` class, you must distinguish the different `Label` objects.</span></span> <span data-ttu-id="2888d-138">変数宣言に、名前空間またはインポートエイリアスを含めます。</span><span class="sxs-lookup"><span data-stu-id="2888d-138">Include the namespace or import alias in the variable declaration.</span></span> <span data-ttu-id="2888d-139">次の例では、インポートエイリアスを使用します。</span><span class="sxs-lookup"><span data-stu-id="2888d-139">The following example uses the import alias.</span></span>  
  
```vb  
' The following statement must precede all your declarations.  
Imports win = System.Windows.Forms, web = System.Web.UI.WebControls  
' The following statement references the Windows.Forms.Label class.  
Dim winLabel As New win.Label()  
```  
  
## <a name="members-of-other-containing-elements"></a><span data-ttu-id="2888d-140">他のコンテナー要素のメンバー</span><span class="sxs-lookup"><span data-stu-id="2888d-140">Members of Other Containing Elements</span></span>  
 <span data-ttu-id="2888d-141">別のクラスまたは構造体の非共有メンバーを使用する場合は、まず、クラスまたは構造体のインスタンスを指す変数または式を使用して、メンバー名を修飾する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2888d-141">When you use a nonshared member of another class or structure, you must first qualify the member name with a variable or expression that points to an instance of the class or structure.</span></span> <span data-ttu-id="2888d-142">次の例では、`demoClass` は `class1`という名前のクラスのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="2888d-142">In the following example, `demoClass` is an instance of a class named `class1`.</span></span>  
  
```vb  
Dim demoClass As class1 = New class1()  
demoClass.someSub[(argumentlist)]  
```  
  
 <span data-ttu-id="2888d-143">クラス名自体を使用して、[Shared](../../../../visual-basic/language-reference/modifiers/shared.md) されていないメンバーを修飾することはできません。</span><span class="sxs-lookup"><span data-stu-id="2888d-143">You cannot use the class name itself to qualify a member that is not [Shared](../../../../visual-basic/language-reference/modifiers/shared.md).</span></span> <span data-ttu-id="2888d-144">まず、オブジェクト変数にインスタンスを作成し (この場合は `demoClass`)、変数名でインスタンスを参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2888d-144">You must first create an instance in an object variable (in this case `demoClass`) and then reference it by the variable name.</span></span>  
  
 <span data-ttu-id="2888d-145">クラスまたは構造体に `Shared` メンバーが含まれている場合は、クラスまたは構造体の名前を使用するか、インスタンスを指す変数または式を使用して、そのメンバーを修飾できます。</span><span class="sxs-lookup"><span data-stu-id="2888d-145">If a class or structure has a `Shared` member, you can qualify that member either with the class or structure name or with a variable or expression that points to an instance.</span></span>  
  
 <span data-ttu-id="2888d-146">モジュールには個別のインスタンスがなく、すべてのメンバーが既定で `Shared` されます。</span><span class="sxs-lookup"><span data-stu-id="2888d-146">A module does not have any separate instances, and all its members are `Shared` by default.</span></span> <span data-ttu-id="2888d-147">そのため、モジュール名を持つモジュールメンバーを修飾します。</span><span class="sxs-lookup"><span data-stu-id="2888d-147">Therefore, you qualify a module member with the module name.</span></span>  
  
 <span data-ttu-id="2888d-148">次の例では、モジュールメンバープロシージャへの修飾参照を示します。</span><span class="sxs-lookup"><span data-stu-id="2888d-148">The following example shows qualified references to module member procedures.</span></span> <span data-ttu-id="2888d-149">この例では、2つの `Sub` プロシージャを、プロジェクト内の異なるモジュールに2つの名前付き `perform`として宣言しています。</span><span class="sxs-lookup"><span data-stu-id="2888d-149">The example declares two `Sub` procedures, both named `perform`, in different modules in a project.</span></span> <span data-ttu-id="2888d-150">それぞれのモジュール内で修飾子を指定せずにそれぞれを指定できますが、他の場所から参照されている場合は修飾する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2888d-150">Each one can be specified without qualification within its own module but must be qualified if referenced from anywhere else.</span></span> <span data-ttu-id="2888d-151">`module3` の最後の参照は `perform`を修飾しないため、コンパイラはその参照を解決できません。</span><span class="sxs-lookup"><span data-stu-id="2888d-151">Because the final reference in `module3` does not qualify `perform`, the compiler cannot resolve that reference.</span></span>  
  
```vb  
' Assume these three modules are all in the same assembly.  
Module module1  
    Public Sub perform()  
        MsgBox("module1.perform() now returning")  
    End Sub  
End Module  
Module module2  
    Public Sub perform()  
        MsgBox("module2.perform() now returning")  
    End Sub  
    Public Sub doSomething()  
        ' The following statement calls perform in module2, the active module.  
        perform()  
        ' The following statement calls perform in module1.  
        module1.perform()  
    End Sub  
End Module  
Module module3  
    Public Sub callPerform()  
        ' The following statement calls perform in module1.  
        module1.perform()  
        ' The following statement makes an unresolvable name reference  
        ' and therefore generates a COMPILER ERROR.  
        perform() ' INVALID statement  
    End Sub  
End Module  
```  
  
## <a name="references-to-projects"></a><span data-ttu-id="2888d-152">プロジェクトへの参照</span><span class="sxs-lookup"><span data-stu-id="2888d-152">References to Projects</span></span>  
 <span data-ttu-id="2888d-153">別のプロジェクトで定義されている [Public](../../../../visual-basic/language-reference/modifiers/public.md) 要素を使用するには、最初にそのプロジェクトのアセンブリまたはタイプライブラリへの*参照*を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2888d-153">To use [Public](../../../../visual-basic/language-reference/modifiers/public.md) elements defined in another project, you must first set a *reference* to that project's assembly or type library.</span></span> <span data-ttu-id="2888d-154">参照を設定するには、 **[プロジェクト]** メニューの **[参照の追加]** をクリックするか、 [-reference (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/reference.md)コマンドラインコンパイラオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="2888d-154">To set a reference, click **Add Reference** on the **Project** menu, or use the [-reference (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/reference.md) command-line compiler option.</span></span>  
  
 <span data-ttu-id="2888d-155">たとえば、.NET Framework の XML オブジェクトモデルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="2888d-155">For example, you can use the XML object model of the .NET Framework.</span></span> <span data-ttu-id="2888d-156"><xref:System.Xml> 名前空間への参照を設定した場合は、<xref:System.Xml.XmlDocument>などの任意のクラスを宣言して使用できます。</span><span class="sxs-lookup"><span data-stu-id="2888d-156">If you set a reference to the <xref:System.Xml> namespace, you can declare and use any of its classes, such as <xref:System.Xml.XmlDocument>.</span></span> <span data-ttu-id="2888d-157">次の例では、<xref:System.Xml.XmlDocument>を使用します。</span><span class="sxs-lookup"><span data-stu-id="2888d-157">The following example uses <xref:System.Xml.XmlDocument>.</span></span>  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As System.Xml.XmlDocument  
```  
  
## <a name="importing-containing-elements"></a><span data-ttu-id="2888d-158">インポート (含まれる要素を)</span><span class="sxs-lookup"><span data-stu-id="2888d-158">Importing Containing Elements</span></span>  
 <span data-ttu-id="2888d-159">[Imports ステートメント (.NET 名前空間と型)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)を使用して、使用するモジュールまたはクラスを含む名前空間を*インポート*できます。</span><span class="sxs-lookup"><span data-stu-id="2888d-159">You can use the [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) to *import* the namespaces that contain the modules or classes that you want to use.</span></span> <span data-ttu-id="2888d-160">これにより、インポートされた名前空間で定義されている要素の名前を完全修飾せずに参照できます。</span><span class="sxs-lookup"><span data-stu-id="2888d-160">This enables you to refer to the elements defined in an imported namespace without fully qualifying their names.</span></span> <span data-ttu-id="2888d-161">次の例では、前の例を書き直して <xref:System.Xml> 名前空間をインポートします。</span><span class="sxs-lookup"><span data-stu-id="2888d-161">The following example rewrites the previous example to import the <xref:System.Xml> namespace.</span></span>  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As XmlDocument  
```  
  
 <span data-ttu-id="2888d-162">さらに、`Imports` ステートメントでは、インポートされた各名前空間の*インポートエイリアス*を定義できます。</span><span class="sxs-lookup"><span data-stu-id="2888d-162">In addition, the `Imports` statement can define an *import alias* for each imported namespace.</span></span> <span data-ttu-id="2888d-163">これにより、ソースコードを短く、読みやすくすることができます。</span><span class="sxs-lookup"><span data-stu-id="2888d-163">This can make the source code shorter and easier to read.</span></span> <span data-ttu-id="2888d-164">次の例では、前の例を書き直して、<xref:System.Xml> 名前空間のエイリアスとして `xD` を使用します。</span><span class="sxs-lookup"><span data-stu-id="2888d-164">The following example rewrites the previous example to use `xD` as an alias for the <xref:System.Xml> namespace.</span></span>  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports xD = System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As xD.XmlDocument  
```  
  
 <span data-ttu-id="2888d-165">`Imports` ステートメントでは、他のプロジェクトの要素をアプリケーションで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="2888d-165">The `Imports` statement does not make elements from other projects available to your application.</span></span> <span data-ttu-id="2888d-166">つまり、参照の設定は行われません。</span><span class="sxs-lookup"><span data-stu-id="2888d-166">That is, it does not take the place of setting a reference.</span></span> <span data-ttu-id="2888d-167">名前空間をインポートすると、その名前空間で定義されている名前を修飾する必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="2888d-167">Importing a namespace just removes the requirement to qualify the names defined in that namespace.</span></span>  
  
 <span data-ttu-id="2888d-168">また、`Imports` ステートメントを使用して、モジュール、クラス、構造体、および列挙型をインポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="2888d-168">You can also use the `Imports` statement to import modules, classes, structures, and enumerations.</span></span> <span data-ttu-id="2888d-169">その後、このようなインポートされた要素のメンバーを修飾なしで使用できます。</span><span class="sxs-lookup"><span data-stu-id="2888d-169">You can then use the members of such imported elements without qualification.</span></span> <span data-ttu-id="2888d-170">ただし、クラスや構造体の非共有メンバーは、クラスまたは構造体のインスタンスに評価される変数または式を使用して、常に修飾する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2888d-170">However, you must always qualify nonshared members of classes and structures with a variable or expression that evaluates to an instance of the class or structure.</span></span>  
  
## <a name="naming-guidelines"></a><span data-ttu-id="2888d-171">名前付けガイドライン</span><span class="sxs-lookup"><span data-stu-id="2888d-171">Naming Guidelines</span></span>  
 <span data-ttu-id="2888d-172">同じ名前を持つ2つ以上のプログラミング要素を定義すると、コンパイラがその名前への参照を解決しようとしたときに、*名前のあいまい*さが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2888d-172">When you define two or more programming elements that have the same name, a *name ambiguity* can result when the compiler attempts to resolve a reference to that name.</span></span> <span data-ttu-id="2888d-173">スコープ内に複数の定義が含まれている場合、またはスコープ内に定義が存在しない場合、参照は解決不可能なになります。</span><span class="sxs-lookup"><span data-stu-id="2888d-173">If more than one definition is in scope, or if no definition is in scope, the reference is irresolvable.</span></span> <span data-ttu-id="2888d-174">例については、このヘルプページの「修飾参照の例」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2888d-174">For an example, see "Qualified Reference Example" on this Help page.</span></span>  
  
 <span data-ttu-id="2888d-175">すべての要素に一意の名前を付けることで、名前のあいまいさを回避できます。</span><span class="sxs-lookup"><span data-stu-id="2888d-175">You can avoid name ambiguity by giving all your elements unique names.</span></span> <span data-ttu-id="2888d-176">その後、名前を名前空間、モジュール、またはクラスで修飾することなく、任意の要素を参照できます。</span><span class="sxs-lookup"><span data-stu-id="2888d-176">Then you can make reference to any element without having to qualify its name with a namespace, module, or class.</span></span> <span data-ttu-id="2888d-177">間違った要素が誤って参照される可能性を低くすることもできます。</span><span class="sxs-lookup"><span data-stu-id="2888d-177">You also reduce the chances of accidentally referring to the wrong element.</span></span>  
  
## <a name="shadowing"></a><span data-ttu-id="2888d-178">シャドウ</span><span class="sxs-lookup"><span data-stu-id="2888d-178">Shadowing</span></span>  
 <span data-ttu-id="2888d-179">2 つのプログラミング要素が同じ名前を共有している場合、そのうちの 1 つを非表示にしたり、もう一方に*シャドウ*を付けることができます。</span><span class="sxs-lookup"><span data-stu-id="2888d-179">When two programming elements share the same name, one of them can hide, or *shadow*, the other one.</span></span> <span data-ttu-id="2888d-180">シャドウされた要素を参照することはできません。代わりに、シャドウされた要素名を使用するコードでは、Visual Basic コンパイラによってシャドウ要素に解決されます。</span><span class="sxs-lookup"><span data-stu-id="2888d-180">A shadowed element is not available for reference; instead, when your code uses the shadowed element name, the Visual Basic compiler resolves it to the shadowing element.</span></span> <span data-ttu-id="2888d-181">例の詳細については、「[Visual Basic におけるシャドウ](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2888d-181">For a more detailed explanation with examples, see [Shadowing in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2888d-182">参照</span><span class="sxs-lookup"><span data-stu-id="2888d-182">See also</span></span>

- [<span data-ttu-id="2888d-183">宣言された要素の名前</span><span class="sxs-lookup"><span data-stu-id="2888d-183">Declared Element Names</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="2888d-184">宣言された要素の特性</span><span class="sxs-lookup"><span data-stu-id="2888d-184">Declared Element Characteristics</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)
- [<span data-ttu-id="2888d-185">プロジェクトおよびソリューションのプロパティの管理</span><span class="sxs-lookup"><span data-stu-id="2888d-185">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
- [<span data-ttu-id="2888d-186">変数</span><span class="sxs-lookup"><span data-stu-id="2888d-186">Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [<span data-ttu-id="2888d-187">Imports ステートメント (.NET 名前空間および型)</span><span class="sxs-lookup"><span data-stu-id="2888d-187">Imports Statement (.NET Namespace and Type)</span></span>](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [<span data-ttu-id="2888d-188">New 演算子</span><span class="sxs-lookup"><span data-stu-id="2888d-188">New Operator</span></span>](../../../../visual-basic/language-reference/operators/new-operator.md)
- [<span data-ttu-id="2888d-189">Public</span><span class="sxs-lookup"><span data-stu-id="2888d-189">Public</span></span>](../../../../visual-basic/language-reference/modifiers/public.md)
