---
title: Imports ステートメント - .NET Namespace よぶ型 (Visual Basic)
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
ms.openlocfilehash: 4574bab62ca6d095ab66c17bf186da5f3d79bfb7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61637883"
---
# <a name="imports-statement-net-namespace-and-type"></a><span data-ttu-id="8c8c3-102">Imports ステートメント (.NET 名前空間および型)</span><span class="sxs-lookup"><span data-stu-id="8c8c3-102">Imports Statement (.NET Namespace and Type)</span></span>
<span data-ttu-id="8c8c3-103">有効では、名前空間の修飾せずに参照する名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="8c8c3-103">Enables type names to be referenced without namespace qualification.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c8c3-104">構文</span><span class="sxs-lookup"><span data-stu-id="8c8c3-104">Syntax</span></span>  
  
```  
Imports [ aliasname = ] namespace  
-or-  
Imports [ aliasname = ] namespace.element  
```  
  
## <a name="parts"></a><span data-ttu-id="8c8c3-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="8c8c3-105">Parts</span></span>  
  
|<span data-ttu-id="8c8c3-106">用語</span><span class="sxs-lookup"><span data-stu-id="8c8c3-106">Term</span></span>|<span data-ttu-id="8c8c3-107">定義</span><span class="sxs-lookup"><span data-stu-id="8c8c3-107">Definition</span></span>|  
|---|---|  
|`aliasname`|<span data-ttu-id="8c8c3-108">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="8c8c3-108">Optional.</span></span> <span data-ttu-id="8c8c3-109">*インポート エイリアス*または名前が使用されるコードを参照できます`namespace`完全に修飾文字列の代わりにします。</span><span class="sxs-lookup"><span data-stu-id="8c8c3-109">An *import alias* or name by which code can refer to `namespace` instead of the full qualification string.</span></span> <span data-ttu-id="8c8c3-110">「 [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8c8c3-110">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>|  
|`namespace`|<span data-ttu-id="8c8c3-111">必須。</span><span class="sxs-lookup"><span data-stu-id="8c8c3-111">Required.</span></span> <span data-ttu-id="8c8c3-112">インポートされる名前空間の完全修飾名。</span><span class="sxs-lookup"><span data-stu-id="8c8c3-112">The fully qualified name of the namespace being imported.</span></span> <span data-ttu-id="8c8c3-113">名前空間の文字列はネストできますを任意のレベル。</span><span class="sxs-lookup"><span data-stu-id="8c8c3-113">Can be a string of namespaces nested to any level.</span></span>|  
|`element`|<span data-ttu-id="8c8c3-114">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="8c8c3-114">Optional.</span></span> <span data-ttu-id="8c8c3-115">名前空間で宣言されたプログラミング要素の名前。</span><span class="sxs-lookup"><span data-stu-id="8c8c3-115">The name of a programming element declared in the namespace.</span></span> <span data-ttu-id="8c8c3-116">任意のコンテナー要素を指定できます。</span><span class="sxs-lookup"><span data-stu-id="8c8c3-116">Can be any container element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8c8c3-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="8c8c3-117">Remarks</span></span>  
 <span data-ttu-id="8c8c3-118">`Imports`ステートメントを直接参照できる特定の名前空間に含まれる型を有効にします。</span><span class="sxs-lookup"><span data-stu-id="8c8c3-118">The `Imports`  statement enables types that are contained in a given namespace to be referenced directly.</span></span>  
  
 <span data-ttu-id="8c8c3-119">単一の名前空間名または入れ子になった名前空間の文字列を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="8c8c3-119">You can supply a single namespace name or a string of nested namespaces.</span></span> <span data-ttu-id="8c8c3-120">入れ子になった各名前空間は、ピリオドで次のより高いレベルの名前空間から分離 (`.`)、次の例に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="8c8c3-120">Each nested namespace is separated from the next higher level namespace by a period (`.`), as the following example illustrates.</span></span>  
  
 `Imports System.Collections.Generic`  
  
 <span data-ttu-id="8c8c3-121">各ソース ファイルは、任意の数を含めることができます`Imports`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="8c8c3-121">Each source file can contain any number of `Imports` statements.</span></span> <span data-ttu-id="8c8c3-122">オプションの任意の宣言をなどこれらに従う必要があります、`Option Strict`ステートメント、および、必要がありますの前に任意のプログラミング要素宣言など`Module`または`Class`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="8c8c3-122">These must follow any option declarations, such as the `Option Strict` statement, and they must precede any programming element declarations, such as `Module` or `Class` statements.</span></span>  
  
 <span data-ttu-id="8c8c3-123">使用することができます`Imports`ファイル レベルでのみです。</span><span class="sxs-lookup"><span data-stu-id="8c8c3-123">You can use `Imports` only at file level.</span></span> <span data-ttu-id="8c8c3-124">つまり、宣言のコンテキストのインポートでは、ソース ファイルである必要があります、名前空間、クラス、構造体、モジュール、インターフェイス、プロシージャ、またはブロックすることはできません。</span><span class="sxs-lookup"><span data-stu-id="8c8c3-124">This means the declaration context for importation must be a source file, and cannot be a namespace, class, structure, module, interface, procedure, or block.</span></span>  
  
 <span data-ttu-id="8c8c3-125">なお、`Imports`ステートメントは行いません他のプロジェクトおよびアセンブリからの要素をプロジェクトに使用できます。</span><span class="sxs-lookup"><span data-stu-id="8c8c3-125">Note that the `Imports` statement does not make elements from other projects and assemblies available to your project.</span></span> <span data-ttu-id="8c8c3-126">インポートしても、参照設定の代わりにはなりません。</span><span class="sxs-lookup"><span data-stu-id="8c8c3-126">Importing does not take the place of setting a reference.</span></span> <span data-ttu-id="8c8c3-127">既にプロジェクトに使用できる名前を修飾する必要性を削除するだけです。</span><span class="sxs-lookup"><span data-stu-id="8c8c3-127">It only removes the need to qualify names that are already available to your project.</span></span> <span data-ttu-id="8c8c3-128">詳細については、「を格納している要素のインポート」を参照してください[References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)します。</span><span class="sxs-lookup"><span data-stu-id="8c8c3-128">For more information, see "Importing Containing Elements" in [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8c8c3-129">暗黙の型を定義する`Imports`ステートメントを使用して、[参照設定 ページ、プロジェクト デザイナー (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic)します。</span><span class="sxs-lookup"><span data-stu-id="8c8c3-129">You can define implicit `Imports` statements by using the [References Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic).</span></span> <span data-ttu-id="8c8c3-130">詳細については、「[方法 :追加またはインポートされた名前空間 (Visual Basic) を削除する](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic)します。</span><span class="sxs-lookup"><span data-stu-id="8c8c3-130">For more information, see [How to: Add or Remove Imported Namespaces (Visual Basic)](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic).</span></span>  
  
## <a name="import-aliases"></a><span data-ttu-id="8c8c3-131">インポート エイリアス</span><span class="sxs-lookup"><span data-stu-id="8c8c3-131">Import Aliases</span></span>  
 <span data-ttu-id="8c8c3-132">*インポート エイリアス*名前空間または型のエイリアスを定義します。</span><span class="sxs-lookup"><span data-stu-id="8c8c3-132">An *import alias* defines the alias for a namespace or type.</span></span> <span data-ttu-id="8c8c3-133">インポート エイリアスは、1 つまたは複数の名前空間で宣言されているのと同じ名前の項目を使用する必要がある場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="8c8c3-133">Import aliases are useful when you need to use items with the same name that are declared in one or more namespaces.</span></span> <span data-ttu-id="8c8c3-134">詳細と例では、「an 要素名を修飾する」を参照してください[References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)します。</span><span class="sxs-lookup"><span data-stu-id="8c8c3-134">For more information and an example, see "Qualifying an Element Name" in [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
 <span data-ttu-id="8c8c3-135">同じ名前では、モジュール レベルのメンバーを宣言する必要があります`aliasname`します。</span><span class="sxs-lookup"><span data-stu-id="8c8c3-135">You should not declare a member at module level with the same name as `aliasname`.</span></span> <span data-ttu-id="8c8c3-136">Visual Basic コンパイラを使用する場合は、`aliasname`されなくし、宣言されたメンバーに対してのみインポート エイリアスとして認識します。</span><span class="sxs-lookup"><span data-stu-id="8c8c3-136">If you do, the Visual Basic compiler uses `aliasname` only for the declared member and no longer recognizes it as an import alias.</span></span>  
  
 <span data-ttu-id="8c8c3-137">XML 名前空間プレフィックスをインポートするのには、インポート エイリアスの宣言に使用される構文は使用がそのような結果は異なります。</span><span class="sxs-lookup"><span data-stu-id="8c8c3-137">Although the syntax used for declaring an import alias is like that used for importing an XML namespace prefix, the results are different.</span></span> <span data-ttu-id="8c8c3-138">インポート エイリアスは、XML 名前空間プレフィックスとして使用できます XML リテラルまたは XML 軸のプロパティでのみ、プレフィックス修飾要素または属性名は、コードで、式として使用できます。</span><span class="sxs-lookup"><span data-stu-id="8c8c3-138">An import alias can be used as an expression in your code, whereas an XML namespace prefix can be used only in XML literals or XML axis properties as the prefix for a qualified element or attribute name.</span></span>  
  
### <a name="element-names"></a><span data-ttu-id="8c8c3-139">要素の名前</span><span class="sxs-lookup"><span data-stu-id="8c8c3-139">Element Names</span></span>  
 <span data-ttu-id="8c8c3-140">指定する場合`element`、表す必要がありますが、*コンテナー要素*、他の要素を含むことのできるプログラミング要素は、します。</span><span class="sxs-lookup"><span data-stu-id="8c8c3-140">If you supply `element`, it must represent a *container element*, that is, a programming element that can contain other elements.</span></span> <span data-ttu-id="8c8c3-141">コンテナー要素には、クラス、構造体、モジュール、インターフェイス、および列挙が含まれます。</span><span class="sxs-lookup"><span data-stu-id="8c8c3-141">Container elements include classes, structures, modules, interfaces, and enumerations.</span></span>  
  
 <span data-ttu-id="8c8c3-142">によって提供される要素のスコープ、`Imports`ステートメントが指定するかどうかに依存`element`します。</span><span class="sxs-lookup"><span data-stu-id="8c8c3-142">The scope of the elements made available by an `Imports` statement depends on whether you specify `element`.</span></span> <span data-ttu-id="8c8c3-143">のみを指定する場合`namespace`、すべて一意に、その名前空間のメンバーとその名前空間内のコンテナー要素のメンバーの名前、修飾なしで利用されます。</span><span class="sxs-lookup"><span data-stu-id="8c8c3-143">If you specify only `namespace`, all uniquely named members of that namespace, and members of container elements within that namespace, are available without qualification.</span></span> <span data-ttu-id="8c8c3-144">両方を指定する場合`namespace`と`element`、のみその要素のメンバーを修飾なしで利用できます。</span><span class="sxs-lookup"><span data-stu-id="8c8c3-144">If you specify both `namespace` and `element`, only the members of that element are available without qualification.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8c8c3-145">例</span><span class="sxs-lookup"><span data-stu-id="8c8c3-145">Example</span></span>  
 <span data-ttu-id="8c8c3-146">次の例では、C:\ ディレクトリ内のすべてのフォルダーを返しますを使用して、<xref:System.IO.DirectoryInfo>クラス。</span><span class="sxs-lookup"><span data-stu-id="8c8c3-146">The following example returns all the folders in the C:\ directory by using the <xref:System.IO.DirectoryInfo> class.</span></span>  
  
 <span data-ttu-id="8c8c3-147">コードを持たない`Imports`ファイルの上部にあるステートメント。</span><span class="sxs-lookup"><span data-stu-id="8c8c3-147">The code has no `Imports` statements at the top of the file.</span></span> <span data-ttu-id="8c8c3-148">そのため、 `DirectoryInfo`、 <xref:System.Text.StringBuilder>、および<xref:Microsoft.VisualBasic.ControlChars.CrLf>の参照がすべて完全修飾名前空間にします。</span><span class="sxs-lookup"><span data-stu-id="8c8c3-148">Therefore, the `DirectoryInfo`, <xref:System.Text.StringBuilder>, and <xref:Microsoft.VisualBasic.ControlChars.CrLf> references are all fully qualified with the namespaces.</span></span>  
  
 [!code-vb[VbVbalrStatements#152](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#152)]  
  
## <a name="example"></a><span data-ttu-id="8c8c3-149">例</span><span class="sxs-lookup"><span data-stu-id="8c8c3-149">Example</span></span>  
 <span data-ttu-id="8c8c3-150">次の例が含まれます`Imports`参照の名前空間のステートメント。</span><span class="sxs-lookup"><span data-stu-id="8c8c3-150">The following example includes `Imports` statements for the referenced namespaces.</span></span> <span data-ttu-id="8c8c3-151">そのため、型は、完全修飾名前空間にするのにはありません。</span><span class="sxs-lookup"><span data-stu-id="8c8c3-151">Therefore, the types do not have to be fully qualified with the namespaces.</span></span>  
  
 [!code-vb[VbVbalrStatements#153](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#153)]  
  
 [!code-vb[VbVbalrStatements#154](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#154)]  
  
## <a name="example"></a><span data-ttu-id="8c8c3-152">例</span><span class="sxs-lookup"><span data-stu-id="8c8c3-152">Example</span></span>  
 <span data-ttu-id="8c8c3-153">次の例が含まれます`Imports`参照の名前空間のエイリアスを作成するステートメント。</span><span class="sxs-lookup"><span data-stu-id="8c8c3-153">The following example includes `Imports` statements that create aliases for the referenced namespaces.</span></span> <span data-ttu-id="8c8c3-154">種類は、エイリアスで修飾されます。</span><span class="sxs-lookup"><span data-stu-id="8c8c3-154">The types are qualified with the aliases.</span></span>  
  
 [!code-vb[VbVbalrStatements#155](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#155)]  
  
 [!code-vb[VbVbalrStatements#156](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#156)]  
  
## <a name="example"></a><span data-ttu-id="8c8c3-155">例</span><span class="sxs-lookup"><span data-stu-id="8c8c3-155">Example</span></span>  
 <span data-ttu-id="8c8c3-156">次の例が含まれます`Imports`参照先の型のエイリアスを作成するステートメント。</span><span class="sxs-lookup"><span data-stu-id="8c8c3-156">The following example includes `Imports` statements that create aliases for the referenced types.</span></span> <span data-ttu-id="8c8c3-157">エイリアスを使用して、種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="8c8c3-157">Aliases are used to specify the types.</span></span>  
  
 [!code-vb[VbVbalrStatements#157](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#157)]  
  
 [!code-vb[VbVbalrStatements#158](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#158)]  
  
## <a name="see-also"></a><span data-ttu-id="8c8c3-158">関連項目</span><span class="sxs-lookup"><span data-stu-id="8c8c3-158">See also</span></span>

- [<span data-ttu-id="8c8c3-159">Namespace ステートメント</span><span class="sxs-lookup"><span data-stu-id="8c8c3-159">Namespace Statement</span></span>](../../../visual-basic/language-reference/statements/namespace-statement.md)
- [<span data-ttu-id="8c8c3-160">Visual Basic における名前空間</span><span class="sxs-lookup"><span data-stu-id="8c8c3-160">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)
- [<span data-ttu-id="8c8c3-161">参照と Imports ステートメント</span><span class="sxs-lookup"><span data-stu-id="8c8c3-161">References and the Imports Statement</span></span>](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)
- [<span data-ttu-id="8c8c3-162">Imports ステートメント (XML 名前空間)</span><span class="sxs-lookup"><span data-stu-id="8c8c3-162">Imports Statement (XML Namespace)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)
- [<span data-ttu-id="8c8c3-163">宣言された要素の参照</span><span class="sxs-lookup"><span data-stu-id="8c8c3-163">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
