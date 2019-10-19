---
title: Imports ステートメント-.NET 名前空間と型 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Imports
- imports
helpviewer_keywords:
- declared element names [Visual Basic], qualification
- imports [Visual Basic]
- Imports statement [Visual Basic]
- aliases [Visual Basic], Imports statement
- container elements [Visual Basic]
- namespaces [Visual Basic], importing
- Imports statement [Visual Basic], syntax
- import aliases [Visual Basic]
- aliases [Visual Basic], import
- declared elements [Visual Basic], container elements
ms.assetid: 7062f8aa-d890-4232-9eed-92836e13fb6e
ms.openlocfilehash: 62b208d4795d0370cb6eace7f45ef42551e6960f
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72581780"
---
# <a name="imports-statement-net-namespace-and-type"></a><span data-ttu-id="e1489-102">Imports ステートメント (.NET 名前空間および型)</span><span class="sxs-lookup"><span data-stu-id="e1489-102">Imports Statement (.NET Namespace and Type)</span></span>
<span data-ttu-id="e1489-103">名前空間の修飾なしで型名を参照できるようにします。</span><span class="sxs-lookup"><span data-stu-id="e1489-103">Enables type names to be referenced without namespace qualification.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1489-104">構文</span><span class="sxs-lookup"><span data-stu-id="e1489-104">Syntax</span></span>  
  
```vb  
Imports [ aliasname = ] namespace  
' -or-  
Imports [ aliasname = ] namespace.element  
```  
  
## <a name="parts"></a><span data-ttu-id="e1489-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="e1489-105">Parts</span></span>  
  
|<span data-ttu-id="e1489-106">用語</span><span class="sxs-lookup"><span data-stu-id="e1489-106">Term</span></span>|<span data-ttu-id="e1489-107">定義</span><span class="sxs-lookup"><span data-stu-id="e1489-107">Definition</span></span>|  
|---|---|  
|`aliasname`|<span data-ttu-id="e1489-108">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="e1489-108">Optional.</span></span> <span data-ttu-id="e1489-109">完全修飾文字列ではなく、コードが `namespace` を参照できる*インポートエイリアス*または名前。</span><span class="sxs-lookup"><span data-stu-id="e1489-109">An *import alias* or name by which code can refer to `namespace` instead of the full qualification string.</span></span> <span data-ttu-id="e1489-110">「 [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e1489-110">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>|  
|`namespace`|<span data-ttu-id="e1489-111">必須です。</span><span class="sxs-lookup"><span data-stu-id="e1489-111">Required.</span></span> <span data-ttu-id="e1489-112">インポートされる名前空間の完全修飾名。</span><span class="sxs-lookup"><span data-stu-id="e1489-112">The fully qualified name of the namespace being imported.</span></span> <span data-ttu-id="e1489-113">には、任意のレベルに入れ子になった名前空間の文字列を指定できます。</span><span class="sxs-lookup"><span data-stu-id="e1489-113">Can be a string of namespaces nested to any level.</span></span>|  
|`element`|<span data-ttu-id="e1489-114">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="e1489-114">Optional.</span></span> <span data-ttu-id="e1489-115">名前空間で宣言されているプログラミング要素の名前。</span><span class="sxs-lookup"><span data-stu-id="e1489-115">The name of a programming element declared in the namespace.</span></span> <span data-ttu-id="e1489-116">任意のコンテナー要素を指定できます。</span><span class="sxs-lookup"><span data-stu-id="e1489-116">Can be any container element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e1489-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="e1489-117">Remarks</span></span>  
 <span data-ttu-id="e1489-118">@No__t_0 ステートメントを使用すると、特定の名前空間に含まれている型を直接参照できます。</span><span class="sxs-lookup"><span data-stu-id="e1489-118">The `Imports`  statement enables types that are contained in a given namespace to be referenced directly.</span></span>  
  
 <span data-ttu-id="e1489-119">1つの名前空間名または入れ子になった名前空間の文字列を指定できます。</span><span class="sxs-lookup"><span data-stu-id="e1489-119">You can supply a single namespace name or a string of nested namespaces.</span></span> <span data-ttu-id="e1489-120">入れ子になった各名前空間は、次の例に示すように、1つ上のレベルの名前空間からピリオド (`.`) で区切られます。</span><span class="sxs-lookup"><span data-stu-id="e1489-120">Each nested namespace is separated from the next higher level namespace by a period (`.`), as the following example illustrates.</span></span>  
  
 `Imports System.Collections.Generic`  
  
 <span data-ttu-id="e1489-121">各ソースファイルには、任意の数の `Imports` ステートメントを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="e1489-121">Each source file can contain any number of `Imports` statements.</span></span> <span data-ttu-id="e1489-122">これらは、`Option Strict` ステートメントなど、任意のオプション宣言に従う必要があり、`Module` や `Class` ステートメントなどのプログラミング要素の宣言の前に記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1489-122">These must follow any option declarations, such as the `Option Strict` statement, and they must precede any programming element declarations, such as `Module` or `Class` statements.</span></span>  
  
 <span data-ttu-id="e1489-123">@No__t_0 は、ファイルレベルでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="e1489-123">You can use `Imports` only at file level.</span></span> <span data-ttu-id="e1489-124">つまり、インポートの宣言コンテキストはソースファイルである必要があり、名前空間、クラス、構造体、モジュール、インターフェイス、プロシージャ、またはブロックにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="e1489-124">This means the declaration context for importation must be a source file, and cannot be a namespace, class, structure, module, interface, procedure, or block.</span></span>  
  
 <span data-ttu-id="e1489-125">@No__t_0 ステートメントでは、プロジェクトで他のプロジェクトおよびアセンブリの要素を使用できないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e1489-125">Note that the `Imports` statement does not make elements from other projects and assemblies available to your project.</span></span> <span data-ttu-id="e1489-126">インポートでは、参照の設定は行われません。</span><span class="sxs-lookup"><span data-stu-id="e1489-126">Importing does not take the place of setting a reference.</span></span> <span data-ttu-id="e1489-127">これにより、プロジェクトで既に使用可能な名前を修飾する必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="e1489-127">It only removes the need to qualify names that are already available to your project.</span></span> <span data-ttu-id="e1489-128">詳細については、「宣言された[要素への参照](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)」の「コンテナー要素のインポート」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e1489-128">For more information, see "Importing Containing Elements" in [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e1489-129">暗黙の `Imports` ステートメントを定義するには、[[参照] ページの [プロジェクトデザイナー] (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic)を使用します。</span><span class="sxs-lookup"><span data-stu-id="e1489-129">You can define implicit `Imports` statements by using the [References Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic).</span></span> <span data-ttu-id="e1489-130">詳細については、「[方法: インポートされた名前空間を追加または削除する (Visual Basic)](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e1489-130">For more information, see [How to: Add or Remove Imported Namespaces (Visual Basic)](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic).</span></span>  
  
## <a name="import-aliases"></a><span data-ttu-id="e1489-131">インポート エイリアス</span><span class="sxs-lookup"><span data-stu-id="e1489-131">Import Aliases</span></span>  
 <span data-ttu-id="e1489-132">*インポートエイリアス*は、名前空間または型のエイリアスを定義します。</span><span class="sxs-lookup"><span data-stu-id="e1489-132">An *import alias* defines the alias for a namespace or type.</span></span> <span data-ttu-id="e1489-133">インポートエイリアスは、1つまたは複数の名前空間で宣言されているものと同じ名前の項目を使用する必要がある場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="e1489-133">Import aliases are useful when you need to use items with the same name that are declared in one or more namespaces.</span></span> <span data-ttu-id="e1489-134">詳細と例については、「宣言された[要素への参照](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)」の「要素名の修飾」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e1489-134">For more information and an example, see "Qualifying an Element Name" in [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
 <span data-ttu-id="e1489-135">モジュールレベルで `aliasname` と同じ名前のメンバーを宣言することはできません。</span><span class="sxs-lookup"><span data-stu-id="e1489-135">You should not declare a member at module level with the same name as `aliasname`.</span></span> <span data-ttu-id="e1489-136">この場合、Visual Basic コンパイラは、宣言されたメンバーに対してのみ `aliasname` を使用し、それをインポートエイリアスとして認識しなくなります。</span><span class="sxs-lookup"><span data-stu-id="e1489-136">If you do, the Visual Basic compiler uses `aliasname` only for the declared member and no longer recognizes it as an import alias.</span></span>  
  
 <span data-ttu-id="e1489-137">インポートエイリアスの宣言に使用される構文は、XML 名前空間プレフィックスのインポートに使用される構文と似ていますが、結果は異なります。</span><span class="sxs-lookup"><span data-stu-id="e1489-137">Although the syntax used for declaring an import alias is like that used for importing an XML namespace prefix, the results are different.</span></span> <span data-ttu-id="e1489-138">インポートエイリアスは、コード内で式として使用できます。一方、XML 名前空間プレフィックスは、xml リテラルまたは XML 軸プロパティで、修飾された要素名または属性名のプレフィックスとしてのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="e1489-138">An import alias can be used as an expression in your code, whereas an XML namespace prefix can be used only in XML literals or XML axis properties as the prefix for a qualified element or attribute name.</span></span>  
  
### <a name="element-names"></a><span data-ttu-id="e1489-139">要素の名前</span><span class="sxs-lookup"><span data-stu-id="e1489-139">Element Names</span></span>  
 <span data-ttu-id="e1489-140">@No__t_0 を指定する場合は、*コンテナー要素*、つまり、他の要素を含むことができるプログラミング要素を表す必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1489-140">If you supply `element`, it must represent a *container element*, that is, a programming element that can contain other elements.</span></span> <span data-ttu-id="e1489-141">コンテナー要素には、クラス、構造体、モジュール、インターフェイス、および列挙体が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e1489-141">Container elements include classes, structures, modules, interfaces, and enumerations.</span></span>  
  
 <span data-ttu-id="e1489-142">@No__t_0 ステートメントで使用できる要素のスコープは、`element` を指定したかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="e1489-142">The scope of the elements made available by an `Imports` statement depends on whether you specify `element`.</span></span> <span data-ttu-id="e1489-143">@No__t_0 だけを指定した場合、その名前空間の一意の名前を持つすべてのメンバーと、その名前空間内のコンテナー要素のメンバーは、修飾なしで使用できます。</span><span class="sxs-lookup"><span data-stu-id="e1489-143">If you specify only `namespace`, all uniquely named members of that namespace, and members of container elements within that namespace, are available without qualification.</span></span> <span data-ttu-id="e1489-144">@No__t_0 と `element` の両方を指定すると、その要素のメンバーだけが修飾なしで使用できます。</span><span class="sxs-lookup"><span data-stu-id="e1489-144">If you specify both `namespace` and `element`, only the members of that element are available without qualification.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e1489-145">例</span><span class="sxs-lookup"><span data-stu-id="e1489-145">Example</span></span>  
 <span data-ttu-id="e1489-146">次の例では、C:\ 内のすべてのフォルダーが返されます。<xref:System.IO.DirectoryInfo> クラスを使用したディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="e1489-146">The following example returns all the folders in the C:\ directory by using the <xref:System.IO.DirectoryInfo> class.</span></span>  
  
 <span data-ttu-id="e1489-147">コードには、ファイルの先頭に `Imports` ステートメントがありません。</span><span class="sxs-lookup"><span data-stu-id="e1489-147">The code has no `Imports` statements at the top of the file.</span></span> <span data-ttu-id="e1489-148">したがって、`DirectoryInfo`、<xref:System.Text.StringBuilder>、および <xref:Microsoft.VisualBasic.ControlChars.CrLf> 参照はすべて、名前空間で完全修飾されています。</span><span class="sxs-lookup"><span data-stu-id="e1489-148">Therefore, the `DirectoryInfo`, <xref:System.Text.StringBuilder>, and <xref:Microsoft.VisualBasic.ControlChars.CrLf> references are all fully qualified with the namespaces.</span></span>  
  
 [!code-vb[VbVbalrStatements#152](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#152)]  
  
## <a name="example"></a><span data-ttu-id="e1489-149">例</span><span class="sxs-lookup"><span data-stu-id="e1489-149">Example</span></span>  
 <span data-ttu-id="e1489-150">次の例には、参照先の名前空間の `Imports` ステートメントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e1489-150">The following example includes `Imports` statements for the referenced namespaces.</span></span> <span data-ttu-id="e1489-151">そのため、型は名前空間で完全修飾されている必要はありません。</span><span class="sxs-lookup"><span data-stu-id="e1489-151">Therefore, the types do not have to be fully qualified with the namespaces.</span></span>  
  
 [!code-vb[VbVbalrStatements#153](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#153)]  
  
 [!code-vb[VbVbalrStatements#154](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#154)]  
  
## <a name="example"></a><span data-ttu-id="e1489-152">例</span><span class="sxs-lookup"><span data-stu-id="e1489-152">Example</span></span>  
 <span data-ttu-id="e1489-153">次の例には、参照先の名前空間のエイリアスを作成する `Imports` ステートメントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e1489-153">The following example includes `Imports` statements that create aliases for the referenced namespaces.</span></span> <span data-ttu-id="e1489-154">型はエイリアスで修飾されます。</span><span class="sxs-lookup"><span data-stu-id="e1489-154">The types are qualified with the aliases.</span></span>  
  
 [!code-vb[VbVbalrStatements#155](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#155)]  
  
 [!code-vb[VbVbalrStatements#156](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#156)]  
  
## <a name="example"></a><span data-ttu-id="e1489-155">例</span><span class="sxs-lookup"><span data-stu-id="e1489-155">Example</span></span>  
 <span data-ttu-id="e1489-156">次の例には、参照される型のエイリアスを作成する `Imports` ステートメントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e1489-156">The following example includes `Imports` statements that create aliases for the referenced types.</span></span> <span data-ttu-id="e1489-157">エイリアスは、型を指定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="e1489-157">Aliases are used to specify the types.</span></span>  
  
 [!code-vb[VbVbalrStatements#157](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#157)]  
  
 [!code-vb[VbVbalrStatements#158](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#158)]  
  
## <a name="see-also"></a><span data-ttu-id="e1489-158">関連項目</span><span class="sxs-lookup"><span data-stu-id="e1489-158">See also</span></span>

- [<span data-ttu-id="e1489-159">Namespace ステートメント</span><span class="sxs-lookup"><span data-stu-id="e1489-159">Namespace Statement</span></span>](../../../visual-basic/language-reference/statements/namespace-statement.md)
- [<span data-ttu-id="e1489-160">Visual Basic 内の名前空間</span><span class="sxs-lookup"><span data-stu-id="e1489-160">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)
- [<span data-ttu-id="e1489-161">参照と Imports ステートメント</span><span class="sxs-lookup"><span data-stu-id="e1489-161">References and the Imports Statement</span></span>](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)
- [<span data-ttu-id="e1489-162">Imports ステートメント (XML 名前空間)</span><span class="sxs-lookup"><span data-stu-id="e1489-162">Imports Statement (XML Namespace)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)
- [<span data-ttu-id="e1489-163">宣言された要素の参照</span><span class="sxs-lookup"><span data-stu-id="e1489-163">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
