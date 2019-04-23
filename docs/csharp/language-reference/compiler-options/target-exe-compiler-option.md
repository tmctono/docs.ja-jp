---
title: -target:exe (C# コンパイラ オプション)
ms.date: 07/20/2015
f1_keywords:
- /exe
helpviewer_keywords:
- target compiler options [C#], /target:exe
- /target compiler options [C#], /target:exe
- -target compiler options [C#], /target:exe
ms.assetid: bda5717d-1b91-4848-956b-fcf85c30e432
ms.openlocfilehash: 7d34a25fd614a209761714e1f4eff3042ca240c0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59331313"
---
# <a name="-targetexe-c-compiler-options"></a><span data-ttu-id="119b2-102">-target:exe (C# コンパイラ オプション)</span><span class="sxs-lookup"><span data-stu-id="119b2-102">-target:exe (C# Compiler Options)</span></span>
<span data-ttu-id="119b2-103">**-target:exe** オプションを指定した場合、コンパイラは実行可能な (EXE) コンソール アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="119b2-103">The **-target:exe** option causes the compiler to create an executable (EXE), console application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="119b2-104">構文</span><span class="sxs-lookup"><span data-stu-id="119b2-104">Syntax</span></span>  
  
```console  
-target:exe  
```  
  
## <a name="remarks"></a><span data-ttu-id="119b2-105">解説</span><span class="sxs-lookup"><span data-stu-id="119b2-105">Remarks</span></span>  
 <span data-ttu-id="119b2-106">**-target:exe** オプションは既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="119b2-106">The **-target:exe** option is in effect by default.</span></span> <span data-ttu-id="119b2-107">実行可能ファイルは、.exe という拡張子で作成されます。</span><span class="sxs-lookup"><span data-stu-id="119b2-107">The executable file will be created with the .exe extension.</span></span>  
  
 <span data-ttu-id="119b2-108">Windows プログラムの実行可能ファイルを作成する場合は、[-target:winexe](../../../csharp/language-reference/compiler-options/target-winexe-compiler-option.md) を使用します。</span><span class="sxs-lookup"><span data-stu-id="119b2-108">Use [-target:winexe](../../../csharp/language-reference/compiler-options/target-winexe-compiler-option.md) to create a Windows program executable.</span></span>  
  
 <span data-ttu-id="119b2-109">[-out](../../../csharp/language-reference/compiler-options/out-compiler-option.md) オプションで指定しない限り、出力ファイル名は [Main](../../../csharp/programming-guide/main-and-command-args/index.md) メソッドを含む入力ファイルと同じになります。</span><span class="sxs-lookup"><span data-stu-id="119b2-109">Unless otherwise specified with the [-out](../../../csharp/language-reference/compiler-options/out-compiler-option.md) option, the output file name takes the name of the input file that contains the [Main](../../../csharp/programming-guide/main-and-command-args/index.md) method.</span></span>  
  
 <span data-ttu-id="119b2-110">コマンド ラインで指定すると、次の **-out** または **-target:module** オプションまでのすべてのファイルが .exe ファイルを作成するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="119b2-110">When specified at the command line, all files up to the next **-out** or **-target:module** option are used to create the .exe file</span></span>  
  
 <span data-ttu-id="119b2-111">**Main** メソッドは、.exe ファイルにコンパイルされるソース コード ファイル内に 1 つだけ必要です。</span><span class="sxs-lookup"><span data-stu-id="119b2-111">One and only one **Main** method is required in the source code files that are compiled into an .exe file.</span></span> <span data-ttu-id="119b2-112">コードに **Main** メソッドを含むクラスが複数ある場合は、[-main](../../../csharp/language-reference/compiler-options/main-compiler-option.md) コンパイラ オプションを使用して、**Main** メソッドを含めるクラスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="119b2-112">The [-main](../../../csharp/language-reference/compiler-options/main-compiler-option.md) compiler option lets you specify which class contains the **Main** method, in cases where your code has more than one class with a **Main** method.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="119b2-113">Visual Studio 開発環境でこのコンパイラ オプションを設定するには</span><span class="sxs-lookup"><span data-stu-id="119b2-113">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="119b2-114">プロジェクトの **[プロパティ]** ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="119b2-114">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="119b2-115">**[アプリケーション]** プロパティ ページをクリックします。</span><span class="sxs-lookup"><span data-stu-id="119b2-115">Click the **Application** property page.</span></span>  
  
3. <span data-ttu-id="119b2-116">**[出力の種類]** プロパティを変更します。</span><span class="sxs-lookup"><span data-stu-id="119b2-116">Modify the **Output type** property.</span></span>  
  
 <span data-ttu-id="119b2-117">このコンパイラ オプションをプログラムで設定する方法については、「 <xref:VSLangProj80.ProjectProperties3.OutputType%2A>」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="119b2-117">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="119b2-118">例</span><span class="sxs-lookup"><span data-stu-id="119b2-118">Example</span></span>  
 <span data-ttu-id="119b2-119">次のコマンド ラインのいずれかで `in.cs` がコンパイルされ、`in.exe` が作成されます。</span><span class="sxs-lookup"><span data-stu-id="119b2-119">Each of the following command lines will compile `in.cs`, creating `in.exe`:</span></span>  
  
```console  
csc -target:exe in.cs  
csc in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="119b2-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="119b2-120">See also</span></span>

- [<span data-ttu-id="119b2-121">-target (C# コンパイラ オプション)</span><span class="sxs-lookup"><span data-stu-id="119b2-121">-target (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/target-compiler-option.md)
- [<span data-ttu-id="119b2-122">C# コンパイラ オプション</span><span class="sxs-lookup"><span data-stu-id="119b2-122">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
