---
title: Option Explicit ステートメント (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Explicit
- vb.OptionExplicit
helpviewer_keywords:
- declaring variables [Visual Basic], explicit
- forced variable declaration in Option Explicit statement [Visual Basic]
- Explicit keyword
- explicit variable declaration
- Option Explicit statement [Visual Basic]
ms.assetid: e82ac1ad-2cd3-49b2-b985-8bcf016f3fcc
ms.openlocfilehash: 0a319ba4259e66ed9a37aa2de9e97d2335b78663
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61784047"
---
# <a name="option-explicit-statement-visual-basic"></a><span data-ttu-id="9a644-102">Option Explicit ステートメント (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9a644-102">Option Explicit Statement (Visual Basic)</span></span>
<span data-ttu-id="9a644-103">ファイルでは、すべての変数の明示的な宣言を強制または変数の暗黙的な宣言を許可します。</span><span class="sxs-lookup"><span data-stu-id="9a644-103">Forces explicit declaration of all variables in a file, or allows implicit declarations of variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a644-104">構文</span><span class="sxs-lookup"><span data-stu-id="9a644-104">Syntax</span></span>  
  
```  
Option Explicit { On | Off }  
```  
  
## <a name="parts"></a><span data-ttu-id="9a644-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="9a644-105">Parts</span></span>  
 `On`  
 <span data-ttu-id="9a644-106">任意。</span><span class="sxs-lookup"><span data-stu-id="9a644-106">Optional.</span></span> <span data-ttu-id="9a644-107">により、`Option Explicit`をチェックします。</span><span class="sxs-lookup"><span data-stu-id="9a644-107">Enables `Option Explicit` checking.</span></span> <span data-ttu-id="9a644-108">場合`On`または`Off`が指定されていない、既定値は`On`します。</span><span class="sxs-lookup"><span data-stu-id="9a644-108">If `On` or `Off` is not specified, the default is `On`.</span></span>  
  
 `Off`  
 <span data-ttu-id="9a644-109">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="9a644-109">Optional.</span></span> <span data-ttu-id="9a644-110">無効にします`Option Explicit`をチェックします。</span><span class="sxs-lookup"><span data-stu-id="9a644-110">Disables `Option Explicit` checking.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9a644-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="9a644-111">Remarks</span></span>  
 <span data-ttu-id="9a644-112">ときに`Option Explicit On`または`Option Explicit`を使用してすべての変数を明示的に宣言する必要がありますが、ファイルに表示されます、`Dim`または`ReDim`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="9a644-112">When `Option Explicit On` or `Option Explicit` appears in a file, you must explicitly declare all variables by using the `Dim` or `ReDim` statements.</span></span> <span data-ttu-id="9a644-113">宣言されていない変数名を使用しようとすると、コンパイル時にエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="9a644-113">If you try to use an undeclared variable name, an error occurs at compile time.</span></span> <span data-ttu-id="9a644-114">`Option Explicit Off`ステートメントは、変数の暗黙的な宣言を使用できます。</span><span class="sxs-lookup"><span data-stu-id="9a644-114">The `Option Explicit Off` statement allows implicit declaration of variables.</span></span>  
  
 <span data-ttu-id="9a644-115">使用した場合、`Option Explicit` ステートメントはファイル内で他のソース コード ステートメントよりも前に記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9a644-115">If used, the `Option Explicit` statement must appear in a file before any other source code statements.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9a644-116">設定`Option Explicit`に`Off`は一般にないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9a644-116">Setting `Option Explicit` to `Off` is generally not a good practice.</span></span> <span data-ttu-id="9a644-117">変数名のスペルを 1 か所以上間違えると、プログラムの実行時に予期しない結果を招く可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9a644-117">You could misspell a variable name in one or more locations, which would cause unexpected results when the program is run.</span></span>  
  
## <a name="when-an-option-explicit-statement-is-not-present"></a><span data-ttu-id="9a644-118">ときに Option Explicit のステートメントが存在しません。</span><span class="sxs-lookup"><span data-stu-id="9a644-118">When an Option Explicit Statement Is Not Present</span></span>  
 <span data-ttu-id="9a644-119">ソース コードが含まれていない場合、`Option Explicit`ステートメントでは、 **Option Explicit**の設定、 [[コンパイル] ページ、プロジェクト デザイナー (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)使用されます。</span><span class="sxs-lookup"><span data-stu-id="9a644-119">If the source code does not contain an `Option Explicit` statement, the **Option Explicit** setting on the [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) is used.</span></span> <span data-ttu-id="9a644-120">コマンド ライン コンパイラを使用する場合、 [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)コンパイラ オプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="9a644-120">If the command-line compiler is used, the [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) compiler option is used.</span></span>  
  
#### <a name="to-set-option-explicit-in-the-ide"></a><span data-ttu-id="9a644-121">IDE で Option Explicit を設定するには</span><span class="sxs-lookup"><span data-stu-id="9a644-121">To set Option Explicit in the IDE</span></span>  
  
1. <span data-ttu-id="9a644-122">**ソリューション エクスプローラー**でプロジェクトを選択します。</span><span class="sxs-lookup"><span data-stu-id="9a644-122">In **Solution Explorer**, select a project.</span></span> <span data-ttu-id="9a644-123">**[プロジェクト]** メニューの **[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9a644-123">On the **Project** menu, click **Properties**.</span></span>  
  
2. <span data-ttu-id="9a644-124">**[コンパイル]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="9a644-124">Click the **Compile** tab.</span></span>  
  
3. <span data-ttu-id="9a644-125">値を設定、 **Option Explicit**ボックス。</span><span class="sxs-lookup"><span data-stu-id="9a644-125">Set the value in the **Option Explicit** box.</span></span>  
  
 <span data-ttu-id="9a644-126">新しいプロジェクトを作成するときに、 **Option Explicit**の設定、**コンパイル**タブに設定されている、 **Option Explicit**での設定、 **VBの既定値** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="9a644-126">When you create a new project, the **Option Explicit** setting on the **Compile** tab is set to the **Option Explicit** setting in the **VB Defaults** dialog box.</span></span> <span data-ttu-id="9a644-127">アクセスする、**既定値は VB**  ダイアログ ボックスで、**ツール** メニューのをクリックして**オプション**。</span><span class="sxs-lookup"><span data-stu-id="9a644-127">To access the **VB Defaults** dialog box, on the **Tools** menu, click **Options**.</span></span> <span data-ttu-id="9a644-128">**[オプション]** ダイアログ ボックスの **[プロジェクトおよびソリューション]** を展開し、**[VISUAL BASIC の既定値]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9a644-128">In the **Options** dialog box, expand **Projects and Solutions**, and then click **VB Defaults**.</span></span> <span data-ttu-id="9a644-129">初期の既定の設定で**VB の既定値**は`On`します。</span><span class="sxs-lookup"><span data-stu-id="9a644-129">The initial default setting in **VB Defaults** is `On`.</span></span>  
  
#### <a name="to-set-option-explicit-on-the-command-line"></a><span data-ttu-id="9a644-130">コマンドラインで Option Explicit を設定するには</span><span class="sxs-lookup"><span data-stu-id="9a644-130">To set Option Explicit on the command line</span></span>  
  
- <span data-ttu-id="9a644-131">含める、 [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)コンパイラ オプションで、 **vbc**コマンド。</span><span class="sxs-lookup"><span data-stu-id="9a644-131">Include the [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) compiler option in the **vbc** command.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9a644-132">例</span><span class="sxs-lookup"><span data-stu-id="9a644-132">Example</span></span>  
 <span data-ttu-id="9a644-133">次の例では、`Option Explicit`すべての変数の明示的な宣言を強制するステートメント。</span><span class="sxs-lookup"><span data-stu-id="9a644-133">The following example uses the `Option Explicit` statement to force explicit declaration of all variables.</span></span> <span data-ttu-id="9a644-134">宣言されていない変数を使用すると場合、コンパイル時にエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="9a644-134">Attempting to use an undeclared variable causes an error at compile time.</span></span>  
  
 [!code-vb[VbVbalrStatements#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#47)]  
  
 [!code-vb[VbVbalrStatements#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#48)]  
  
## <a name="see-also"></a><span data-ttu-id="9a644-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="9a644-135">See also</span></span>

- [<span data-ttu-id="9a644-136">Dim ステートメント</span><span class="sxs-lookup"><span data-stu-id="9a644-136">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)
- [<span data-ttu-id="9a644-137">ReDim ステートメント</span><span class="sxs-lookup"><span data-stu-id="9a644-137">ReDim Statement</span></span>](../../../visual-basic/language-reference/statements/redim-statement.md)
- [<span data-ttu-id="9a644-138">Option Compare ステートメント</span><span class="sxs-lookup"><span data-stu-id="9a644-138">Option Compare Statement</span></span>](../../../visual-basic/language-reference/statements/option-compare-statement.md)
- [<span data-ttu-id="9a644-139">Option Strict ステートメント</span><span class="sxs-lookup"><span data-stu-id="9a644-139">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="9a644-140">/optioncompare</span><span class="sxs-lookup"><span data-stu-id="9a644-140">/optioncompare</span></span>](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [<span data-ttu-id="9a644-141">/optionexplicit</span><span class="sxs-lookup"><span data-stu-id="9a644-141">/optionexplicit</span></span>](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)
- [<span data-ttu-id="9a644-142">/optionstrict</span><span class="sxs-lookup"><span data-stu-id="9a644-142">/optionstrict</span></span>](../../../visual-basic/reference/command-line-compiler/optionstrict.md)
- <span data-ttu-id="9a644-143">[[Visual Basic の既定値] ([オプション] ダイアログ ボックス - [プロジェクト])](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)</span><span class="sxs-lookup"><span data-stu-id="9a644-143">[Visual Basic Defaults, Projects, Options Dialog Box](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)</span></span>
