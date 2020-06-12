---
title: 属性リスト
ms.date: 07/20/2015
helpviewer_keywords:
- attribute list
- attributes [Visual Basic], applying
ms.assetid: 5880073a-68a4-4b6b-8a07-ace32959a4e2
ms.openlocfilehash: f2400334182d373ea49c130fd17bc4f9943248d3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408446"
---
# <a name="attribute-list-visual-basic"></a><span data-ttu-id="94f26-102">属性リスト (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="94f26-102">Attribute List (Visual Basic)</span></span>
<span data-ttu-id="94f26-103">宣言されたプログラミング要素に適用する属性を指定します。</span><span class="sxs-lookup"><span data-stu-id="94f26-103">Specifies the attributes to be applied to a declared programming element.</span></span> <span data-ttu-id="94f26-104">複数の属性を指定するときは、コンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="94f26-104">Multiple attributes are separated by commas.</span></span> <span data-ttu-id="94f26-105">次に 1 つの属性の構文を示します。</span><span class="sxs-lookup"><span data-stu-id="94f26-105">Following is the syntax for one attribute.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94f26-106">構文</span><span class="sxs-lookup"><span data-stu-id="94f26-106">Syntax</span></span>  
  
```vb  
[ attributemodifier ] attributename [ ( attributearguments | attributeinitializer ) ]  
```  
  
## <a name="parts"></a><span data-ttu-id="94f26-107">指定項目</span><span class="sxs-lookup"><span data-stu-id="94f26-107">Parts</span></span>  
|||
|---|---|
|`attributemodifier`|<span data-ttu-id="94f26-108">ソース ファイルの先頭で適用される属性の場合は必須です。</span><span class="sxs-lookup"><span data-stu-id="94f26-108">Required for attributes applied at the beginning of a source file.</span></span> <span data-ttu-id="94f26-109">[Assembly](../modifiers/assembly.md) または [Module](../modifiers/module-keyword.md) を指定できます。</span><span class="sxs-lookup"><span data-stu-id="94f26-109">Can be [Assembly](../modifiers/assembly.md) or [Module](../modifiers/module-keyword.md).</span></span>|
|`attributename`| <span data-ttu-id="94f26-110">必須です。</span><span class="sxs-lookup"><span data-stu-id="94f26-110">Required.</span></span> <span data-ttu-id="94f26-111">属性の名前。</span><span class="sxs-lookup"><span data-stu-id="94f26-111">Name of the attribute.</span></span>|
|`attributearguments`|<span data-ttu-id="94f26-112">任意。</span><span class="sxs-lookup"><span data-stu-id="94f26-112">Optional.</span></span> <span data-ttu-id="94f26-113">この属性の位置引数の一覧です。</span><span class="sxs-lookup"><span data-stu-id="94f26-113">List of positional arguments for this attribute.</span></span> <span data-ttu-id="94f26-114">複数の引数はコンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="94f26-114">Multiple arguments are separated by commas.</span></span>|
|`attributeinitializer`|<span data-ttu-id="94f26-115">任意。</span><span class="sxs-lookup"><span data-stu-id="94f26-115">Optional.</span></span> <span data-ttu-id="94f26-116">この属性の変数またはプロパティ初期化子の一覧です。</span><span class="sxs-lookup"><span data-stu-id="94f26-116">List of variable or property initializers for this attribute.</span></span> <span data-ttu-id="94f26-117">複数の初期化子を指定するときは、コンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="94f26-117">Multiple initializers are separated by commas.</span></span>|
  
## <a name="remarks"></a><span data-ttu-id="94f26-118">Remarks</span><span class="sxs-lookup"><span data-stu-id="94f26-118">Remarks</span></span>  
 <span data-ttu-id="94f26-119">1 つまたは複数の属性を、ほぼすべてのプログラミング要素 (型、プロシージャ、プロパティなど) に適用できます。</span><span class="sxs-lookup"><span data-stu-id="94f26-119">You can apply one or more attributes to nearly any programming element (types, procedures, properties, and so forth).</span></span> <span data-ttu-id="94f26-120">属性は、アセンブリのメタデータに指定され、コードに注釈を付けたり、特定のプログラミング要素の使用方法を指定したりするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="94f26-120">Attributes appear in your assembly's metadata, and they can help you annotate your code or specify how to use a particular programming element.</span></span> <span data-ttu-id="94f26-121">Visual Basic と .NET Framework で定義された属性を適用したり、独自の属性を定義したりできます。</span><span class="sxs-lookup"><span data-stu-id="94f26-121">You can apply attributes defined by Visual Basic and the .NET Framework, and you can define your own attributes.</span></span>  

 <span data-ttu-id="94f26-122">属性を使用するタイミングの詳細については、[属性の概要](../../programming-guide/concepts/attributes/index.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="94f26-122">For more information on when to use attributes, see [Attributes overview](../../programming-guide/concepts/attributes/index.md).</span></span> <span data-ttu-id="94f26-123">属性名については、「[宣言された要素の名前](../../programming-guide/language-features/declared-elements/declared-element-names.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94f26-123">For information on attribute names, see [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="94f26-124">ルール</span><span class="sxs-lookup"><span data-stu-id="94f26-124">Rules</span></span>  
  
- <span data-ttu-id="94f26-125">**配置。**</span><span class="sxs-lookup"><span data-stu-id="94f26-125">**Placement.**</span></span> <span data-ttu-id="94f26-126">ほとんどの宣言されたプログラミング要素に属性を適用できます。</span><span class="sxs-lookup"><span data-stu-id="94f26-126">You can apply attributes to most declared programming elements.</span></span> <span data-ttu-id="94f26-127">1 つまたは複数の属性を適用するには、要素宣言の先頭に*属性ブロック*を配置します。</span><span class="sxs-lookup"><span data-stu-id="94f26-127">To apply one or more attributes, you place an *attribute block* at the beginning of the element declaration.</span></span> <span data-ttu-id="94f26-128">属性リストの各エントリは、適用する属性、および属性のこの呼び出しに使用する修飾子と引数を指定します。</span><span class="sxs-lookup"><span data-stu-id="94f26-128">Each entry in the attribute list specifies an attribute you wish to apply, and the modifier and arguments you are using for this invocation of the attribute.</span></span>  
  
- <span data-ttu-id="94f26-129">**山かっこ。**</span><span class="sxs-lookup"><span data-stu-id="94f26-129">**Angle Brackets.**</span></span> <span data-ttu-id="94f26-130">属性リストを指定する場合は、山かっこ ("`<`" および "`>`") で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="94f26-130">If you supply an attribute list, you must enclose it in angle brackets ("`<`" and "`>`").</span></span>  
  
- <span data-ttu-id="94f26-131">**宣言の一部。**</span><span class="sxs-lookup"><span data-stu-id="94f26-131">**Part of the Declaration.**</span></span> <span data-ttu-id="94f26-132">属性は、個別のステートメントではなく、要素宣言の一部である必要があります。</span><span class="sxs-lookup"><span data-stu-id="94f26-132">The attribute must be part of the element declaration, not a separate statement.</span></span> <span data-ttu-id="94f26-133">行連結シーケンス ("`_`") を使用して、宣言ステートメントを複数のソースコード行に拡張することができます。</span><span class="sxs-lookup"><span data-stu-id="94f26-133">You can use the line-continuation sequence (" `_`") to extend the declaration statement onto multiple source-code lines.</span></span>  
  
- <span data-ttu-id="94f26-134">**修飾子。**</span><span class="sxs-lookup"><span data-stu-id="94f26-134">**Modifiers.**</span></span> <span data-ttu-id="94f26-135">ソース ファイルの先頭でプログラミング要素に適用されるすべての属性に対して、属性修飾子 (`Assembly` または `Module`) が必要です。</span><span class="sxs-lookup"><span data-stu-id="94f26-135">An attribute modifier (`Assembly` or `Module`) is required on every attribute applied to a programming element at the beginning of a source file.</span></span> <span data-ttu-id="94f26-136">ソース ファイルの先頭にない要素に適用される属性では、属性修飾子は使用できません。</span><span class="sxs-lookup"><span data-stu-id="94f26-136">Attribute modifiers are not allowed on attributes applied to elements that are not at the beginning of a source file.</span></span>  
  
- <span data-ttu-id="94f26-137">**引数。**</span><span class="sxs-lookup"><span data-stu-id="94f26-137">**Arguments.**</span></span> <span data-ttu-id="94f26-138">属性のすべての位置引数は、変数またはプロパティ初期化子の前に記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="94f26-138">All positional arguments for an attribute must precede any variable or property initializers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="94f26-139">例</span><span class="sxs-lookup"><span data-stu-id="94f26-139">Example</span></span>  
 <span data-ttu-id="94f26-140">次の例では、<xref:System.Runtime.InteropServices.DllImportAttribute> 属性を `Function` プロシージャのスケルトン定義に適用しています。</span><span class="sxs-lookup"><span data-stu-id="94f26-140">The following example applies the <xref:System.Runtime.InteropServices.DllImportAttribute> attribute to a skeleton definition of a `Function` procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#1)]  
  
 <span data-ttu-id="94f26-141"><xref:System.Runtime.InteropServices.DllImportAttribute> は、属性付きプロシージャがアンマネージ ダイナミックリンク ライブラリ (DLL) のエントリ ポイントを表していることを示します。</span><span class="sxs-lookup"><span data-stu-id="94f26-141"><xref:System.Runtime.InteropServices.DllImportAttribute> indicates that the attributed procedure represents an entry point in an unmanaged dynamic-link library (DLL).</span></span> <span data-ttu-id="94f26-142">属性は、DLL 名を位置引数として指定し、その他の情報を変数初期化子として指定しています。</span><span class="sxs-lookup"><span data-stu-id="94f26-142">The attribute supplies the DLL name as a positional argument and the other information as variable initializers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94f26-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="94f26-143">See also</span></span>

- [<span data-ttu-id="94f26-144">Assembly</span><span class="sxs-lookup"><span data-stu-id="94f26-144">Assembly</span></span>](../modifiers/assembly.md)
- [<span data-ttu-id="94f26-145">Module \<keyword></span><span class="sxs-lookup"><span data-stu-id="94f26-145">Module \<keyword></span></span>](../modifiers/module-keyword.md)
- [<span data-ttu-id="94f26-146">属性の概要</span><span class="sxs-lookup"><span data-stu-id="94f26-146">Attributes overview</span></span>](../../programming-guide/concepts/attributes/index.md)
- [<span data-ttu-id="94f26-147">方法: コード内でステートメントを分割および連結する</span><span class="sxs-lookup"><span data-stu-id="94f26-147">How to: Break and Combine Statements in Code</span></span>](../../programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
