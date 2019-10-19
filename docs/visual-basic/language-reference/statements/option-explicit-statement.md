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
ms.openlocfilehash: 19ff8cf1dbcdb941e38f23be4cb68d3a5e5b83a8
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582577"
---
# <a name="option-explicit-statement-visual-basic"></a><span data-ttu-id="f3f76-102">Option Explicit ステートメント (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f3f76-102">Option Explicit Statement (Visual Basic)</span></span>
<span data-ttu-id="f3f76-103">ファイル内のすべての変数の明示的な宣言を強制的に実行するか、変数の暗黙的な宣言を許可します。</span><span class="sxs-lookup"><span data-stu-id="f3f76-103">Forces explicit declaration of all variables in a file, or allows implicit declarations of variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3f76-104">構文</span><span class="sxs-lookup"><span data-stu-id="f3f76-104">Syntax</span></span>  
  
```vb  
Option Explicit { On | Off }  
```  
  
## <a name="parts"></a><span data-ttu-id="f3f76-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="f3f76-105">Parts</span></span>  
 `On`  
 <span data-ttu-id="f3f76-106">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="f3f76-106">Optional.</span></span> <span data-ttu-id="f3f76-107">@No__t_0 チェックを有効にします。</span><span class="sxs-lookup"><span data-stu-id="f3f76-107">Enables `Option Explicit` checking.</span></span> <span data-ttu-id="f3f76-108">@No__t_0 または `Off` が指定されていない場合、既定値は `On` になります。</span><span class="sxs-lookup"><span data-stu-id="f3f76-108">If `On` or `Off` is not specified, the default is `On`.</span></span>  
  
 `Off`  
 <span data-ttu-id="f3f76-109">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="f3f76-109">Optional.</span></span> <span data-ttu-id="f3f76-110">@No__t_0 チェックを無効にします。</span><span class="sxs-lookup"><span data-stu-id="f3f76-110">Disables `Option Explicit` checking.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f3f76-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="f3f76-111">Remarks</span></span>  
 <span data-ttu-id="f3f76-112">@No__t_0 または `Option Explicit` がファイルに含まれている場合は、`Dim` または `ReDim` ステートメントを使用して、すべての変数を明示的に宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f3f76-112">When `Option Explicit On` or `Option Explicit` appears in a file, you must explicitly declare all variables by using the `Dim` or `ReDim` statements.</span></span> <span data-ttu-id="f3f76-113">宣言されていない変数名を使用しようとすると、コンパイル時にエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="f3f76-113">If you try to use an undeclared variable name, an error occurs at compile time.</span></span> <span data-ttu-id="f3f76-114">@No__t_0 ステートメントを使用すると、変数を暗黙的に宣言できます。</span><span class="sxs-lookup"><span data-stu-id="f3f76-114">The `Option Explicit Off` statement allows implicit declaration of variables.</span></span>  
  
 <span data-ttu-id="f3f76-115">使用した場合、`Option Explicit` ステートメントはファイル内で他のソース コード ステートメントよりも前に記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f3f76-115">If used, the `Option Explicit` statement must appear in a file before any other source code statements.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f3f76-116">@No__t_0 を `Off` に設定することは、通常はお勧めできません。</span><span class="sxs-lookup"><span data-stu-id="f3f76-116">Setting `Option Explicit` to `Off` is generally not a good practice.</span></span> <span data-ttu-id="f3f76-117">変数名のスペルを 1 か所以上間違えると、プログラムの実行時に予期しない結果を招く可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f3f76-117">You could misspell a variable name in one or more locations, which would cause unexpected results when the program is run.</span></span>  
  
## <a name="when-an-option-explicit-statement-is-not-present"></a><span data-ttu-id="f3f76-118">Option Explicit ステートメントが存在しない場合</span><span class="sxs-lookup"><span data-stu-id="f3f76-118">When an Option Explicit Statement Is Not Present</span></span>  
 <span data-ttu-id="f3f76-119">ソースコードに `Option Explicit` ステートメントが含まれていない場合は、[[コンパイル] ページ (プロジェクトデザイナー (Visual Basic))](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)の [**明示的な設定] オプション**が使用されます。</span><span class="sxs-lookup"><span data-stu-id="f3f76-119">If the source code does not contain an `Option Explicit` statement, the **Option Explicit** setting on the [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) is used.</span></span> <span data-ttu-id="f3f76-120">コマンドラインコンパイラを使用する場合は、 [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)コンパイラオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="f3f76-120">If the command-line compiler is used, the [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) compiler option is used.</span></span>  
  
#### <a name="to-set-option-explicit-in-the-ide"></a><span data-ttu-id="f3f76-121">IDE で Option Explicit を設定するには</span><span class="sxs-lookup"><span data-stu-id="f3f76-121">To set Option Explicit in the IDE</span></span>  
  
1. <span data-ttu-id="f3f76-122">**ソリューション エクスプローラー**でプロジェクトを選択します。</span><span class="sxs-lookup"><span data-stu-id="f3f76-122">In **Solution Explorer**, select a project.</span></span> <span data-ttu-id="f3f76-123">**[プロジェクト]** メニューの **[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f3f76-123">On the **Project** menu, click **Properties**.</span></span>  
  
2. <span data-ttu-id="f3f76-124">**[コンパイル]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f3f76-124">Click the **Compile** tab.</span></span>  
  
3. <span data-ttu-id="f3f76-125">**[Option Explicit]** ボックスに値を設定します。</span><span class="sxs-lookup"><span data-stu-id="f3f76-125">Set the value in the **Option Explicit** box.</span></span>  
  
 <span data-ttu-id="f3f76-126">新しいプロジェクトを作成する場合、 **[コンパイル]** タブの **[明示的]** な設定 オプションは、VB の **[既定値]** ダイアログボックスの **[明示的]** 設定に設定されています。</span><span class="sxs-lookup"><span data-stu-id="f3f76-126">When you create a new project, the **Option Explicit** setting on the **Compile** tab is set to the **Option Explicit** setting in the **VB Defaults** dialog box.</span></span> <span data-ttu-id="f3f76-127">VB の **[既定値]** ダイアログボックスにアクセスするには、 **[ツール]** メニューの **[オプション]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f3f76-127">To access the **VB Defaults** dialog box, on the **Tools** menu, click **Options**.</span></span> <span data-ttu-id="f3f76-128">**[オプション]** ダイアログ ボックスの **[プロジェクトおよびソリューション]** を展開し、 **[VISUAL BASIC の既定値]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f3f76-128">In the **Options** dialog box, expand **Projects and Solutions**, and then click **VB Defaults**.</span></span> <span data-ttu-id="f3f76-129">[VB の既定**値**] の初期の既定の設定は、`On` です。</span><span class="sxs-lookup"><span data-stu-id="f3f76-129">The initial default setting in **VB Defaults** is `On`.</span></span>  
  
#### <a name="to-set-option-explicit-on-the-command-line"></a><span data-ttu-id="f3f76-130">コマンドラインで Option Explicit を設定するには</span><span class="sxs-lookup"><span data-stu-id="f3f76-130">To set Option Explicit on the command line</span></span>  
  
- <span data-ttu-id="f3f76-131">**Vbc.exe**コマンドに[/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)コンパイラオプションを含めます。</span><span class="sxs-lookup"><span data-stu-id="f3f76-131">Include the [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) compiler option in the **vbc** command.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f3f76-132">例</span><span class="sxs-lookup"><span data-stu-id="f3f76-132">Example</span></span>  
 <span data-ttu-id="f3f76-133">次の例では、`Option Explicit` ステートメントを使用して、すべての変数の明示的な宣言を強制的に実行します。</span><span class="sxs-lookup"><span data-stu-id="f3f76-133">The following example uses the `Option Explicit` statement to force explicit declaration of all variables.</span></span> <span data-ttu-id="f3f76-134">宣言されていない変数を使用しようとすると、コンパイル時にエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="f3f76-134">Attempting to use an undeclared variable causes an error at compile time.</span></span>  
  
 [!code-vb[VbVbalrStatements#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#47)]  
  
 [!code-vb[VbVbalrStatements#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#48)]  
  
## <a name="see-also"></a><span data-ttu-id="f3f76-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="f3f76-135">See also</span></span>

- [<span data-ttu-id="f3f76-136">Dim ステートメント</span><span class="sxs-lookup"><span data-stu-id="f3f76-136">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)
- [<span data-ttu-id="f3f76-137">ReDim ステートメント</span><span class="sxs-lookup"><span data-stu-id="f3f76-137">ReDim Statement</span></span>](../../../visual-basic/language-reference/statements/redim-statement.md)
- [<span data-ttu-id="f3f76-138">Option Compare ステートメント</span><span class="sxs-lookup"><span data-stu-id="f3f76-138">Option Compare Statement</span></span>](../../../visual-basic/language-reference/statements/option-compare-statement.md)
- [<span data-ttu-id="f3f76-139">Option Strict ステートメント</span><span class="sxs-lookup"><span data-stu-id="f3f76-139">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="f3f76-140">/optioncompare</span><span class="sxs-lookup"><span data-stu-id="f3f76-140">/optioncompare</span></span>](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [<span data-ttu-id="f3f76-141">/optionexplicit</span><span class="sxs-lookup"><span data-stu-id="f3f76-141">/optionexplicit</span></span>](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)
- [<span data-ttu-id="f3f76-142">/optionstrict</span><span class="sxs-lookup"><span data-stu-id="f3f76-142">/optionstrict</span></span>](../../../visual-basic/reference/command-line-compiler/optionstrict.md)
- <span data-ttu-id="f3f76-143">[[Visual Basic の既定値] ([オプション] ダイアログ ボックス - [プロジェクト])](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)</span><span class="sxs-lookup"><span data-stu-id="f3f76-143">[Visual Basic Defaults, Projects, Options Dialog Box](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)</span></span>
