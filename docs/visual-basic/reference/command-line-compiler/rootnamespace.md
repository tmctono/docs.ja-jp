---
title: -rootnamespace
ms.date: 03/13/2018
f1_keywords:
- /rootnamespace
- rootnamespace
helpviewer_keywords:
- /rootnamespace compiler option [Visual Basic]
- -rootnamespace compiler option [Visual Basic]
- rootnamespace compiler option [Visual Basic]
ms.assetid: e9245edf-6bef-420d-a7c7-324117752783
ms.openlocfilehash: 4df4e74fc13c922f51f5b74c3c152bdea28b4431
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005208"
---
# <a name="-rootnamespace"></a><span data-ttu-id="cc9bd-102">-rootnamespace</span><span class="sxs-lookup"><span data-stu-id="cc9bd-102">-rootnamespace</span></span>
<span data-ttu-id="cc9bd-103">すべての型宣言に対して名前空間を指定します。</span><span class="sxs-lookup"><span data-stu-id="cc9bd-103">Specifies a namespace for all type declarations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc9bd-104">構文</span><span class="sxs-lookup"><span data-stu-id="cc9bd-104">Syntax</span></span>  
  
```console  
-rootnamespace:namespace  
```  
  
## <a name="arguments"></a><span data-ttu-id="cc9bd-105">引数</span><span class="sxs-lookup"><span data-stu-id="cc9bd-105">Arguments</span></span>  
  
|<span data-ttu-id="cc9bd-106">項目</span><span class="sxs-lookup"><span data-stu-id="cc9bd-106">Term</span></span>|<span data-ttu-id="cc9bd-107">定義</span><span class="sxs-lookup"><span data-stu-id="cc9bd-107">Definition</span></span>|  
|---|---|  
|`namespace`|<span data-ttu-id="cc9bd-108">現在のプロジェクトのすべての型宣言を囲む名前空間の名前。</span><span class="sxs-lookup"><span data-stu-id="cc9bd-108">The name of the namespace in which to enclose all type declarations for the current project.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cc9bd-109">コメント</span><span class="sxs-lookup"><span data-stu-id="cc9bd-109">Remarks</span></span>  
 <span data-ttu-id="cc9bd-110">Visual studio の実行可能ファイル (Devenv.exe) を使用して、Visual Studio 統合開発環境で作成されたプロジェクトをコンパイルする場合は、`-rootnamespace` を使用して、<xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A> プロパティの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="cc9bd-110">If you use the Visual Studio executable file (Devenv.exe) to compile a project created in the Visual Studio integrated development environment, use `-rootnamespace` to specify the value of the <xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A> property.</span></span> <span data-ttu-id="cc9bd-111">詳細については、「 [Devenv コマンドラインスイッチ](/visualstudio/ide/reference/devenv-command-line-switches)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc9bd-111">See [Devenv Command Line Switches](/visualstudio/ide/reference/devenv-command-line-switches) for more information.</span></span>  
  
 <span data-ttu-id="cc9bd-112">共通言語ランタイムの MSIL 逆アセンブラー (`Ildasm.exe`) を使用して、出力ファイル内の名前空間の名前を表示します。</span><span class="sxs-lookup"><span data-stu-id="cc9bd-112">Use the common language runtime MSIL Disassembler (`Ildasm.exe`) to view the namespace names in your output file.</span></span>  
  
|<span data-ttu-id="cc9bd-113">Visual Studio 統合開発環境で rootnamespace を設定するには</span><span class="sxs-lookup"><span data-stu-id="cc9bd-113">To set -rootnamespace in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="cc9bd-114">1. **ソリューション エクスプローラー**でプロジェクトを選択します。</span><span class="sxs-lookup"><span data-stu-id="cc9bd-114">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="cc9bd-115">**[プロジェクト]** メニューの **[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cc9bd-115">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="cc9bd-116">2. **[アプリケーション]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="cc9bd-116">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="cc9bd-117">3. **[ルート名前空間]** ボックスの値を変更します。</span><span class="sxs-lookup"><span data-stu-id="cc9bd-117">3.  Modify the value in the **Root Namespace** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="cc9bd-118">例</span><span class="sxs-lookup"><span data-stu-id="cc9bd-118">Example</span></span>  
 <span data-ttu-id="cc9bd-119">次のコードでは `In.vb` をコンパイルし、名前空間 `mynamespace` のすべての型宣言を囲みます。</span><span class="sxs-lookup"><span data-stu-id="cc9bd-119">The following code compiles `In.vb` and encloses all type declarations in the namespace `mynamespace`.</span></span>  
  
```console
vbc -rootnamespace:mynamespace in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="cc9bd-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="cc9bd-120">See also</span></span>

- [<span data-ttu-id="cc9bd-121">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="cc9bd-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="cc9bd-122">Ildasm.exe (IL 逆アセンブラー)</span><span class="sxs-lookup"><span data-stu-id="cc9bd-122">Ildasm.exe (IL Disassembler)</span></span>](../../../framework/tools/ildasm-exe-il-disassembler.md)
- [<span data-ttu-id="cc9bd-123">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="cc9bd-123">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
