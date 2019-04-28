---
title: -nowarn
ms.date: 07/20/2015
helpviewer_keywords:
- nowarn compiler option [Visual Basic]
- /nowarn compiler option [Visual Basic]
- -nowarn compiler option [Visual Basic]
ms.assetid: 7ebf2106-0652-4fdc-bf60-70fc86465d83
ms.openlocfilehash: 31f7a2b771cfa1bcc6581d720aa0de3505aec826
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61788987"
---
# <a name="-nowarn"></a><span data-ttu-id="a8f97-102">-nowarn</span><span class="sxs-lookup"><span data-stu-id="a8f97-102">-nowarn</span></span>
<span data-ttu-id="a8f97-103">警告を生成するコンパイラの機能を無効にします。</span><span class="sxs-lookup"><span data-stu-id="a8f97-103">Suppresses the compiler's ability to generate warnings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8f97-104">構文</span><span class="sxs-lookup"><span data-stu-id="a8f97-104">Syntax</span></span>  
  
```  
-nowarn[:numberList]  
```  
  
## <a name="arguments"></a><span data-ttu-id="a8f97-105">引数</span><span class="sxs-lookup"><span data-stu-id="a8f97-105">Arguments</span></span>  
  
|<span data-ttu-id="a8f97-106">用語</span><span class="sxs-lookup"><span data-stu-id="a8f97-106">Term</span></span>|<span data-ttu-id="a8f97-107">定義</span><span class="sxs-lookup"><span data-stu-id="a8f97-107">Definition</span></span>|  
|---|---|  
|`numberList`|<span data-ttu-id="a8f97-108">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="a8f97-108">Optional.</span></span> <span data-ttu-id="a8f97-109">コンパイラはしないようにする警告の ID 番号のコンマ区切りリスト。</span><span class="sxs-lookup"><span data-stu-id="a8f97-109">Comma-delimited list of the warning ID numbers that the compiler should suppress.</span></span> <span data-ttu-id="a8f97-110">警告の Id が指定されていない場合は、すべての警告が抑制されます。</span><span class="sxs-lookup"><span data-stu-id="a8f97-110">If the warning IDs are not specified, all warnings are suppressed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a8f97-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="a8f97-111">Remarks</span></span>  
 <span data-ttu-id="a8f97-112">`-nowarn`オプションと、コンパイラの警告を生成しません。</span><span class="sxs-lookup"><span data-stu-id="a8f97-112">The `-nowarn` option causes the compiler to not generate warnings.</span></span> <span data-ttu-id="a8f97-113">個々 の警告を抑制するのに警告の ID を指定します、`-nowarn`コロンに続くオプション。</span><span class="sxs-lookup"><span data-stu-id="a8f97-113">To suppress an individual warning, supply the warning ID to the `-nowarn` option following the colon.</span></span> <span data-ttu-id="a8f97-114">複数の警告番号をコンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="a8f97-114">Separate multiple warning numbers with commas.</span></span>  
  
 <span data-ttu-id="a8f97-115">警告 id の数値の一部だけを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8f97-115">You need to specify only the numeric part of the warning identifier.</span></span> <span data-ttu-id="a8f97-116">たとえば、BC42024、未使用のローカル変数の警告を抑制する場合は、指定`-nowarn:42024`します。</span><span class="sxs-lookup"><span data-stu-id="a8f97-116">For example, if you want to suppress BC42024, the warning for unused local variables, specify `-nowarn:42024`.</span></span>  
  
 <span data-ttu-id="a8f97-117">警告の ID 番号の詳細については、次を参照してください。 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)します。</span><span class="sxs-lookup"><span data-stu-id="a8f97-117">For more information on the warning ID numbers, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
|<span data-ttu-id="a8f97-118">Visual Studio 統合開発環境で-nowarn を設定するには</span><span class="sxs-lookup"><span data-stu-id="a8f97-118">To set -nowarn in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="a8f97-119">1.**ソリューション エクスプローラー**でプロジェクトを選択します。</span><span class="sxs-lookup"><span data-stu-id="a8f97-119">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="a8f97-120">**[プロジェクト]** メニューの **[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a8f97-120">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="a8f97-121">2.**[コンパイル]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a8f97-121">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="a8f97-122">3.選択、**すべての警告を無効にする**すべての警告を無効にする チェック ボックス。</span><span class="sxs-lookup"><span data-stu-id="a8f97-122">3.  Select the **Disable all warnings** check box to disable all warnings.</span></span><br />     <span data-ttu-id="a8f97-123">または</span><span class="sxs-lookup"><span data-stu-id="a8f97-123">- or -</span></span><br />     <span data-ttu-id="a8f97-124">特定の警告を無効にするには、 **None**警告の横にあるドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="a8f97-124">To disable a particular warning, click **None** from the drop-down list adjacent to the warning.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a8f97-125">例</span><span class="sxs-lookup"><span data-stu-id="a8f97-125">Example</span></span>  
 <span data-ttu-id="a8f97-126">次のコードのコンパイル`T2.vb`すべての警告は表示されません。</span><span class="sxs-lookup"><span data-stu-id="a8f97-126">The following code compiles `T2.vb` and does not display any warnings.</span></span>  
  
```console
vbc -nowarn t2.vb  
```  
  
## <a name="example"></a><span data-ttu-id="a8f97-127">例</span><span class="sxs-lookup"><span data-stu-id="a8f97-127">Example</span></span>  
 <span data-ttu-id="a8f97-128">次のコードのコンパイル`T2.vb`未使用のローカル変数 (42024) の警告は表示されません。</span><span class="sxs-lookup"><span data-stu-id="a8f97-128">The following code compiles `T2.vb` and does not display the warnings for unused local variables (42024).</span></span>  
  
```console
vbc -nowarn:42024 t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="a8f97-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="a8f97-129">See also</span></span>

- [<span data-ttu-id="a8f97-130">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="a8f97-130">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="a8f97-131">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="a8f97-131">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="a8f97-132">Configuring Warnings in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a8f97-132">Configuring Warnings in Visual Basic</span></span>](/visualstudio/ide/configuring-warnings-in-visual-basic)
