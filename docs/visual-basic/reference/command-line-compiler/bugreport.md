---
title: -bugreport
ms.date: 03/08/2018
helpviewer_keywords:
- -bugreport compiler option [Visual Basic]
- bugreport compiler option [Visual Basic]
- /bugreport compiler option [Visual Basic]
ms.assetid: e4325406-8dbd-4b48-b311-9ee0799e48bb
ms.openlocfilehash: 02d84bceb0242988c70889ddd5d3dc7530f6e808
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793546"
---
# <a name="-bugreport"></a><span data-ttu-id="1d495-102">-bugreport</span><span class="sxs-lookup"><span data-stu-id="1d495-102">-bugreport</span></span>

<span data-ttu-id="1d495-103">バグレポートをファイルするときに使用できるファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="1d495-103">Creates a file that you can use when you file a bug report.</span></span>

## <a name="syntax"></a><span data-ttu-id="1d495-104">構文</span><span class="sxs-lookup"><span data-stu-id="1d495-104">Syntax</span></span>

```console
-bugreport:file
```

## <a name="arguments"></a><span data-ttu-id="1d495-105">引数</span><span class="sxs-lookup"><span data-stu-id="1d495-105">Arguments</span></span>

|<span data-ttu-id="1d495-106">用語</span><span class="sxs-lookup"><span data-stu-id="1d495-106">Term</span></span>|<span data-ttu-id="1d495-107">Definition</span><span class="sxs-lookup"><span data-stu-id="1d495-107">Definition</span></span>|
|---|---|
|`file`|<span data-ttu-id="1d495-108">必ず指定します。</span><span class="sxs-lookup"><span data-stu-id="1d495-108">Required.</span></span> <span data-ttu-id="1d495-109">バグレポートを格納するファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="1d495-109">The name of the file that will contain your bug report.</span></span> <span data-ttu-id="1d495-110">名前にスペースが含まれている場合は、ファイル名を引用符 ("") で囲みます。</span><span class="sxs-lookup"><span data-stu-id="1d495-110">Enclose the file name in quotation marks (" ") if the name contains a space.</span></span>|

## <a name="remarks"></a><span data-ttu-id="1d495-111">コメント</span><span class="sxs-lookup"><span data-stu-id="1d495-111">Remarks</span></span>

<span data-ttu-id="1d495-112">`file`に次の情報が追加されます。</span><span class="sxs-lookup"><span data-stu-id="1d495-112">The following information is added to `file`:</span></span>

- <span data-ttu-id="1d495-113">コンパイル内のすべてのソースコードファイルのコピー。</span><span class="sxs-lookup"><span data-stu-id="1d495-113">A copy of all source-code files in the compilation.</span></span>

- <span data-ttu-id="1d495-114">コンパイルで使用されるコンパイラオプションの一覧。</span><span class="sxs-lookup"><span data-stu-id="1d495-114">A list of the compiler options used in the compilation.</span></span>

- <span data-ttu-id="1d495-115">コンパイラ、共通言語ランタイム、およびオペレーティングシステムに関するバージョン情報。</span><span class="sxs-lookup"><span data-stu-id="1d495-115">Version information about your compiler, common language runtime, and operating system.</span></span>

- <span data-ttu-id="1d495-116">コンパイラの出力 (指定されている場合)。</span><span class="sxs-lookup"><span data-stu-id="1d495-116">Compiler output, if any.</span></span>

- <span data-ttu-id="1d495-117">問題の説明。メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1d495-117">A description of the problem, for which you are prompted.</span></span>

- <span data-ttu-id="1d495-118">問題の解決方法についての説明。確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1d495-118">A description of how you think the problem should be fixed, for which you are prompted.</span></span>

<span data-ttu-id="1d495-119">すべてのソースコードファイルのコピーが `file`に含まれているため、可能な限り短いプログラムで (疑わしい) コードの欠陥を再現することが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="1d495-119">Because a copy of all source-code files is included in `file`, you may want to reproduce the (suspected) code defect in the shortest possible program.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1d495-120">`-bugreport` オプションを指定すると、機密情報が含まれる可能性のあるファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="1d495-120">The `-bugreport` option produces a file that contains potentially sensitive information.</span></span> <span data-ttu-id="1d495-121">これには、現在の時刻、コンパイラのバージョン、.NET Framework バージョン、OS バージョン、ユーザー名、コンパイラが実行されたコマンドライン引数、すべてのソースコード、および参照アセンブリのバイナリ形式が含まれます。</span><span class="sxs-lookup"><span data-stu-id="1d495-121">This includes current time, compiler version, .NET Framework version, OS version, user name, the command-line arguments with which the compiler was run, all source code, and the binary form of any referenced assembly.</span></span> <span data-ttu-id="1d495-122">このオプションにアクセスするには、web.config ファイルで ASP.NET アプリケーションのサーバー側コンパイルのコマンドラインオプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="1d495-122">This option can be accessed by specifying command-line options in the Web.config file for a server-side compilation of an ASP.NET application.</span></span> <span data-ttu-id="1d495-123">これを回避するには、machine.config ファイルを変更して、ユーザーがサーバーでコンパイルできないようにします。</span><span class="sxs-lookup"><span data-stu-id="1d495-123">To prevent this, modify the Machine.config file to disallow users from compiling on the server.</span></span>

<span data-ttu-id="1d495-124">このオプションを `-errorreport:prompt`、`-errorreport:queue`、または `-errorreport:send`と共に使用し、アプリケーションで内部コンパイラエラーが発生した場合、`file` 内の情報が Microsoft Corporation に送信されます。</span><span class="sxs-lookup"><span data-stu-id="1d495-124">If this option is used with `-errorreport:prompt`, `-errorreport:queue`, or `-errorreport:send`, and your application encounters an internal compiler error, the information in `file` is sent to Microsoft Corporation.</span></span> <span data-ttu-id="1d495-125">この情報は、Microsoft のエンジニアがエラーの原因を特定するのに役立ちます。また、Visual Basic の次のリリースの向上に役立つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="1d495-125">That information will help Microsoft engineers identify the cause of the error and may help improve the next release of Visual Basic.</span></span> <span data-ttu-id="1d495-126">既定では、情報は Microsoft に送信されません。</span><span class="sxs-lookup"><span data-stu-id="1d495-126">By default, no information is sent to Microsoft.</span></span> <span data-ttu-id="1d495-127">ただし、既定で有効になっている `-errorreport:queue`を使用してアプリケーションをコンパイルすると、アプリケーションはそのエラーレポートを収集します。</span><span class="sxs-lookup"><span data-stu-id="1d495-127">However, when you compile an application by using `-errorreport:queue`, which is enabled by default, the application collects its error reports.</span></span> <span data-ttu-id="1d495-128">その後、コンピューターの管理者がログインすると、エラー報告システムにポップアップウィンドウが表示され、ログオン後に発生したエラーレポートを管理者が Microsoft に転送できるようになります。</span><span class="sxs-lookup"><span data-stu-id="1d495-128">Then, when the computer's administrator logs in, the error reporting system displays a pop-up window that enables the administrator to forward to Microsoft any error reports that occurred since the logon.</span></span>

> [!NOTE]
> <span data-ttu-id="1d495-129">`-bugreport` オプションは、Visual Studio 開発環境内からは使用できません。これは、コマンドラインからコンパイルする場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="1d495-129">The `-bugreport` option is not available from within the Visual Studio development environment; it is available only when you compile from the command line.</span></span>

## <a name="example"></a><span data-ttu-id="1d495-130">使用例</span><span class="sxs-lookup"><span data-stu-id="1d495-130">Example</span></span>

<span data-ttu-id="1d495-131">次の例では、 *T2*をコンパイルし、すべてのバグ報告情報をファイルの*問題 .txt*に配置します。</span><span class="sxs-lookup"><span data-stu-id="1d495-131">The following example compiles *T2.vb* and puts all bug-reporting information in the file *Problem.txt*.</span></span>

```console
vbc -bugreport:problem.txt t2.vb
```

## <a name="see-also"></a><span data-ttu-id="1d495-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="1d495-132">See also</span></span>

- [<span data-ttu-id="1d495-133">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="1d495-133">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="1d495-134">-debug (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1d495-134">-debug (Visual Basic)</span></span>](debug.md)
- [<span data-ttu-id="1d495-135">-errorreport</span><span class="sxs-lookup"><span data-stu-id="1d495-135">-errorreport</span></span>](errorreport.md)
- [<span data-ttu-id="1d495-136">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="1d495-136">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- <span data-ttu-id="1d495-137">[Ws-securitypolicy の trustLevel 要素 (ASP.NET Settings スキーマ)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/as399f0x(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="1d495-137">[trustLevel Element for securityPolicy (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/as399f0x(v=vs.100))</span></span>
