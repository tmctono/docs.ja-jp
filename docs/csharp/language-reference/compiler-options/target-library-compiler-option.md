---
description: -target:library (C# コンパイラ オプション)
title: -target:library (C# コンパイラ オプション)
ms.date: 07/20/2015
f1_keywords:
- /dll
helpviewer_keywords:
- -target compiler options [C#], /target:library
- target compiler options [C#], /target:library
- /target compiler options [C#], /target:library
ms.assetid: c5670e88-2126-47c1-8d1c-217923837d17
ms.openlocfilehash: 953249c4d0168ed3d279d03a0b2fb63d8ff6d5f5
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2020
ms.locfileid: "89128479"
---
# <a name="-targetlibrary-c-compiler-options"></a><span data-ttu-id="11774-103">-target:library (C# コンパイラ オプション)</span><span class="sxs-lookup"><span data-stu-id="11774-103">-target:library (C# Compiler Options)</span></span>
<span data-ttu-id="11774-104">**-target:library** オプションを指定した場合、コンパイラは実行可能ファイル (EXE) ではなく、ダイナミック リンク ライブラリ (DLL) を作成します。</span><span class="sxs-lookup"><span data-stu-id="11774-104">The **-target:library** option causes the compiler to create a dynamic-link library (DLL) rather than an executable file (EXE).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11774-105">構文</span><span class="sxs-lookup"><span data-stu-id="11774-105">Syntax</span></span>  
  
```console  
-target:library  
```  
  
## <a name="remarks"></a><span data-ttu-id="11774-106">解説</span><span class="sxs-lookup"><span data-stu-id="11774-106">Remarks</span></span>  
 <span data-ttu-id="11774-107">.dll 拡張子の DLL が作成されます。</span><span class="sxs-lookup"><span data-stu-id="11774-107">The DLL will be created with the .dll extension.</span></span>  
  
 <span data-ttu-id="11774-108">[-out](./out-compiler-option.md) オプションを特に指定しない限り、出力ファイル名は最初の入力ファイルと同じになります。</span><span class="sxs-lookup"><span data-stu-id="11774-108">Unless otherwise specified with the [-out](./out-compiler-option.md) option, the output file name takes the name of the first input file.</span></span>  
  
 <span data-ttu-id="11774-109">コマンド ラインで指定すると、次の **-out** または **-target:module** オプションまでのすべてのファイルが .dll ファイルを作成するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="11774-109">When specified at the command line, all files up to the next **-out** or **-target:module** option are used to create the .dll file.</span></span>  
  
 <span data-ttu-id="11774-110">.dll ファイルを作成する際に、[Main](../../programming-guide/main-and-command-args/index.md)メソッドは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="11774-110">When building a .dll file, a [Main](../../programming-guide/main-and-command-args/index.md) method is not required.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="11774-111">Visual Studio 開発環境でこのコンパイラ オプションを設定するには</span><span class="sxs-lookup"><span data-stu-id="11774-111">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="11774-112">プロジェクトの **[プロパティ]** ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="11774-112">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="11774-113">**[アプリケーション]** プロパティ ページをクリックします。</span><span class="sxs-lookup"><span data-stu-id="11774-113">Click the **Application** property page.</span></span>  
  
3. <span data-ttu-id="11774-114">**[出力の種類]** プロパティを変更します。</span><span class="sxs-lookup"><span data-stu-id="11774-114">Modify the **Output type** property.</span></span>  
  
 <span data-ttu-id="11774-115">このコンパイラ オプションをプログラムで設定する方法については、「<xref:VSLangProj80.ProjectProperties3.OutputType%2A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="11774-115">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="11774-116">例</span><span class="sxs-lookup"><span data-stu-id="11774-116">Example</span></span>  
 <span data-ttu-id="11774-117">`in.cs` をコンパイルし、`in.dll` を作成するには、次のコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="11774-117">Compile `in.cs`, creating `in.dll`:</span></span>  
  
```console  
csc -target:library in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="11774-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="11774-118">See also</span></span>

- [<span data-ttu-id="11774-119">-target (C# コンパイラ オプション)</span><span class="sxs-lookup"><span data-stu-id="11774-119">-target (C# Compiler Options)</span></span>](./target-compiler-option.md)
- [<span data-ttu-id="11774-120">C# コンパイラ オプション</span><span class="sxs-lookup"><span data-stu-id="11774-120">C# Compiler Options</span></span>](./index.md)
