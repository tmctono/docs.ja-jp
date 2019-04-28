---
title: 名前 '<name>' は宣言されていません。
ms.date: 10/10/2018
f1_keywords:
- bc30451
- vbc30451
helpviewer_keywords:
- BC30451
ms.assetid: 765f099b-e21e-47c6-a906-a065444e56b3
ms.openlocfilehash: 3aadc49f91021409123550ba2712f1acf5b99d83
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61651026"
---
# <a name="name-name-is-not-declared"></a><span data-ttu-id="86269-102">名前 '\<名 >' が宣言されていません</span><span class="sxs-lookup"><span data-stu-id="86269-102">Name '\<name>' is not declared</span></span>
<span data-ttu-id="86269-103">ステートメントがプログラミング要素の場合を参照しますが、コンパイラは、正確な名前を持つ要素を見つけることができません。</span><span class="sxs-lookup"><span data-stu-id="86269-103">A statement refers to a programming element, but the compiler cannot find an element with that exact name.</span></span>  
  
 <span data-ttu-id="86269-104">**エラー ID:** BC30451</span><span class="sxs-lookup"><span data-stu-id="86269-104">**Error ID:** BC30451</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="86269-105">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="86269-105">To correct this error</span></span>  
  
1. <span data-ttu-id="86269-106">参照元のステートメントで名前のスペルを確認します。</span><span class="sxs-lookup"><span data-stu-id="86269-106">Check the spelling of the name in the referring statement.</span></span> <span data-ttu-id="86269-107">Visual Basic では、大文字と小文字が、スペルにその他の違いは完全に別の名前と見なされます。</span><span class="sxs-lookup"><span data-stu-id="86269-107">Visual Basic is case-insensitive, but any other variation in the spelling is regarded as a completely different name.</span></span> <span data-ttu-id="86269-108">アンダースコア (`_`) も名前の一部であり、スペルに含まれます。</span><span class="sxs-lookup"><span data-stu-id="86269-108">Note that the underscore (`_`) is part of the name and therefore part of the spelling.</span></span>  
  
2. <span data-ttu-id="86269-109">メンバー アクセス演算子があることを確認 (`.`) オブジェクトとメンバーの間。</span><span class="sxs-lookup"><span data-stu-id="86269-109">Check that you have the member access operator (`.`) between an object and its member.</span></span> <span data-ttu-id="86269-110">たとえば、 <xref:System.Windows.Forms.TextBox> という名前の `TextBox1`コントロールがある場合、このコントロールの <xref:System.Windows.Forms.TextBoxBase.Text%2A> プロパティにアクセスするには、「 `TextBox1.Text`」と入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="86269-110">For example, if you have a <xref:System.Windows.Forms.TextBox> control named `TextBox1`, to access its <xref:System.Windows.Forms.TextBoxBase.Text%2A> property you should type `TextBox1.Text`.</span></span> <span data-ttu-id="86269-111">代わりに「 `TextBox1Text`」と入力した場合、別の名前と見なされます。</span><span class="sxs-lookup"><span data-stu-id="86269-111">If instead you type `TextBox1Text`, you have created a different name.</span></span>  
  
3. <span data-ttu-id="86269-112">スペルが正しいことと、オブジェクト メンバー アクセスの構文が正しくの場合は、要素が宣言されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="86269-112">If the spelling is correct and the syntax of any object member access is correct, verify that the element has been declared.</span></span> <span data-ttu-id="86269-113">詳細については、次を参照してください。 [Declared Elements](../../programming-guide/language-features/declared-elements/index.md)します。</span><span class="sxs-lookup"><span data-stu-id="86269-113">For more information, see [Declared Elements](../../programming-guide/language-features/declared-elements/index.md).</span></span>  
  
4. <span data-ttu-id="86269-114">プログラミング要素が宣言されている場合は、スコープ内にあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="86269-114">If the programming element has been declared, check that it is in scope.</span></span> <span data-ttu-id="86269-115">参照元のステートメントがプログラミング要素が宣言領域の外側にある場合は、要素名を修飾する必要があります。</span><span class="sxs-lookup"><span data-stu-id="86269-115">If the referring statement is outside the region declaring the programming element, you might need to qualify the element name.</span></span> <span data-ttu-id="86269-116">詳細については、「 [Scope in Visual Basic](../../programming-guide/language-features/declared-elements/scope.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="86269-116">For more information, see [Scope in Visual Basic](../../programming-guide/language-features/declared-elements/scope.md).</span></span>  

5. <span data-ttu-id="86269-117">完全修飾型または型およびメンバーの名前を使用しない場合 (たとえば、コードがプロパティとして`MethodInfo.Name`の代わりに`System.Reflection.MethodInfo.Name`)、追加、 [Imports ステートメント](../statements/imports-statement-net-namespace-and-type.md)します。</span><span class="sxs-lookup"><span data-stu-id="86269-117">If you are not using a fully qualified type or type and member name (for example, your code refers to a property as `MethodInfo.Name` instead of `System.Reflection.MethodInfo.Name`), add an [Imports statement](../statements/imports-statement-net-namespace-and-type.md).</span></span>

6. <span data-ttu-id="86269-118">SDK スタイル プロジェクトをコンパイルしようとしているかどうか (のプロジェクトを\*.vbproj ファイル、行で始まる`<Project Sdk="Microsoft.NET.Sdk">`)、およびエラー メッセージが参照型または Microsoft.VisualBasic.dll アセンブリ内のメンバーに、アプリケーションへの構成Visual Basic ランタイム ライブラリへの参照を使用してコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="86269-118">If you are attempting to compile an SDK-style project (a project with a \*.vbproj file that begins with the line `<Project Sdk="Microsoft.NET.Sdk">`), and the error message refers to a type or member in the Microsoft.VisualBasic.dll assembly, configure your application to compile with a reference to the Visual Basic Runtime Library.</span></span> <span data-ttu-id="86269-119">既定では、ライブラリのサブセットは SDK スタイル プロジェクトでアセンブリに埋め込まれます。</span><span class="sxs-lookup"><span data-stu-id="86269-119">By default, a subset of the library is embedded in your assembly in an SDK-style project.</span></span>

   <span data-ttu-id="86269-120">たとえば、次の例のため、コンパイルが失敗した、<xref:Microsoft.VisualBasic.CompilerServices.Conversions.ToInteger%2A?displayProperty=fullName>メソッドが見つかりません。</span><span class="sxs-lookup"><span data-stu-id="86269-120">For example, the following example fails to compile because the <xref:Microsoft.VisualBasic.CompilerServices.Conversions.ToInteger%2A?displayProperty=fullName> method cannot be found.</span></span> <span data-ttu-id="86269-121">アプリケーションに含まれている Visual Basic ランタイムのサブセットでは埋め込まれません。</span><span class="sxs-lookup"><span data-stu-id="86269-121">It is not embedded in the subset of the Visual Basic Runtime included with your application.</span></span>  

   [!code-vb[BC30451](~/samples/snippets/visualbasic/language-reference/error-messages/bc30451/program1.vb)]

   <span data-ttu-id="86269-122">このエラーに対処するための追加、`<VBRuntime>Default</VBRuntime>`要素をプロジェクトに`<PropertyGroup>`セクションを次の Visual Basic プロジェクト ファイルに示します。</span><span class="sxs-lookup"><span data-stu-id="86269-122">To address this error, add the `<VBRuntime>Default</VBRuntime>` element to the projects `<PropertyGroup>` section, as the following Visual Basic project file shows.</span></span>

   [!code-vb[BC30451](~/samples/snippets/visualbasic/language-reference/error-messages/bc30451/vbruntime.vbproj?highlight=6)]

## <a name="see-also"></a><span data-ttu-id="86269-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="86269-123">See also</span></span>

- [<span data-ttu-id="86269-124">宣言と定数の概要</span><span class="sxs-lookup"><span data-stu-id="86269-124">Declarations and Constants Summary</span></span>](../../../visual-basic/language-reference/keywords/declarations-and-constants-summary.md)
- [<span data-ttu-id="86269-125">Visual Basic の名前付け規則</span><span class="sxs-lookup"><span data-stu-id="86269-125">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
- [<span data-ttu-id="86269-126">Declared Element Names</span><span class="sxs-lookup"><span data-stu-id="86269-126">Declared Element Names</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="86269-127">宣言された要素の参照</span><span class="sxs-lookup"><span data-stu-id="86269-127">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
