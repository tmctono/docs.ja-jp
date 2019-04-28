---
title: -warnaserror (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- warnaserror compiler option [Visual Basic]
- /warnaserror compiler option [Visual Basic]
- -warnaserror compiler option [Visual Basic]
ms.assetid: 49819f1d-a1bd-4201-affe-5afe6d9712e1
ms.openlocfilehash: c06326a250fba0de2f63e13672b4fffbfa8a07f0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61796176"
---
# <a name="-warnaserror-visual-basic"></a><span data-ttu-id="d12c8-102">-warnaserror (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d12c8-102">-warnaserror (Visual Basic)</span></span>
<span data-ttu-id="d12c8-103">コンパイラで、最初に発生した警告がエラーとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="d12c8-103">Causes the compiler to treat the first occurrence of a warning as an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d12c8-104">構文</span><span class="sxs-lookup"><span data-stu-id="d12c8-104">Syntax</span></span>  
  
```  
-warnaserror[+ | -][:numberList]  
```  
  
## <a name="arguments"></a><span data-ttu-id="d12c8-105">引数</span><span class="sxs-lookup"><span data-stu-id="d12c8-105">Arguments</span></span>  
  
|<span data-ttu-id="d12c8-106">用語</span><span class="sxs-lookup"><span data-stu-id="d12c8-106">Term</span></span>|<span data-ttu-id="d12c8-107">定義</span><span class="sxs-lookup"><span data-stu-id="d12c8-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="d12c8-108">+ &#124; -</span><span class="sxs-lookup"><span data-stu-id="d12c8-108">+ &#124; -</span></span>|<span data-ttu-id="d12c8-109">任意。</span><span class="sxs-lookup"><span data-stu-id="d12c8-109">Optional.</span></span> <span data-ttu-id="d12c8-110">既定では `-warnaserror-` は有効です。警告が発生しても、コンパイラは出力ファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="d12c8-110">By default, `-warnaserror-` is in effect; warnings do not prevent the compiler from producing an output file.</span></span> <span data-ttu-id="d12c8-111">`-warnaserror` オプションは `-warnaserror+` と同じで、警告がエラーとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="d12c8-111">The `-warnaserror` option, which is the same as `-warnaserror+`, causes warnings to be treated as errors.</span></span>|  
|`numberList`|<span data-ttu-id="d12c8-112">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="d12c8-112">Optional.</span></span> <span data-ttu-id="d12c8-113">`-warnaserror` オプションを適用する、警告 ID 番号のコンマ区切りのリスト。</span><span class="sxs-lookup"><span data-stu-id="d12c8-113">Comma-delimited list of the warning ID numbers to which the `-warnaserror` option applies.</span></span> <span data-ttu-id="d12c8-114">警告 ID が指定されていない場合、`-warnaserror`オプションはすべての警告に適用されます。</span><span class="sxs-lookup"><span data-stu-id="d12c8-114">If no warning ID is specified, the `-warnaserror` option applies to all warnings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d12c8-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="d12c8-115">Remarks</span></span>  
 <span data-ttu-id="d12c8-116">`-warnaserror` オプションで、すべての警告がエラーとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="d12c8-116">The `-warnaserror` option treats all warnings as errors.</span></span> <span data-ttu-id="d12c8-117">通常は警告として報告されるすべてのメッセージが、代わりにエラーとして報告されます。</span><span class="sxs-lookup"><span data-stu-id="d12c8-117">Any messages that would ordinarily be reported as warnings are instead reported as errors.</span></span> <span data-ttu-id="d12c8-118">コンパイラは、後続の同じ警告の発生を警告として報告します。</span><span class="sxs-lookup"><span data-stu-id="d12c8-118">The compiler reports subsequent occurrences of the same warning as warnings.</span></span>  
  
 <span data-ttu-id="d12c8-119">既定では `-warnaserror-` が有効であり、警告は情報提供のみになります。</span><span class="sxs-lookup"><span data-stu-id="d12c8-119">By default, `-warnaserror-` is in effect, which causes the warnings to be informational only.</span></span> <span data-ttu-id="d12c8-120">`-warnaserror` オプションは `-warnaserror+` と同じで、警告がエラーとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="d12c8-120">The `-warnaserror` option, which is the same as `-warnaserror+`, causes warnings to be treated as errors.</span></span>  
  
 <span data-ttu-id="d12c8-121">いくつかの特定の警告のみをエラーとして扱う場合は、エラーとして扱う警告番号のコンマ区切りのリストを指定できます。</span><span class="sxs-lookup"><span data-stu-id="d12c8-121">If you want only a few specific warnings to be treated as errors, you may specify a comma-separated list of warning numbers to treat as errors.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d12c8-122">`-warnaserror` オプションでは、警告の表示方法は制御されません。</span><span class="sxs-lookup"><span data-stu-id="d12c8-122">The `-warnaserror` option does not control how warnings are displayed.</span></span> <span data-ttu-id="d12c8-123">[-nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md) オプションを使用して警告を無効にします。</span><span class="sxs-lookup"><span data-stu-id="d12c8-123">Use the [-nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md) option to disable warnings.</span></span>  
  
|<span data-ttu-id="d12c8-124">-warnaserror を設定し、Visual Studio IDE ですべての警告をエラーとして扱う</span><span class="sxs-lookup"><span data-stu-id="d12c8-124">To set -warnaserror to treat all warnings as errors in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="d12c8-125">1.**ソリューション エクスプローラー**でプロジェクトを選択します。</span><span class="sxs-lookup"><span data-stu-id="d12c8-125">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="d12c8-126">**[プロジェクト]** メニューの **[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d12c8-126">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="d12c8-127">2.**[コンパイル]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d12c8-127">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="d12c8-128">3.**[すべての警告を表示しない]** チェック ボックスがオフになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d12c8-128">3.  Make sure the **Disable all warnings** check box is unchecked.</span></span><br /><span data-ttu-id="d12c8-129">4.**[すべての警告をエラーとして扱う]** チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="d12c8-129">4.  Check the **Treat all warnings as errors** check box.</span></span>|  
  
|<span data-ttu-id="d12c8-130">-warnaserror を設定し、Visual Studio IDE で特定の警告をエラーとして扱う</span><span class="sxs-lookup"><span data-stu-id="d12c8-130">To set -warnaserror to treat specific warnings as errors in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="d12c8-131">1.**ソリューション エクスプローラー**でプロジェクトを選択します。</span><span class="sxs-lookup"><span data-stu-id="d12c8-131">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="d12c8-132">**[プロジェクト]** メニューの **[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d12c8-132">On the **Project** menu, click **Properties**.</span></span><br /><span data-ttu-id="d12c8-133">2.**[コンパイル]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d12c8-133">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="d12c8-134">3.**[すべての警告を表示しない]** チェック ボックスがオフになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d12c8-134">3.  Make sure the **Disable all warnings** check box is unchecked.</span></span><br /><span data-ttu-id="d12c8-135">4.**[すべての警告をエラーとして扱う]** チェック ボックスがオフになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d12c8-135">4.  Make sure the **Treat all warnings as errors** check box is unchecked.</span></span><br /><span data-ttu-id="d12c8-136">5.エラーとして扱う警告の隣にある **[通知]** 列から、**[エラー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d12c8-136">5.  Select **Error** from the **Notification** column adjacent to the warning that should be treated as an error.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d12c8-137">例</span><span class="sxs-lookup"><span data-stu-id="d12c8-137">Example</span></span>  
 <span data-ttu-id="d12c8-138">次のコードは `In.vb` をコンパイルし、最初に見つけたすべての警告をエラーとして表示するようにコンパイラに指示します。</span><span class="sxs-lookup"><span data-stu-id="d12c8-138">The following code compiles `In.vb` and directs the compiler to display an error for the first occurrence of every warning it finds.</span></span>  
  
```console
vbc -warnaserror in.vb  
```  
  
## <a name="example"></a><span data-ttu-id="d12c8-139">例</span><span class="sxs-lookup"><span data-stu-id="d12c8-139">Example</span></span>  
 <span data-ttu-id="d12c8-140">次のコードは `T2.vb` をコンパイルし、使用されていないローカル変数 (42024) に向けた警告のみをエラーとして扱います。</span><span class="sxs-lookup"><span data-stu-id="d12c8-140">The following code compiles `T2.vb` and treats only the warning for unused local variables (42024) as an error.</span></span>  
  
```console
vbc -warnaserror:42024 t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="d12c8-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="d12c8-141">See also</span></span>

- [<span data-ttu-id="d12c8-142">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="d12c8-142">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="d12c8-143">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="d12c8-143">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="d12c8-144">Configuring Warnings in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d12c8-144">Configuring Warnings in Visual Basic</span></span>](/visualstudio/ide/configuring-warnings-in-visual-basic)
