---
title: -win32icon
ms.date: 03/13/2018
helpviewer_keywords:
- win32icon compiler option [Visual Basic]
- -win32icon compiler option [Visual Basic]
- /win32icon compiler option [Visual Basic]
ms.assetid: aecaab01-9353-46c5-941c-6edabd4eff92
ms.openlocfilehash: 6b4b69d227c857442de6857fac023090b3698e81
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004632"
---
# <a name="-win32icon"></a><span data-ttu-id="cc982-102">-win32icon</span><span class="sxs-lookup"><span data-stu-id="cc982-102">-win32icon</span></span>
<span data-ttu-id="cc982-103">.Ico ファイルを出力ファイルに挿入します。</span><span class="sxs-lookup"><span data-stu-id="cc982-103">Inserts an .ico file in the output file.</span></span> <span data-ttu-id="cc982-104">この .ico ファイルは、**ファイルエクスプローラー**の出力ファイルを表します。</span><span class="sxs-lookup"><span data-stu-id="cc982-104">This .ico file represents the output file in **File Explorer**.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc982-105">構文</span><span class="sxs-lookup"><span data-stu-id="cc982-105">Syntax</span></span>  
  
```console  
-win32icon:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="cc982-106">引数</span><span class="sxs-lookup"><span data-stu-id="cc982-106">Arguments</span></span>  
  
|<span data-ttu-id="cc982-107">項目</span><span class="sxs-lookup"><span data-stu-id="cc982-107">Term</span></span>|<span data-ttu-id="cc982-108">定義</span><span class="sxs-lookup"><span data-stu-id="cc982-108">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="cc982-109">出力ファイルに追加する .ico ファイル。</span><span class="sxs-lookup"><span data-stu-id="cc982-109">The .ico file to add to your output file.</span></span> <span data-ttu-id="cc982-110">ファイル名にスペースが含まれている場合は、ファイル名を引用符 ("") で囲みます。</span><span class="sxs-lookup"><span data-stu-id="cc982-110">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cc982-111">コメント</span><span class="sxs-lookup"><span data-stu-id="cc982-111">Remarks</span></span>  
 <span data-ttu-id="cc982-112">Microsoft Windows リソースコンパイラ (RC) を使用して .ico ファイルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="cc982-112">You can create an .ico file with the Microsoft Windows Resource Compiler (RC).</span></span> <span data-ttu-id="cc982-113">リソースコンパイラは、ビジュアルC++プログラムをコンパイルすると呼び出されます.ico ファイルは、.rc ファイルから作成されます。</span><span class="sxs-lookup"><span data-stu-id="cc982-113">The resource compiler is invoked when you compile a Visual C++ program; an .ico file is created from the .rc file.</span></span> <span data-ttu-id="cc982-114">@No__t-0 および `-win32resource` オプションは相互に排他的です。</span><span class="sxs-lookup"><span data-stu-id="cc982-114">The `-win32icon` and `-win32resource` options are mutually exclusive.</span></span>  
  
 <span data-ttu-id="cc982-115">.NET Framework リソースファイルを参照する場合は[-linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md)を参照し、.NET Framework リソースファイルをアタッチする場合は[-resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc982-115">See [-linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) to reference a .NET Framework resource file, or [-resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) to attach a .NET Framework resource file.</span></span> <span data-ttu-id="cc982-116">.Res ファイルをインポートするには[、「-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc982-116">See [-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) to import a .res file.</span></span>  
  
|<span data-ttu-id="cc982-117">Visual Studio IDE で-win32icon を設定するには</span><span class="sxs-lookup"><span data-stu-id="cc982-117">To set -win32icon in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="cc982-118">1. **ソリューション エクスプローラー**でプロジェクトを選択します。</span><span class="sxs-lookup"><span data-stu-id="cc982-118">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="cc982-119">**[プロジェクト]** メニューの **[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cc982-119">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="cc982-120">2. **[アプリケーション]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="cc982-120">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="cc982-121">3. **[アイコン]** ボックスの値を変更します。</span><span class="sxs-lookup"><span data-stu-id="cc982-121">3.  Modify the value in the **Icon** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="cc982-122">例</span><span class="sxs-lookup"><span data-stu-id="cc982-122">Example</span></span>  
 <span data-ttu-id="cc982-123">次のコードは `In.vb` をコンパイルし、.ico ファイルをアタッチします。 `Rf.ico` です。</span><span class="sxs-lookup"><span data-stu-id="cc982-123">The following code compiles `In.vb` and attaches an .ico file, `Rf.ico`.</span></span>  
  
```console
vbc -win32icon:rf.ico in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="cc982-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="cc982-124">See also</span></span>

- [<span data-ttu-id="cc982-125">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="cc982-125">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="cc982-126">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="cc982-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
