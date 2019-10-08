---
title: -bugreport
ms.date: 03/08/2018
helpviewer_keywords:
- -bugreport compiler option [Visual Basic]
- bugreport compiler option [Visual Basic]
- /bugreport compiler option [Visual Basic]
ms.assetid: e4325406-8dbd-4b48-b311-9ee0799e48bb
ms.openlocfilehash: 46d726332806f7d1f6e80dd7df31867051276b45
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2019
ms.locfileid: "72002349"
---
# <a name="-bugreport"></a><span data-ttu-id="d9c53-102">-bugreport</span><span class="sxs-lookup"><span data-stu-id="d9c53-102">-bugreport</span></span>
<span data-ttu-id="d9c53-103">バグレポートをファイルするときに使用できるファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="d9c53-103">Creates a file that you can use when you file a bug report.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9c53-104">構文</span><span class="sxs-lookup"><span data-stu-id="d9c53-104">Syntax</span></span>  
  
```  
-bugreport:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="d9c53-105">引数</span><span class="sxs-lookup"><span data-stu-id="d9c53-105">Arguments</span></span>  
  
|<span data-ttu-id="d9c53-106">項目</span><span class="sxs-lookup"><span data-stu-id="d9c53-106">Term</span></span>|<span data-ttu-id="d9c53-107">定義</span><span class="sxs-lookup"><span data-stu-id="d9c53-107">Definition</span></span>|  
|---|---|  
|`file`|<span data-ttu-id="d9c53-108">必須。</span><span class="sxs-lookup"><span data-stu-id="d9c53-108">Required.</span></span> <span data-ttu-id="d9c53-109">バグレポートを格納するファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="d9c53-109">The name of the file that will contain your bug report.</span></span> <span data-ttu-id="d9c53-110">名前にスペースが含まれている場合は、ファイル名を引用符 ("") で囲みます。</span><span class="sxs-lookup"><span data-stu-id="d9c53-110">Enclose the file name in quotation marks (" ") if the name contains a space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d9c53-111">コメント</span><span class="sxs-lookup"><span data-stu-id="d9c53-111">Remarks</span></span>  
 <span data-ttu-id="d9c53-112">次の情報が `file` に追加されます。</span><span class="sxs-lookup"><span data-stu-id="d9c53-112">The following information is added to `file`:</span></span>  
  
- <span data-ttu-id="d9c53-113">コンパイル内のすべてのソースコードファイルのコピー。</span><span class="sxs-lookup"><span data-stu-id="d9c53-113">A copy of all source-code files in the compilation.</span></span>  
  
- <span data-ttu-id="d9c53-114">コンパイルで使用されるコンパイラオプションの一覧。</span><span class="sxs-lookup"><span data-stu-id="d9c53-114">A list of the compiler options used in the compilation.</span></span>  
  
- <span data-ttu-id="d9c53-115">コンパイラ、共通言語ランタイム、およびオペレーティングシステムに関するバージョン情報。</span><span class="sxs-lookup"><span data-stu-id="d9c53-115">Version information about your compiler, common language runtime, and operating system.</span></span>  
  
- <span data-ttu-id="d9c53-116">コンパイラの出力 (指定されている場合)。</span><span class="sxs-lookup"><span data-stu-id="d9c53-116">Compiler output, if any.</span></span>  
  
- <span data-ttu-id="d9c53-117">問題の説明。メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d9c53-117">A description of the problem, for which you are prompted.</span></span>  
  
- <span data-ttu-id="d9c53-118">問題の解決方法についての説明。確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d9c53-118">A description of how you think the problem should be fixed, for which you are prompted.</span></span>  
  
 <span data-ttu-id="d9c53-119">すべてのソースコードファイルのコピーが `file` に含まれるため、可能な限り短いプログラムで (疑わしい) コードの欠陥を再現することができます。</span><span class="sxs-lookup"><span data-stu-id="d9c53-119">Because a copy of all source-code files is included in `file`, you may want to reproduce the (suspected) code defect in the shortest possible program.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="d9c53-120">@No__t-0 オプションを指定すると、機密情報が含まれる可能性のあるファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="d9c53-120">The `-bugreport` option produces a file that contains potentially sensitive information.</span></span> <span data-ttu-id="d9c53-121">これには、現在の時刻、コンパイラのバージョン、.NET Framework バージョン、OS バージョン、ユーザー名、コンパイラが実行されたコマンドライン引数、すべてのソースコード、および参照アセンブリのバイナリ形式が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d9c53-121">This includes current time, compiler version, .NET Framework version, OS version, user name, the command-line arguments with which the compiler was run, all source code, and the binary form of any referenced assembly.</span></span> <span data-ttu-id="d9c53-122">このオプションにアクセスするには、web.config ファイルで ASP.NET アプリケーションのサーバー側コンパイルのコマンドラインオプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="d9c53-122">This option can be accessed by specifying command-line options in the Web.config file for a server-side compilation of an ASP.NET application.</span></span> <span data-ttu-id="d9c53-123">これを回避するには、machine.config ファイルを変更して、ユーザーがサーバーでコンパイルできないようにします。</span><span class="sxs-lookup"><span data-stu-id="d9c53-123">To prevent this, modify the Machine.config file to disallow users from compiling on the server.</span></span>  
  
 <span data-ttu-id="d9c53-124">このオプションを `-errorreport:prompt`、`-errorreport:queue`、または `-errorreport:send` と共に使用し、アプリケーションで内部コンパイラエラーが発生した場合は、`file` の情報が Microsoft Corporation に送信されます。</span><span class="sxs-lookup"><span data-stu-id="d9c53-124">If this option is used with `-errorreport:prompt`, `-errorreport:queue`, or `-errorreport:send`, and your application encounters an internal compiler error, the information in `file` is sent to Microsoft Corporation.</span></span> <span data-ttu-id="d9c53-125">この情報は、Microsoft のエンジニアがエラーの原因を特定するのに役立ちます。また、Visual Basic の次のリリースの向上に役立つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="d9c53-125">That information will help Microsoft engineers identify the cause of the error and may help improve the next release of Visual Basic.</span></span> <span data-ttu-id="d9c53-126">既定では、情報は Microsoft に送信されません。</span><span class="sxs-lookup"><span data-stu-id="d9c53-126">By default, no information is sent to Microsoft.</span></span> <span data-ttu-id="d9c53-127">ただし、既定で有効になっている `-errorreport:queue` を使用してアプリケーションをコンパイルすると、アプリケーションはそのエラーレポートを収集します。</span><span class="sxs-lookup"><span data-stu-id="d9c53-127">However, when you compile an application by using `-errorreport:queue`, which is enabled by default, the application collects its error reports.</span></span> <span data-ttu-id="d9c53-128">その後、コンピューターの管理者がログインすると、エラー報告システムにポップアップウィンドウが表示され、ログオン後に発生したエラーレポートを管理者が Microsoft に転送できるようになります。</span><span class="sxs-lookup"><span data-stu-id="d9c53-128">Then, when the computer's administrator logs in, the error reporting system displays a pop-up window that enables the administrator to forward to Microsoft any error reports that occurred since the logon.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d9c53-129">@No__t-0 オプションは、Visual Studio 開発環境内からは使用できません。これは、コマンドラインからコンパイルする場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="d9c53-129">The `/bugreport` option is not available from within the Visual Studio development environment; it is available only when you compile from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d9c53-130">例</span><span class="sxs-lookup"><span data-stu-id="d9c53-130">Example</span></span>  
 <span data-ttu-id="d9c53-131">次の例では、`T2.vb` をコンパイルし、すべてのバグ報告情報をファイル `Problem.txt` に格納します。</span><span class="sxs-lookup"><span data-stu-id="d9c53-131">The following example compiles `T2.vb` and puts all bug-reporting information in the file `Problem.txt`.</span></span>  
  
```console  
vbc -bugreport:problem.txt t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="d9c53-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="d9c53-132">See also</span></span>

- [<span data-ttu-id="d9c53-133">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="d9c53-133">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="d9c53-134">-debug (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d9c53-134">-debug (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/debug.md)
- [<span data-ttu-id="d9c53-135">-errorreport</span><span class="sxs-lookup"><span data-stu-id="d9c53-135">-errorreport</span></span>](../../../visual-basic/reference/command-line-compiler/errorreport.md)
- [<span data-ttu-id="d9c53-136">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="d9c53-136">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- <span data-ttu-id="d9c53-137">[Ws-securitypolicy の trustLevel 要素 (ASP.NET Settings スキーマ)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/as399f0x(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="d9c53-137">[trustLevel Element for securityPolicy (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/as399f0x(v=vs.100))</span></span>
