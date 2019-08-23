---
title: -bugreport
ms.date: 03/08/2018
helpviewer_keywords:
- -bugreport compiler option [Visual Basic]
- bugreport compiler option [Visual Basic]
- /bugreport compiler option [Visual Basic]
ms.assetid: e4325406-8dbd-4b48-b311-9ee0799e48bb
ms.openlocfilehash: 75c3e5842447a8f0812d5a90d7157f7a6a496936
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962445"
---
# <a name="-bugreport"></a><span data-ttu-id="a8294-102">-bugreport</span><span class="sxs-lookup"><span data-stu-id="a8294-102">-bugreport</span></span>
<span data-ttu-id="a8294-103">バグレポートをファイルするときに使用できるファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="a8294-103">Creates a file that you can use when you file a bug report.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8294-104">構文</span><span class="sxs-lookup"><span data-stu-id="a8294-104">Syntax</span></span>  
  
```  
-bugreport:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="a8294-105">引数</span><span class="sxs-lookup"><span data-stu-id="a8294-105">Arguments</span></span>  
  
|<span data-ttu-id="a8294-106">用語</span><span class="sxs-lookup"><span data-stu-id="a8294-106">Term</span></span>|<span data-ttu-id="a8294-107">定義</span><span class="sxs-lookup"><span data-stu-id="a8294-107">Definition</span></span>|  
|---|---|  
|`file`|<span data-ttu-id="a8294-108">必須。</span><span class="sxs-lookup"><span data-stu-id="a8294-108">Required.</span></span> <span data-ttu-id="a8294-109">バグレポートを格納するファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="a8294-109">The name of the file that will contain your bug report.</span></span> <span data-ttu-id="a8294-110">名前にスペースが含まれている場合は、ファイル名を引用符 ("") で囲みます。</span><span class="sxs-lookup"><span data-stu-id="a8294-110">Enclose the file name in quotation marks (" ") if the name contains a space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a8294-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="a8294-111">Remarks</span></span>  
 <span data-ttu-id="a8294-112">に`file`次の情報が追加されます。</span><span class="sxs-lookup"><span data-stu-id="a8294-112">The following information is added to `file`:</span></span>  
  
- <span data-ttu-id="a8294-113">コンパイル内のすべてのソースコードファイルのコピー。</span><span class="sxs-lookup"><span data-stu-id="a8294-113">A copy of all source-code files in the compilation.</span></span>  
  
- <span data-ttu-id="a8294-114">コンパイルで使用されるコンパイラオプションの一覧。</span><span class="sxs-lookup"><span data-stu-id="a8294-114">A list of the compiler options used in the compilation.</span></span>  
  
- <span data-ttu-id="a8294-115">コンパイラ、共通言語ランタイム、およびオペレーティングシステムに関するバージョン情報。</span><span class="sxs-lookup"><span data-stu-id="a8294-115">Version information about your compiler, common language runtime, and operating system.</span></span>  
  
- <span data-ttu-id="a8294-116">コンパイラの出力 (指定されている場合)。</span><span class="sxs-lookup"><span data-stu-id="a8294-116">Compiler output, if any.</span></span>  
  
- <span data-ttu-id="a8294-117">問題の説明。メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a8294-117">A description of the problem, for which you are prompted.</span></span>  
  
- <span data-ttu-id="a8294-118">問題の解決方法についての説明。確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a8294-118">A description of how you think the problem should be fixed, for which you are prompted.</span></span>  
  
 <span data-ttu-id="a8294-119">すべてのソースコードファイルのコピーがに`file`含まれているため、可能な限り最短のプログラムでコードの欠陥を再現することができます。</span><span class="sxs-lookup"><span data-stu-id="a8294-119">Because a copy of all source-code files is included in `file`, you may want to reproduce the (suspected) code defect in the shortest possible program.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="a8294-120">オプション`-bugreport`を指定すると、機密情報を含むファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="a8294-120">The `-bugreport` option produces a file that contains potentially sensitive information.</span></span> <span data-ttu-id="a8294-121">これには、現在の時刻、コンパイラのバージョン、.NET Framework バージョン、OS バージョン、ユーザー名、コンパイラが実行されたコマンドライン引数、すべてのソースコード、および参照アセンブリのバイナリ形式が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a8294-121">This includes current time, compiler version, .NET Framework version, OS version, user name, the command-line arguments with which the compiler was run, all source code, and the binary form of any referenced assembly.</span></span> <span data-ttu-id="a8294-122">このオプションにアクセスするには、web.config ファイルで ASP.NET アプリケーションのサーバー側コンパイルのコマンドラインオプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="a8294-122">This option can be accessed by specifying command-line options in the Web.config file for a server-side compilation of an ASP.NET application.</span></span> <span data-ttu-id="a8294-123">これを回避するには、machine.config ファイルを変更して、ユーザーがサーバーでコンパイルできないようにします。</span><span class="sxs-lookup"><span data-stu-id="a8294-123">To prevent this, modify the Machine.config file to disallow users from compiling on the server.</span></span>  
  
 <span data-ttu-id="a8294-124">`-errorreport:prompt`このオプションが、 `-errorreport:queue`、または`-errorreport:send`で使用されていて、アプリケーションで内部コンパイラエラーが発生`file`した場合は、の情報が Microsoft Corporation に送信されます。</span><span class="sxs-lookup"><span data-stu-id="a8294-124">If this option is used with `-errorreport:prompt`, `-errorreport:queue`, or `-errorreport:send`, and your application encounters an internal compiler error, the information in `file` is sent to Microsoft Corporation.</span></span> <span data-ttu-id="a8294-125">この情報は、Microsoft のエンジニアがエラーの原因を特定するのに役立ちます。また、Visual Basic の次のリリースの向上に役立つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="a8294-125">That information will help Microsoft engineers identify the cause of the error and may help improve the next release of Visual Basic.</span></span> <span data-ttu-id="a8294-126">既定では、情報は Microsoft に送信されません。</span><span class="sxs-lookup"><span data-stu-id="a8294-126">By default, no information is sent to Microsoft.</span></span> <span data-ttu-id="a8294-127">ただし、既定で有効になっている`-errorreport:queue`を使用してアプリケーションをコンパイルすると、アプリケーションはそのエラーレポートを収集します。</span><span class="sxs-lookup"><span data-stu-id="a8294-127">However, when you compile an application by using `-errorreport:queue`, which is enabled by default, the application collects its error reports.</span></span> <span data-ttu-id="a8294-128">その後、コンピューターの管理者がログインすると、エラー報告システムにポップアップウィンドウが表示され、ログオン後に発生したエラーレポートを管理者が Microsoft に転送できるようになります。</span><span class="sxs-lookup"><span data-stu-id="a8294-128">Then, when the computer's administrator logs in, the error reporting system displays a pop-up window that enables the administrator to forward to Microsoft any error reports that occurred since the logon.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a8294-129">この`/bugreport`オプションは、Visual Studio 開発環境内からは使用できません。コマンドラインからコンパイルする場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="a8294-129">The `/bugreport` option is not available from within the Visual Studio development environment; it is available only when you compile from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a8294-130">例</span><span class="sxs-lookup"><span data-stu-id="a8294-130">Example</span></span>  
 <span data-ttu-id="a8294-131">次の例で`T2.vb`は、すべてのバグ報告情報をコンパイルし`Problem.txt`てファイルに格納します。</span><span class="sxs-lookup"><span data-stu-id="a8294-131">The following example compiles `T2.vb` and puts all bug-reporting information in the file `Problem.txt`.</span></span>  
  
```  
vbc -bugreport:problem.txt t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="a8294-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="a8294-132">See also</span></span>

- [<span data-ttu-id="a8294-133">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="a8294-133">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="a8294-134">-debug (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a8294-134">-debug (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/debug.md)
- [<span data-ttu-id="a8294-135">-errorreport</span><span class="sxs-lookup"><span data-stu-id="a8294-135">-errorreport</span></span>](../../../visual-basic/reference/command-line-compiler/errorreport.md)
- [<span data-ttu-id="a8294-136">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="a8294-136">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- <span data-ttu-id="a8294-137">[Ws-securitypolicy の trustLevel 要素 (ASP.NET Settings スキーマ)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/as399f0x(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="a8294-137">[trustLevel Element for securityPolicy (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/as399f0x(v=vs.100))</span></span>
