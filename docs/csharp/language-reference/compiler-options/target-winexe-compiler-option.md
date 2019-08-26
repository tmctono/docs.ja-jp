---
title: -target:winexe (C# コンパイラ オプション)
ms.date: 07/20/2015
f1_keywords:
- /target:winexe
helpviewer_keywords:
- /target compiler options [C#], /target:winexe
- -target compiler options [C#], /target:winexe
- target compiler options [C#], /target:winexe
ms.assetid: b5a0619c-8caa-46a5-a743-1cf68408ad7a
ms.openlocfilehash: 981f1b0b6ca9f708bb022a3662ab181a4f472040
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2019
ms.locfileid: "69606382"
---
# <a name="-targetwinexe-c-compiler-options"></a><span data-ttu-id="b0d1d-102">-target:winexe (C# コンパイラ オプション)</span><span class="sxs-lookup"><span data-stu-id="b0d1d-102">-target:winexe (C# Compiler Options)</span></span>
<span data-ttu-id="b0d1d-103">**-target:winexe** オプションを使用すると、実行可能な (EXE) Windows プログラムがコンパイラによって作成されます。</span><span class="sxs-lookup"><span data-stu-id="b0d1d-103">The **-target:winexe** option causes the compiler to create an executable (EXE), Windows program.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0d1d-104">構文</span><span class="sxs-lookup"><span data-stu-id="b0d1d-104">Syntax</span></span>  
  
```console  
-target:winexe  
```  
  
## <a name="remarks"></a><span data-ttu-id="b0d1d-105">解説</span><span class="sxs-lookup"><span data-stu-id="b0d1d-105">Remarks</span></span>  
 <span data-ttu-id="b0d1d-106">実行可能ファイルは、.exe という拡張子で作成されます。</span><span class="sxs-lookup"><span data-stu-id="b0d1d-106">The executable file will be created with the .exe extension.</span></span> <span data-ttu-id="b0d1d-107">Windows プログラムは、.NET Framework ライブラリまたは Windows API のユーザー インターフェイスを提供するプログラムです。</span><span class="sxs-lookup"><span data-stu-id="b0d1d-107">A Windows program is one that provides a user interface from either the .NET Framework library or with the Windows APIs.</span></span>  
  
 <span data-ttu-id="b0d1d-108">コンソール アプリケーションを作成するには、[-target:exe](./target-exe-compiler-option.md) を使用します。</span><span class="sxs-lookup"><span data-stu-id="b0d1d-108">Use [-target:exe](./target-exe-compiler-option.md) to create a console application.</span></span>  
  
 <span data-ttu-id="b0d1d-109">[-out](./out-compiler-option.md) オプションで指定しない限り、出力ファイル名は [Main](../../programming-guide/main-and-command-args/index.md) メソッドを含む入力ファイルと同じになります。</span><span class="sxs-lookup"><span data-stu-id="b0d1d-109">Unless otherwise specified with the [-out](./out-compiler-option.md) option, the output file name takes the name of the input file that contains the [Main](../../programming-guide/main-and-command-args/index.md) method.</span></span>  
  
 <span data-ttu-id="b0d1d-110">コマンド ラインで指定すると、次の **-out** オプションまたは [-target](./target-compiler-option.md) オプションまでのすべてのファイルが、Windows プログラムの作成に使用されます。</span><span class="sxs-lookup"><span data-stu-id="b0d1d-110">When specified at the command line, all files until the next **-out** or [-target](./target-compiler-option.md) option are used to create the Windows program.</span></span>  
  
 <span data-ttu-id="b0d1d-111">**Main** メソッドは、.exe ファイルにコンパイルされるソース コード ファイル内に 1 つだけ必要です。</span><span class="sxs-lookup"><span data-stu-id="b0d1d-111">One and only one **Main** method is required in the source code files that are compiled into an .exe file.</span></span> <span data-ttu-id="b0d1d-112">コードに **Main** メソッドを含むクラスが複数ある場合は、[-main](./main-compiler-option.md) オプションを使用して、**Main** メソッドを含めるクラスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="b0d1d-112">The [-main](./main-compiler-option.md) option lets you specify which class contains the **Main** method, in cases where your code has more than one class with a **Main** method.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="b0d1d-113">Visual Studio 開発環境でこのコンパイラ オプションを設定するには</span><span class="sxs-lookup"><span data-stu-id="b0d1d-113">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="b0d1d-114">プロジェクトの **[プロパティ]** ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="b0d1d-114">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="b0d1d-115">**[アプリケーション]** プロパティ ページをクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0d1d-115">Click the **Application** property page.</span></span>  
  
3. <span data-ttu-id="b0d1d-116">**[出力の種類]** プロパティを変更します。</span><span class="sxs-lookup"><span data-stu-id="b0d1d-116">Modify the **Output type** property.</span></span>  
  
 <span data-ttu-id="b0d1d-117">このコンパイラ オプションをプログラムで設定する方法については、「 <xref:VSLangProj80.ProjectProperties3.OutputType%2A>」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b0d1d-117">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b0d1d-118">例</span><span class="sxs-lookup"><span data-stu-id="b0d1d-118">Example</span></span>  
 <span data-ttu-id="b0d1d-119">`in.cs` をコンパイルし、Windows プログラムを生成する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="b0d1d-119">Compile `in.cs` into a Windows program:</span></span>  
  
```console  
csc -target:winexe in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="b0d1d-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="b0d1d-120">See also</span></span>

- [<span data-ttu-id="b0d1d-121">-target (C# コンパイラ オプション)</span><span class="sxs-lookup"><span data-stu-id="b0d1d-121">-target (C# Compiler Options)</span></span>](./target-compiler-option.md)
- [<span data-ttu-id="b0d1d-122">C# コンパイラ オプション</span><span class="sxs-lookup"><span data-stu-id="b0d1d-122">C# Compiler Options</span></span>](./index.md)
