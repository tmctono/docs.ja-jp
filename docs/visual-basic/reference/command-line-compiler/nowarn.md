---
title: -nowarn
ms.date: 07/20/2015
helpviewer_keywords:
- nowarn compiler option [Visual Basic]
- /nowarn compiler option [Visual Basic]
- -nowarn compiler option [Visual Basic]
ms.assetid: 7ebf2106-0652-4fdc-bf60-70fc86465d83
ms.openlocfilehash: cde96fff975a65d6303ee62e6a811bfd83d5ff97
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "91097684"
---
# <a name="-nowarn"></a><span data-ttu-id="0ac73-102">-nowarn</span><span class="sxs-lookup"><span data-stu-id="0ac73-102">-nowarn</span></span>

<span data-ttu-id="0ac73-103">警告を生成するコンパイラの機能を無効にします。</span><span class="sxs-lookup"><span data-stu-id="0ac73-103">Suppresses the compiler's ability to generate warnings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ac73-104">構文</span><span class="sxs-lookup"><span data-stu-id="0ac73-104">Syntax</span></span>  
  
```console  
-nowarn[:numberList]  
```  
  
## <a name="arguments"></a><span data-ttu-id="0ac73-105">引数</span><span class="sxs-lookup"><span data-stu-id="0ac73-105">Arguments</span></span>  
  
|<span data-ttu-id="0ac73-106">用語</span><span class="sxs-lookup"><span data-stu-id="0ac73-106">Term</span></span>|<span data-ttu-id="0ac73-107">定義</span><span class="sxs-lookup"><span data-stu-id="0ac73-107">Definition</span></span>|  
|---|---|  
|`numberList`|<span data-ttu-id="0ac73-108">任意。</span><span class="sxs-lookup"><span data-stu-id="0ac73-108">Optional.</span></span> <span data-ttu-id="0ac73-109">コンパイラにより非表示にされるべき警告 ID 番号のコンマ区切りの一覧。</span><span class="sxs-lookup"><span data-stu-id="0ac73-109">Comma-delimited list of the warning ID numbers that the compiler should suppress.</span></span> <span data-ttu-id="0ac73-110">警告 ID が指定されていない場合、すべての警告は非表示になります。</span><span class="sxs-lookup"><span data-stu-id="0ac73-110">If the warning IDs are not specified, all warnings are suppressed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0ac73-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="0ac73-111">Remarks</span></span>  

 <span data-ttu-id="0ac73-112">`-nowarn` オプションを指定すると、コンパイラにより警告が生成されなくなります。</span><span class="sxs-lookup"><span data-stu-id="0ac73-112">The `-nowarn` option causes the compiler to not generate warnings.</span></span> <span data-ttu-id="0ac73-113">個々の警告を非表示にするには、`-nowarn` オプションの後にコロンを追加し、警告 ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="0ac73-113">To suppress an individual warning, supply the warning ID to the `-nowarn` option following the colon.</span></span> <span data-ttu-id="0ac73-114">警告が複数ある場合は、番号をコンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="0ac73-114">Separate multiple warning numbers with commas.</span></span>  
  
 <span data-ttu-id="0ac73-115">警告 ID は、数値部分のみを指定します。</span><span class="sxs-lookup"><span data-stu-id="0ac73-115">You need to specify only the numeric part of the warning identifier.</span></span> <span data-ttu-id="0ac73-116">たとえば、BC42024 を非表示にする場合は、使用されていないローカル変数の警告に、`-nowarn:42024` を指定します。</span><span class="sxs-lookup"><span data-stu-id="0ac73-116">For example, if you want to suppress BC42024, the warning for unused local variables, specify `-nowarn:42024`.</span></span>  
  
 <span data-ttu-id="0ac73-117">警告 ID の番号の詳細については、「[Visual Basic での警告の構成](/visualstudio/ide/configuring-warnings-in-visual-basic)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0ac73-117">For more information on the warning ID numbers, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
|<span data-ttu-id="0ac73-118">Visual Studio 統合開発環境で -nowarn を設定するには</span><span class="sxs-lookup"><span data-stu-id="0ac73-118">To set -nowarn in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="0ac73-119">1.**ソリューション エクスプローラー**でプロジェクトを選択します。</span><span class="sxs-lookup"><span data-stu-id="0ac73-119">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="0ac73-120">**[プロジェクト]** メニューの **[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0ac73-120">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="0ac73-121">2. **[コンパイル]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="0ac73-121">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="0ac73-122">3.警告をすべて無効にするには、 **[すべての警告を表示しない]** チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="0ac73-122">3.  Select the **Disable all warnings** check box to disable all warnings.</span></span><br />     <span data-ttu-id="0ac73-123">または</span><span class="sxs-lookup"><span data-stu-id="0ac73-123">- or -</span></span><br />     <span data-ttu-id="0ac73-124">特定の警告を無効にするには、その警告の隣のドロップダウン リストから **[なし]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0ac73-124">To disable a particular warning, click **None** from the drop-down list adjacent to the warning.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="0ac73-125">例</span><span class="sxs-lookup"><span data-stu-id="0ac73-125">Example</span></span>  

 <span data-ttu-id="0ac73-126">次のコードでは `T2.vb` がコンパイルされ、警告が表示されません。</span><span class="sxs-lookup"><span data-stu-id="0ac73-126">The following code compiles `T2.vb` and does not display any warnings.</span></span>  
  
```console
vbc -nowarn t2.vb  
```  
  
## <a name="example"></a><span data-ttu-id="0ac73-127">例</span><span class="sxs-lookup"><span data-stu-id="0ac73-127">Example</span></span>  

 <span data-ttu-id="0ac73-128">次のコードでは `T2.vb` がコンパイルされ、使用されていないローカル変数 (42024) の警告が表示されません。</span><span class="sxs-lookup"><span data-stu-id="0ac73-128">The following code compiles `T2.vb` and does not display the warnings for unused local variables (42024).</span></span>  
  
```console
vbc -nowarn:42024 t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="0ac73-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="0ac73-129">See also</span></span>

- [<span data-ttu-id="0ac73-130">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="0ac73-130">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="0ac73-131">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="0ac73-131">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- [<span data-ttu-id="0ac73-132">Configuring Warnings in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0ac73-132">Configuring Warnings in Visual Basic</span></span>](/visualstudio/ide/configuring-warnings-in-visual-basic)
