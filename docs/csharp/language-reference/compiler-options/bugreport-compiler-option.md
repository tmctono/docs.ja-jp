---
title: -bugreport (C# コンパイラ オプション)
ms.date: 07/20/2015
f1_keywords:
- /bugreport
helpviewer_keywords:
- /bugreport compiler option [C#]
- -bugreport compiler option [C#]
- bugreport compiler option [C#]
ms.assetid: f39665e3-4f6f-4357-88a2-3274c7bec0c1
ms.openlocfilehash: 0989678be070910c410d71717fe66679e1b70557
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2019
ms.locfileid: "69603085"
---
# <a name="-bugreport-c-compiler-options"></a><span data-ttu-id="6d217-102">-bugreport (C# コンパイラ オプション)</span><span class="sxs-lookup"><span data-stu-id="6d217-102">-bugreport (C# Compiler Options)</span></span>
<span data-ttu-id="6d217-103">後で分析を実行できるように、デバッグ情報をファイルに出力するよう指定します。</span><span class="sxs-lookup"><span data-stu-id="6d217-103">Specifies that debug information should be placed in a file for later analysis.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d217-104">構文</span><span class="sxs-lookup"><span data-stu-id="6d217-104">Syntax</span></span>  
  
```console  
-bugreport:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="6d217-105">引数</span><span class="sxs-lookup"><span data-stu-id="6d217-105">Arguments</span></span>  
 `file`  
 <span data-ttu-id="6d217-106">バグ レポートを作成するファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="6d217-106">The name of the file that you want to contain your bug report.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6d217-107">解説</span><span class="sxs-lookup"><span data-stu-id="6d217-107">Remarks</span></span>  
 <span data-ttu-id="6d217-108">**-bugreport** オプションを指定すると、次の情報が `file` に出力されます。</span><span class="sxs-lookup"><span data-stu-id="6d217-108">The **-bugreport** option specifies that the following information should be placed in `file`:</span></span>  
  
- <span data-ttu-id="6d217-109">コンパイルのすべてのソース コード ファイルのコピー。</span><span class="sxs-lookup"><span data-stu-id="6d217-109">A copy of all source code files in the compilation.</span></span>  
  
- <span data-ttu-id="6d217-110">コンパイルで使用されたコンパイラ オプションの一覧。</span><span class="sxs-lookup"><span data-stu-id="6d217-110">A listing of the compiler options used in the compilation.</span></span>  
  
- <span data-ttu-id="6d217-111">コンパイラ、ランタイム、およびオペレーティング システムのバージョン情報。</span><span class="sxs-lookup"><span data-stu-id="6d217-111">Version information about your compiler, run time, and operating system.</span></span>  
  
- <span data-ttu-id="6d217-112">16 進数として保存された参照アセンブリとモジュール (.NET Framework (SDK を含む) に付属のアセンブリを除く)。</span><span class="sxs-lookup"><span data-stu-id="6d217-112">Referenced assemblies and modules, saved as hexadecimal digits, except assemblies that ship with the .NET Framework and SDK.</span></span>  
  
- <span data-ttu-id="6d217-113">コンパイラの出力 (指定されている場合)。</span><span class="sxs-lookup"><span data-stu-id="6d217-113">Compiler output, if any.</span></span>  
  
- <span data-ttu-id="6d217-114">問題点の説明。プロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6d217-114">A description of the problem, which you will be prompted for.</span></span>  
  
- <span data-ttu-id="6d217-115">問題点の修正方法の説明。プロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6d217-115">A description of how you think the problem should be fixed, which you will be prompted for.</span></span>  
  
 <span data-ttu-id="6d217-116">このオプションに **-errorreport:prompt** または **-errorreport:send** を指定すると、ファイルに保存される情報が Microsoft Corporation に送信されます。</span><span class="sxs-lookup"><span data-stu-id="6d217-116">If this option is used with **-errorreport:prompt** or **-errorreport:send**, the information in the file will be sent to Microsoft Corporation.</span></span>  
  
 <span data-ttu-id="6d217-117">すべてのソース コード ファイルのコピーが `file` に出力されるため、問題があると思われるコードは、できるだけ小さなプログラムで再生成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6d217-117">Because a copy of all source code files will be placed in `file`, you might want to reproduce the suspected code defect in the shortest possible program.</span></span>  
  
 <span data-ttu-id="6d217-118">このコンパイラ オプションは Visual Studio では使用できず、プログラムで変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="6d217-118">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
 <span data-ttu-id="6d217-119">生成されたファイルの内容によってソース コードが公開され、意図しない情報開示につながる場合があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="6d217-119">Notice that contents of the generated file expose source code that could result in inadvertent information disclosure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d217-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="6d217-120">See also</span></span>

- [<span data-ttu-id="6d217-121">C# コンパイラ オプション</span><span class="sxs-lookup"><span data-stu-id="6d217-121">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="6d217-122">-errorreport (C# コンパイラ オプション)</span><span class="sxs-lookup"><span data-stu-id="6d217-122">-errorreport (C# Compiler Options)</span></span>](./errorreport-compiler-option.md)
- [<span data-ttu-id="6d217-123">プロジェクトおよびソリューションのプロパティの管理</span><span class="sxs-lookup"><span data-stu-id="6d217-123">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
