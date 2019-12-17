---
title: -nowarn
ms.date: 07/20/2015
helpviewer_keywords:
- nowarn compiler option [Visual Basic]
- /nowarn compiler option [Visual Basic]
- -nowarn compiler option [Visual Basic]
ms.assetid: 7ebf2106-0652-4fdc-bf60-70fc86465d83
ms.openlocfilehash: 880fdf4931dadea547d64d0506bd3e978956468e
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005397"
---
# <a name="-nowarn"></a><span data-ttu-id="2cf71-102">-nowarn</span><span class="sxs-lookup"><span data-stu-id="2cf71-102">-nowarn</span></span>
<span data-ttu-id="2cf71-103">警告を生成するコンパイラの機能を無効にします。</span><span class="sxs-lookup"><span data-stu-id="2cf71-103">Suppresses the compiler's ability to generate warnings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2cf71-104">構文</span><span class="sxs-lookup"><span data-stu-id="2cf71-104">Syntax</span></span>  
  
```console  
-nowarn[:numberList]  
```  
  
## <a name="arguments"></a><span data-ttu-id="2cf71-105">引数</span><span class="sxs-lookup"><span data-stu-id="2cf71-105">Arguments</span></span>  
  
|<span data-ttu-id="2cf71-106">項目</span><span class="sxs-lookup"><span data-stu-id="2cf71-106">Term</span></span>|<span data-ttu-id="2cf71-107">定義</span><span class="sxs-lookup"><span data-stu-id="2cf71-107">Definition</span></span>|  
|---|---|  
|`numberList`|<span data-ttu-id="2cf71-108">任意。</span><span class="sxs-lookup"><span data-stu-id="2cf71-108">Optional.</span></span> <span data-ttu-id="2cf71-109">コンパイラによって抑制される警告 ID 番号のコンマ区切りの一覧。</span><span class="sxs-lookup"><span data-stu-id="2cf71-109">Comma-delimited list of the warning ID numbers that the compiler should suppress.</span></span> <span data-ttu-id="2cf71-110">警告 Id が指定されていない場合は、すべての警告が抑制されます。</span><span class="sxs-lookup"><span data-stu-id="2cf71-110">If the warning IDs are not specified, all warnings are suppressed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2cf71-111">コメント</span><span class="sxs-lookup"><span data-stu-id="2cf71-111">Remarks</span></span>  
 <span data-ttu-id="2cf71-112">@No__t-0 オプションを指定すると、コンパイラは警告を生成しません。</span><span class="sxs-lookup"><span data-stu-id="2cf71-112">The `-nowarn` option causes the compiler to not generate warnings.</span></span> <span data-ttu-id="2cf71-113">個々の警告を非表示にするには、警告 ID をコロンの後の `-nowarn` オプションに指定します。</span><span class="sxs-lookup"><span data-stu-id="2cf71-113">To suppress an individual warning, supply the warning ID to the `-nowarn` option following the colon.</span></span> <span data-ttu-id="2cf71-114">複数の警告番号はコンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="2cf71-114">Separate multiple warning numbers with commas.</span></span>  
  
 <span data-ttu-id="2cf71-115">警告 id の数値部分のみを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2cf71-115">You need to specify only the numeric part of the warning identifier.</span></span> <span data-ttu-id="2cf71-116">たとえば、BC42024 を抑制する場合は、使用されていないローカル変数の警告として、`-nowarn:42024` を指定します。</span><span class="sxs-lookup"><span data-stu-id="2cf71-116">For example, if you want to suppress BC42024, the warning for unused local variables, specify `-nowarn:42024`.</span></span>  
  
 <span data-ttu-id="2cf71-117">警告 ID 番号の詳細については、「[Visual Basic での警告の構成](/visualstudio/ide/configuring-warnings-in-visual-basic)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2cf71-117">For more information on the warning ID numbers, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
|<span data-ttu-id="2cf71-118">Visual Studio 統合開発環境で-nowarn を設定するには</span><span class="sxs-lookup"><span data-stu-id="2cf71-118">To set -nowarn in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="2cf71-119">1. **ソリューション エクスプローラー**でプロジェクトを選択します。</span><span class="sxs-lookup"><span data-stu-id="2cf71-119">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="2cf71-120">**[プロジェクト]** メニューの **[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2cf71-120">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="2cf71-121">2. **[コンパイル]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="2cf71-121">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="2cf71-122">3.すべての警告を無効にするには、[**すべての警告を無効**にする] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="2cf71-122">3.  Select the **Disable all warnings** check box to disable all warnings.</span></span><br />     <span data-ttu-id="2cf71-123">または</span><span class="sxs-lookup"><span data-stu-id="2cf71-123">- or -</span></span><br />     <span data-ttu-id="2cf71-124">特定の警告を無効にするには、警告の隣にあるドロップダウンリストから **[なし]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2cf71-124">To disable a particular warning, click **None** from the drop-down list adjacent to the warning.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="2cf71-125">例</span><span class="sxs-lookup"><span data-stu-id="2cf71-125">Example</span></span>  
 <span data-ttu-id="2cf71-126">次のコードは `T2.vb` をコンパイルし、警告を表示しません。</span><span class="sxs-lookup"><span data-stu-id="2cf71-126">The following code compiles `T2.vb` and does not display any warnings.</span></span>  
  
```console
vbc -nowarn t2.vb  
```  
  
## <a name="example"></a><span data-ttu-id="2cf71-127">例</span><span class="sxs-lookup"><span data-stu-id="2cf71-127">Example</span></span>  
 <span data-ttu-id="2cf71-128">次のコードは `T2.vb` をコンパイルし、使用されていないローカル変数 (42024) の警告を表示しません。</span><span class="sxs-lookup"><span data-stu-id="2cf71-128">The following code compiles `T2.vb` and does not display the warnings for unused local variables (42024).</span></span>  
  
```console
vbc -nowarn:42024 t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="2cf71-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="2cf71-129">See also</span></span>

- [<span data-ttu-id="2cf71-130">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="2cf71-130">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="2cf71-131">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="2cf71-131">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="2cf71-132">Visual Basic での警告の構成</span><span class="sxs-lookup"><span data-stu-id="2cf71-132">Configuring Warnings in Visual Basic</span></span>](/visualstudio/ide/configuring-warnings-in-visual-basic)
