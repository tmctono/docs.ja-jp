---
title: -win32icon
ms.date: 03/13/2018
helpviewer_keywords:
- win32icon compiler option [Visual Basic]
- -win32icon compiler option [Visual Basic]
- /win32icon compiler option [Visual Basic]
ms.assetid: aecaab01-9353-46c5-941c-6edabd4eff92
ms.openlocfilehash: 52ef0b991554c800dba4320b0c64c81ddd1b0ff4
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414286"
---
# <a name="-win32icon"></a><span data-ttu-id="32e33-102">-win32icon</span><span class="sxs-lookup"><span data-stu-id="32e33-102">-win32icon</span></span>
<span data-ttu-id="32e33-103">.ico ファイルを出力ファイルに挿入します。</span><span class="sxs-lookup"><span data-stu-id="32e33-103">Inserts an .ico file in the output file.</span></span> <span data-ttu-id="32e33-104">この .ico ファイルは、**エクスプローラー**では出力ファイルを表します。</span><span class="sxs-lookup"><span data-stu-id="32e33-104">This .ico file represents the output file in **File Explorer**.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32e33-105">構文</span><span class="sxs-lookup"><span data-stu-id="32e33-105">Syntax</span></span>  
  
```console  
-win32icon:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="32e33-106">引数</span><span class="sxs-lookup"><span data-stu-id="32e33-106">Arguments</span></span>  
  
|<span data-ttu-id="32e33-107">用語</span><span class="sxs-lookup"><span data-stu-id="32e33-107">Term</span></span>|<span data-ttu-id="32e33-108">定義</span><span class="sxs-lookup"><span data-stu-id="32e33-108">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="32e33-109">出力ファイルに追加する .ico ファイル。</span><span class="sxs-lookup"><span data-stu-id="32e33-109">The .ico file to add to your output file.</span></span> <span data-ttu-id="32e33-110">ファイル名に空白が含まれている場合は、名前を二重引用符 (" ") で囲みます。</span><span class="sxs-lookup"><span data-stu-id="32e33-110">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="32e33-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="32e33-111">Remarks</span></span>  
 <span data-ttu-id="32e33-112">Microsoft Windows リソース コンパイラ (RC) を使用して .ico ファイルを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="32e33-112">You can create an .ico file with the Microsoft Windows Resource Compiler (RC).</span></span> <span data-ttu-id="32e33-113">リソース コンパイラは、Visual C++ プログラムをコンパイルするときに呼び出されます。 .ico ファイルは .rc ファイルから作成されます。</span><span class="sxs-lookup"><span data-stu-id="32e33-113">The resource compiler is invoked when you compile a Visual C++ program; an .ico file is created from the .rc file.</span></span> <span data-ttu-id="32e33-114">`-win32icon` オプションと `-win32resource` オプションは同時に指定できません。</span><span class="sxs-lookup"><span data-stu-id="32e33-114">The `-win32icon` and `-win32resource` options are mutually exclusive.</span></span>  
  
 <span data-ttu-id="32e33-115">.NET Framework リソース ファイルの参照については「[-linkresource (Visual Basic)](linkresource.md)」を、.NET Framework リソース ファイルのアタッチについては「[-resource (Visual Basic)](resource.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32e33-115">See [-linkresource (Visual Basic)](linkresource.md) to reference a .NET Framework resource file, or [-resource (Visual Basic)](resource.md) to attach a .NET Framework resource file.</span></span> <span data-ttu-id="32e33-116">.res ファイルのインポートについては、「[-win32resource](win32resource.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32e33-116">See [-win32resource](win32resource.md) to import a .res file.</span></span>  
  
|<span data-ttu-id="32e33-117">Visual Studio IDE で -win32icon を設定するには</span><span class="sxs-lookup"><span data-stu-id="32e33-117">To set -win32icon in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="32e33-118">1.**ソリューション エクスプローラー**でプロジェクトを選択します。</span><span class="sxs-lookup"><span data-stu-id="32e33-118">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="32e33-119">**[プロジェクト]** メニューの **[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="32e33-119">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="32e33-120">2. **[アプリケーション]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="32e33-120">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="32e33-121">3. **[アイコン]** ボックスの値を変更します。</span><span class="sxs-lookup"><span data-stu-id="32e33-121">3.  Modify the value in the **Icon** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="32e33-122">例</span><span class="sxs-lookup"><span data-stu-id="32e33-122">Example</span></span>  
 <span data-ttu-id="32e33-123">次のコードでは `In.vb` がコンパイルされ、.ico ファイル `Rf.ico` がアタッチされます。</span><span class="sxs-lookup"><span data-stu-id="32e33-123">The following code compiles `In.vb` and attaches an .ico file, `Rf.ico`.</span></span>  
  
```console
vbc -win32icon:rf.ico in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="32e33-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="32e33-124">See also</span></span>

- [<span data-ttu-id="32e33-125">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="32e33-125">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="32e33-126">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="32e33-126">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
