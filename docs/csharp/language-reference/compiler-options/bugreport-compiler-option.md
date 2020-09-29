---
description: -bugreport (C# コンパイラ オプション)
title: -bugreport (C# コンパイラ オプション)
ms.date: 07/20/2015
f1_keywords:
- /bugreport
helpviewer_keywords:
- /bugreport compiler option [C#]
- -bugreport compiler option [C#]
- bugreport compiler option [C#]
ms.assetid: f39665e3-4f6f-4357-88a2-3274c7bec0c1
ms.openlocfilehash: 2afab44eec0c7bcc9809b458be0348093cb6dd07
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91196820"
---
# <a name="-bugreport-c-compiler-options"></a><span data-ttu-id="6cbcb-103">-bugreport (C# コンパイラ オプション)</span><span class="sxs-lookup"><span data-stu-id="6cbcb-103">-bugreport (C# Compiler Options)</span></span>

<span data-ttu-id="6cbcb-104">後で分析を実行できるように、デバッグ情報をファイルに出力するよう指定します。</span><span class="sxs-lookup"><span data-stu-id="6cbcb-104">Specifies that debug information should be placed in a file for later analysis.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6cbcb-105">構文</span><span class="sxs-lookup"><span data-stu-id="6cbcb-105">Syntax</span></span>  
  
```console  
-bugreport:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="6cbcb-106">引数</span><span class="sxs-lookup"><span data-stu-id="6cbcb-106">Arguments</span></span>  

 `file`  
 <span data-ttu-id="6cbcb-107">バグ レポートを作成するファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="6cbcb-107">The name of the file that you want to contain your bug report.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6cbcb-108">注釈</span><span class="sxs-lookup"><span data-stu-id="6cbcb-108">Remarks</span></span>  

 <span data-ttu-id="6cbcb-109">**-bugreport** オプションを指定すると、次の情報が `file` に出力されます。</span><span class="sxs-lookup"><span data-stu-id="6cbcb-109">The **-bugreport** option specifies that the following information should be placed in `file`:</span></span>  
  
- <span data-ttu-id="6cbcb-110">コンパイルのすべてのソース コード ファイルのコピー。</span><span class="sxs-lookup"><span data-stu-id="6cbcb-110">A copy of all source code files in the compilation.</span></span>  
  
- <span data-ttu-id="6cbcb-111">コンパイルで使用されたコンパイラ オプションの一覧。</span><span class="sxs-lookup"><span data-stu-id="6cbcb-111">A listing of the compiler options used in the compilation.</span></span>  
  
- <span data-ttu-id="6cbcb-112">コンパイラ、ランタイム、およびオペレーティング システムのバージョン情報。</span><span class="sxs-lookup"><span data-stu-id="6cbcb-112">Version information about your compiler, run time, and operating system.</span></span>  
  
- <span data-ttu-id="6cbcb-113">16 進数として保存された参照アセンブリとモジュール (.NET Framework (SDK を含む) に付属のアセンブリを除く)。</span><span class="sxs-lookup"><span data-stu-id="6cbcb-113">Referenced assemblies and modules, saved as hexadecimal digits, except assemblies that ship with the .NET Framework and SDK.</span></span>  
  
- <span data-ttu-id="6cbcb-114">コンパイラの出力 (指定されている場合)。</span><span class="sxs-lookup"><span data-stu-id="6cbcb-114">Compiler output, if any.</span></span>  
  
- <span data-ttu-id="6cbcb-115">問題点の説明。プロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6cbcb-115">A description of the problem, which you will be prompted for.</span></span>  
  
- <span data-ttu-id="6cbcb-116">問題点の修正方法の説明。プロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6cbcb-116">A description of how you think the problem should be fixed, which you will be prompted for.</span></span>  
  
 <span data-ttu-id="6cbcb-117">このオプションに **-errorreport:prompt** または **-errorreport:send** を指定すると、ファイルに保存される情報が Microsoft Corporation に送信されます。</span><span class="sxs-lookup"><span data-stu-id="6cbcb-117">If this option is used with **-errorreport:prompt** or **-errorreport:send**, the information in the file will be sent to Microsoft Corporation.</span></span>  
  
 <span data-ttu-id="6cbcb-118">すべてのソース コード ファイルのコピーが `file` に出力されるため、問題があると思われるコードは、できるだけ小さなプログラムで再生成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6cbcb-118">Because a copy of all source code files will be placed in `file`, you might want to reproduce the suspected code defect in the shortest possible program.</span></span>  
  
 <span data-ttu-id="6cbcb-119">このコンパイラ オプションは Visual Studio では使用できず、プログラムで変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="6cbcb-119">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
 <span data-ttu-id="6cbcb-120">生成されたファイルの内容によってソース コードが公開され、意図しない情報開示につながる場合があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="6cbcb-120">Notice that contents of the generated file expose source code that could result in inadvertent information disclosure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6cbcb-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="6cbcb-121">See also</span></span>

- [<span data-ttu-id="6cbcb-122">C# コンパイラ オプション</span><span class="sxs-lookup"><span data-stu-id="6cbcb-122">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="6cbcb-123">-errorreport (C# コンパイラ オプション)</span><span class="sxs-lookup"><span data-stu-id="6cbcb-123">-errorreport (C# Compiler Options)</span></span>](./errorreport-compiler-option.md)
- [<span data-ttu-id="6cbcb-124">プロジェクトおよびソリューションのプロパティの管理</span><span class="sxs-lookup"><span data-stu-id="6cbcb-124">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
