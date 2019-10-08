---
title: 属性リスト (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- attribute list
- attributes [Visual Basic], applying
ms.assetid: 5880073a-68a4-4b6b-8a07-ace32959a4e2
ms.openlocfilehash: 771757afe214919649e13fda3990e1154be8e1e1
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004530"
---
# <a name="attribute-list-visual-basic"></a><span data-ttu-id="557c3-102">属性リスト (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="557c3-102">Attribute List (Visual Basic)</span></span>
<span data-ttu-id="557c3-103">宣言されたプログラミング要素に適用する属性を指定します。</span><span class="sxs-lookup"><span data-stu-id="557c3-103">Specifies the attributes to be applied to a declared programming element.</span></span> <span data-ttu-id="557c3-104">複数の属性を指定するときは、コンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="557c3-104">Multiple attributes are separated by commas.</span></span> <span data-ttu-id="557c3-105">1つの属性の構文を次に示します。</span><span class="sxs-lookup"><span data-stu-id="557c3-105">Following is the syntax for one attribute.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="557c3-106">構文</span><span class="sxs-lookup"><span data-stu-id="557c3-106">Syntax</span></span>  
  
```vb  
[ attributemodifier ] attributename [ ( attributearguments | attributeinitializer ) ]  
```  
  
## <a name="parts"></a><span data-ttu-id="557c3-107">指定項目</span><span class="sxs-lookup"><span data-stu-id="557c3-107">Parts</span></span>  
|||
|---|---|
|`attributemodifier`|<span data-ttu-id="557c3-108">ソースファイルの先頭で適用される属性に必要です。</span><span class="sxs-lookup"><span data-stu-id="557c3-108">Required for attributes applied at the beginning of a source file.</span></span> <span data-ttu-id="557c3-109">[アセンブリ](../../../visual-basic/language-reference/modifiers/assembly.md)または[モジュール](../../../visual-basic/language-reference/modifiers/module-keyword.md)を指定できます。</span><span class="sxs-lookup"><span data-stu-id="557c3-109">Can be [Assembly](../../../visual-basic/language-reference/modifiers/assembly.md) or [Module](../../../visual-basic/language-reference/modifiers/module-keyword.md).</span></span>|
|`attributename`| <span data-ttu-id="557c3-110">必須。</span><span class="sxs-lookup"><span data-stu-id="557c3-110">Required.</span></span> <span data-ttu-id="557c3-111">属性の名前。</span><span class="sxs-lookup"><span data-stu-id="557c3-111">Name of the attribute.</span></span>|
|`attributearguments`|<span data-ttu-id="557c3-112">任意。</span><span class="sxs-lookup"><span data-stu-id="557c3-112">Optional.</span></span> <span data-ttu-id="557c3-113">この属性の位置指定引数の一覧。</span><span class="sxs-lookup"><span data-stu-id="557c3-113">List of positional arguments for this attribute.</span></span> <span data-ttu-id="557c3-114">複数の引数は、コンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="557c3-114">Multiple arguments are separated by commas.</span></span>|
|`attributeinitializer`|<span data-ttu-id="557c3-115">任意。</span><span class="sxs-lookup"><span data-stu-id="557c3-115">Optional.</span></span> <span data-ttu-id="557c3-116">この属性の変数またはプロパティ初期化子のリスト。</span><span class="sxs-lookup"><span data-stu-id="557c3-116">List of variable or property initializers for this attribute.</span></span> <span data-ttu-id="557c3-117">複数の初期化子は、コンマで区切られます。</span><span class="sxs-lookup"><span data-stu-id="557c3-117">Multiple initializers are separated by commas.</span></span>|
  
## <a name="remarks"></a><span data-ttu-id="557c3-118">コメント</span><span class="sxs-lookup"><span data-stu-id="557c3-118">Remarks</span></span>  
 <span data-ttu-id="557c3-119">1つまたは複数の属性を、ほぼすべてのプログラミング要素 (型、プロシージャ、プロパティなど) に適用できます。</span><span class="sxs-lookup"><span data-stu-id="557c3-119">You can apply one or more attributes to nearly any programming element (types, procedures, properties, and so forth).</span></span> <span data-ttu-id="557c3-120">属性は、アセンブリのメタデータに表示され、コードに注釈を付けたり、特定のプログラミング要素の使用方法を指定したりするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="557c3-120">Attributes appear in your assembly's metadata, and they can help you annotate your code or specify how to use a particular programming element.</span></span> <span data-ttu-id="557c3-121">Visual Basic と .NET Framework で定義された属性を適用し、独自の属性を定義することができます。</span><span class="sxs-lookup"><span data-stu-id="557c3-121">You can apply attributes defined by Visual Basic and the .NET Framework, and you can define your own attributes.</span></span>  

 <span data-ttu-id="557c3-122">属性を使用する場合の詳細については、「[属性の概要](../../../visual-basic/programming-guide/concepts/attributes/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="557c3-122">For more information on when to use attributes, see [Attributes overview](../../../visual-basic/programming-guide/concepts/attributes/index.md).</span></span> <span data-ttu-id="557c3-123">属性名の詳細については、「宣言された[要素名](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="557c3-123">For information on attribute names, see [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="557c3-124">ルール</span><span class="sxs-lookup"><span data-stu-id="557c3-124">Rules</span></span>  
  
- <span data-ttu-id="557c3-125">**場所.**</span><span class="sxs-lookup"><span data-stu-id="557c3-125">**Placement.**</span></span> <span data-ttu-id="557c3-126">最も宣言されたプログラミング要素に属性を適用できます。</span><span class="sxs-lookup"><span data-stu-id="557c3-126">You can apply attributes to most declared programming elements.</span></span> <span data-ttu-id="557c3-127">1つまたは複数の属性を適用するには、要素宣言の先頭に*属性ブロック*を配置します。</span><span class="sxs-lookup"><span data-stu-id="557c3-127">To apply one or more attributes, you place an *attribute block* at the beginning of the element declaration.</span></span> <span data-ttu-id="557c3-128">属性リストの各エントリは、適用する属性、および属性のこの呼び出しに使用する修飾子と引数を指定します。</span><span class="sxs-lookup"><span data-stu-id="557c3-128">Each entry in the attribute list specifies an attribute you wish to apply, and the modifier and arguments you are using for this invocation of the attribute.</span></span>  
  
- <span data-ttu-id="557c3-129">**山かっこ。**</span><span class="sxs-lookup"><span data-stu-id="557c3-129">**Angle Brackets.**</span></span> <span data-ttu-id="557c3-130">属性リストを指定する場合は、山かっこ ("`<`" と "`>`") で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="557c3-130">If you supply an attribute list, you must enclose it in angle brackets ("`<`" and "`>`").</span></span>  
  
- <span data-ttu-id="557c3-131">**宣言の一部。**</span><span class="sxs-lookup"><span data-stu-id="557c3-131">**Part of the Declaration.**</span></span> <span data-ttu-id="557c3-132">属性は、個別のステートメントではなく、要素宣言の一部である必要があります。</span><span class="sxs-lookup"><span data-stu-id="557c3-132">The attribute must be part of the element declaration, not a separate statement.</span></span> <span data-ttu-id="557c3-133">行連結シーケンス ("`_`") を使用して、宣言ステートメントを複数のソースコード行に拡張することができます。</span><span class="sxs-lookup"><span data-stu-id="557c3-133">You can use the line-continuation sequence (" `_`") to extend the declaration statement onto multiple source-code lines.</span></span>  
  
- <span data-ttu-id="557c3-134">**ド.**</span><span class="sxs-lookup"><span data-stu-id="557c3-134">**Modifiers.**</span></span> <span data-ttu-id="557c3-135">ソースファイルの先頭でプログラミング要素に適用されるすべての属性には、属性修飾子 (`Assembly` または `Module`) が必要です。</span><span class="sxs-lookup"><span data-stu-id="557c3-135">An attribute modifier (`Assembly` or `Module`) is required on every attribute applied to a programming element at the beginning of a source file.</span></span> <span data-ttu-id="557c3-136">ソースファイルの先頭にない要素に適用される属性では、属性修飾子は使用できません。</span><span class="sxs-lookup"><span data-stu-id="557c3-136">Attribute modifiers are not allowed on attributes applied to elements that are not at the beginning of a source file.</span></span>  
  
- <span data-ttu-id="557c3-137">**数値.**</span><span class="sxs-lookup"><span data-stu-id="557c3-137">**Arguments.**</span></span> <span data-ttu-id="557c3-138">属性のすべての位置指定引数は、変数またはプロパティ初期化子の前に記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="557c3-138">All positional arguments for an attribute must precede any variable or property initializers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="557c3-139">例</span><span class="sxs-lookup"><span data-stu-id="557c3-139">Example</span></span>  
 <span data-ttu-id="557c3-140">次の例では、<xref:System.Runtime.InteropServices.DllImportAttribute> 属性を `Function` プロシージャのスケルトン定義に適用します。</span><span class="sxs-lookup"><span data-stu-id="557c3-140">The following example applies the <xref:System.Runtime.InteropServices.DllImportAttribute> attribute to a skeleton definition of a `Function` procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#1)]  
  
 <span data-ttu-id="557c3-141"><xref:System.Runtime.InteropServices.DllImportAttribute> は、属性付きプロシージャがアンマネージダイナミックリンクライブラリ (DLL) のエントリポイントを表すことを示します。</span><span class="sxs-lookup"><span data-stu-id="557c3-141"><xref:System.Runtime.InteropServices.DllImportAttribute> indicates that the attributed procedure represents an entry point in an unmanaged dynamic-link library (DLL).</span></span> <span data-ttu-id="557c3-142">属性は、DLL 名を位置引数として指定し、その他の情報を変数初期化子として提供します。</span><span class="sxs-lookup"><span data-stu-id="557c3-142">The attribute supplies the DLL name as a positional argument and the other information as variable initializers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="557c3-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="557c3-143">See also</span></span>

- [<span data-ttu-id="557c3-144">Assembly</span><span class="sxs-lookup"><span data-stu-id="557c3-144">Assembly</span></span>](../../../visual-basic/language-reference/modifiers/assembly.md)
- [<span data-ttu-id="557c3-145">Module \<キーワード></span><span class="sxs-lookup"><span data-stu-id="557c3-145">Module \<keyword></span></span>](../../../visual-basic/language-reference/modifiers/module-keyword.md)
- [<span data-ttu-id="557c3-146">属性の概要</span><span class="sxs-lookup"><span data-stu-id="557c3-146">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)
- [<span data-ttu-id="557c3-147">2 つのオブジェクトが等しいかどうかをテストする方法コード内でステートメントを分割および連結する</span><span class="sxs-lookup"><span data-stu-id="557c3-147">How to: Break and Combine Statements in Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
