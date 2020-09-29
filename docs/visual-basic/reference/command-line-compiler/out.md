---
title: -out
ms.date: 07/20/2015
helpviewer_keywords:
- /out compiler option [Visual Basic]
- -out compiler option [Visual Basic]
- out compiler option [Visual Basic]
ms.assetid: 9f148c15-0909-4cb8-a2db-777f8a8b45ae
ms.openlocfilehash: 7c013270c8a6b7c2b28f02766df7437b43075dd2
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "91098905"
---
# <a name="-out-visual-basic"></a><span data-ttu-id="99bac-102">-out (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="99bac-102">-out (Visual Basic)</span></span>

<span data-ttu-id="99bac-103">出力ファイルの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="99bac-103">Specifies the name of the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99bac-104">構文</span><span class="sxs-lookup"><span data-stu-id="99bac-104">Syntax</span></span>  
  
```console  
-out:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="99bac-105">引数</span><span class="sxs-lookup"><span data-stu-id="99bac-105">Arguments</span></span>  
  
|<span data-ttu-id="99bac-106">期間</span><span class="sxs-lookup"><span data-stu-id="99bac-106">Term</span></span>|<span data-ttu-id="99bac-107">定義</span><span class="sxs-lookup"><span data-stu-id="99bac-107">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="99bac-108">必須です。</span><span class="sxs-lookup"><span data-stu-id="99bac-108">Required.</span></span> <span data-ttu-id="99bac-109">コンパイラによって作成される出力ファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="99bac-109">The name of the output file the compiler creates.</span></span> <span data-ttu-id="99bac-110">ファイル名に空白が含まれている場合は、名前を二重引用符 (" ") で囲みます。</span><span class="sxs-lookup"><span data-stu-id="99bac-110">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="99bac-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="99bac-111">Remarks</span></span>  

 <span data-ttu-id="99bac-112">作成するファイルの完全な名前と拡張子を指定します。</span><span class="sxs-lookup"><span data-stu-id="99bac-112">Specify the full name and extension of the file to create.</span></span> <span data-ttu-id="99bac-113">そうしない場合、.exe ファイル名は `Sub Main` プロシージャを含むソースコード ファイルの名前になり、.dll ファイル名は最初のソースコード ファイルの名前になります。</span><span class="sxs-lookup"><span data-stu-id="99bac-113">If you do not, the .exe file takes its name from the source-code file containing the `Sub Main` procedure, and the .dll file takes its name from the first source-code file.</span></span>  
  
 <span data-ttu-id="99bac-114">.exe または .dll 拡張子のないファイル名を指定すると、コンパイラによって、`-target` コンパイラ オプションに指定された値に応じて、自動的に拡張子が追加されます。</span><span class="sxs-lookup"><span data-stu-id="99bac-114">If you specify a file name without an .exe or .dll extension, the compiler automatically adds the extension for you, depending on the value specified for the `-target` compiler option.</span></span>  
  
|<span data-ttu-id="99bac-115">Visual Studio 統合開発環境で -out を設定するには</span><span class="sxs-lookup"><span data-stu-id="99bac-115">To set -out in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="99bac-116">1.**ソリューション エクスプローラー**でプロジェクトを選択します。</span><span class="sxs-lookup"><span data-stu-id="99bac-116">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="99bac-117">**[プロジェクト]** メニューの **[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="99bac-117">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="99bac-118">2. **[アプリケーション]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="99bac-118">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="99bac-119">3. **[アセンブリ名]** ボックスで値を変更します。</span><span class="sxs-lookup"><span data-stu-id="99bac-119">3.  Modify the value in the **Assembly Name** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="99bac-120">例</span><span class="sxs-lookup"><span data-stu-id="99bac-120">Example</span></span>  

 <span data-ttu-id="99bac-121">次のコードでは `T2.vb` をコンパイルし、出力ファイル `T2.exe` を作成します。</span><span class="sxs-lookup"><span data-stu-id="99bac-121">The following code compiles `T2.vb` and creates output file `T2.exe`.</span></span>  
  
```console
vbc t2.vb -out:t3.exe  
```  
  
## <a name="see-also"></a><span data-ttu-id="99bac-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="99bac-122">See also</span></span>

- [<span data-ttu-id="99bac-123">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="99bac-123">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="99bac-124">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="99bac-124">-target (Visual Basic)</span></span>](target.md)
- [<span data-ttu-id="99bac-125">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="99bac-125">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
