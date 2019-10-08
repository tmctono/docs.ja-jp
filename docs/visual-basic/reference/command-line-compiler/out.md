---
title: -out (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- /out compiler option [Visual Basic]
- -out compiler option [Visual Basic]
- out compiler option [Visual Basic]
ms.assetid: 9f148c15-0909-4cb8-a2db-777f8a8b45ae
ms.openlocfilehash: 6b005ac26e3fffad350cb4ce52f7757c9fff2ac1
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005334"
---
# <a name="-out-visual-basic"></a><span data-ttu-id="36e2b-102">-out (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="36e2b-102">-out (Visual Basic)</span></span>
<span data-ttu-id="36e2b-103">出力ファイルの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="36e2b-103">Specifies the name of the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36e2b-104">構文</span><span class="sxs-lookup"><span data-stu-id="36e2b-104">Syntax</span></span>  
  
```console  
-out:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="36e2b-105">引数</span><span class="sxs-lookup"><span data-stu-id="36e2b-105">Arguments</span></span>  
  
|<span data-ttu-id="36e2b-106">項目</span><span class="sxs-lookup"><span data-stu-id="36e2b-106">Term</span></span>|<span data-ttu-id="36e2b-107">定義</span><span class="sxs-lookup"><span data-stu-id="36e2b-107">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="36e2b-108">必須。</span><span class="sxs-lookup"><span data-stu-id="36e2b-108">Required.</span></span> <span data-ttu-id="36e2b-109">コンパイラによって作成される出力ファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="36e2b-109">The name of the output file the compiler creates.</span></span> <span data-ttu-id="36e2b-110">ファイル名にスペースが含まれている場合は、名前を引用符 ("") で囲みます。</span><span class="sxs-lookup"><span data-stu-id="36e2b-110">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="36e2b-111">コメント</span><span class="sxs-lookup"><span data-stu-id="36e2b-111">Remarks</span></span>  
 <span data-ttu-id="36e2b-112">作成するファイルの完全な名前と拡張子を指定します。</span><span class="sxs-lookup"><span data-stu-id="36e2b-112">Specify the full name and extension of the file to create.</span></span> <span data-ttu-id="36e2b-113">そうしないと、.exe ファイルの名前が `Sub Main` プロシージャを含むソースコードファイルから取得され、.dll ファイルの名前が最初のソースコードファイルの名前になります。</span><span class="sxs-lookup"><span data-stu-id="36e2b-113">If you do not, the .exe file takes its name from the source-code file containing the `Sub Main` procedure, and the .dll file takes its name from the first source-code file.</span></span>  
  
 <span data-ttu-id="36e2b-114">.Exe または .dll 拡張子のないファイル名を指定すると、コンパイラは、`-target` コンパイラオプションに指定された値に応じて、自動的に拡張機能を追加します。</span><span class="sxs-lookup"><span data-stu-id="36e2b-114">If you specify a file name without an .exe or .dll extension, the compiler automatically adds the extension for you, depending on the value specified for the `-target` compiler option.</span></span>  
  
|<span data-ttu-id="36e2b-115">Visual Studio 統合開発環境でを設定するには</span><span class="sxs-lookup"><span data-stu-id="36e2b-115">To set -out in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="36e2b-116">1. **ソリューション エクスプローラー**でプロジェクトを選択します。</span><span class="sxs-lookup"><span data-stu-id="36e2b-116">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="36e2b-117">**[プロジェクト]** メニューの **[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="36e2b-117">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="36e2b-118">2. **[アプリケーション]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="36e2b-118">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="36e2b-119">3. **[アセンブリ名]** ボックスの値を変更します。</span><span class="sxs-lookup"><span data-stu-id="36e2b-119">3.  Modify the value in the **Assembly Name** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="36e2b-120">例</span><span class="sxs-lookup"><span data-stu-id="36e2b-120">Example</span></span>  
 <span data-ttu-id="36e2b-121">次のコードでは `T2.vb` をコンパイルし、出力ファイル `T2.exe` を作成します。</span><span class="sxs-lookup"><span data-stu-id="36e2b-121">The following code compiles `T2.vb` and creates output file `T2.exe`.</span></span>  
  
```console
vbc t2.vb -out:t3.exe  
```  
  
## <a name="see-also"></a><span data-ttu-id="36e2b-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="36e2b-122">See also</span></span>

- [<span data-ttu-id="36e2b-123">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="36e2b-123">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="36e2b-124">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="36e2b-124">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="36e2b-125">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="36e2b-125">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
