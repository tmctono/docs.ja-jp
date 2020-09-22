---
title: -bugreport
ms.date: 03/08/2018
helpviewer_keywords:
- -bugreport compiler option [Visual Basic]
- bugreport compiler option [Visual Basic]
- /bugreport compiler option [Visual Basic]
ms.assetid: e4325406-8dbd-4b48-b311-9ee0799e48bb
ms.openlocfilehash: 4b468b8ee4301693312e9545396f2b9f495f75d8
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90550912"
---
# <a name="-bugreport"></a><span data-ttu-id="9b76b-102">-bugreport</span><span class="sxs-lookup"><span data-stu-id="9b76b-102">-bugreport</span></span>

<span data-ttu-id="9b76b-103">バグ レポートを提出するときに使用できるファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="9b76b-103">Creates a file that you can use when you file a bug report.</span></span>

## <a name="syntax"></a><span data-ttu-id="9b76b-104">構文</span><span class="sxs-lookup"><span data-stu-id="9b76b-104">Syntax</span></span>

```console
-bugreport:file
```

## <a name="arguments"></a><span data-ttu-id="9b76b-105">引数</span><span class="sxs-lookup"><span data-stu-id="9b76b-105">Arguments</span></span>

|<span data-ttu-id="9b76b-106">用語</span><span class="sxs-lookup"><span data-stu-id="9b76b-106">Term</span></span>|<span data-ttu-id="9b76b-107">定義</span><span class="sxs-lookup"><span data-stu-id="9b76b-107">Definition</span></span>|
|---|---|
|`file`|<span data-ttu-id="9b76b-108">必須です。</span><span class="sxs-lookup"><span data-stu-id="9b76b-108">Required.</span></span> <span data-ttu-id="9b76b-109">バグ レポートが含まれるファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="9b76b-109">The name of the file that will contain your bug report.</span></span> <span data-ttu-id="9b76b-110">ファイル名に空白が含まれている場合は、名前を二重引用符 (" ") で囲みます。</span><span class="sxs-lookup"><span data-stu-id="9b76b-110">Enclose the file name in quotation marks (" ") if the name contains a space.</span></span>|

## <a name="remarks"></a><span data-ttu-id="9b76b-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="9b76b-111">Remarks</span></span>

<span data-ttu-id="9b76b-112">`file` に次の情報が追加されます。</span><span class="sxs-lookup"><span data-stu-id="9b76b-112">The following information is added to `file`:</span></span>

- <span data-ttu-id="9b76b-113">コンパイル時のすべてのソースコード ファイルのコピー。</span><span class="sxs-lookup"><span data-stu-id="9b76b-113">A copy of all source-code files in the compilation.</span></span>

- <span data-ttu-id="9b76b-114">コンパイルで使用されたコンパイラ オプションの一覧。</span><span class="sxs-lookup"><span data-stu-id="9b76b-114">A list of the compiler options used in the compilation.</span></span>

- <span data-ttu-id="9b76b-115">コンパイラ、共通言語ランタイム、およびオペレーティング システムに関するバージョン情報。</span><span class="sxs-lookup"><span data-stu-id="9b76b-115">Version information about your compiler, common language runtime, and operating system.</span></span>

- <span data-ttu-id="9b76b-116">コンパイラの出力 (指定されている場合)。</span><span class="sxs-lookup"><span data-stu-id="9b76b-116">Compiler output, if any.</span></span>

- <span data-ttu-id="9b76b-117">問題の説明。プロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9b76b-117">A description of the problem, for which you are prompted.</span></span>

- <span data-ttu-id="9b76b-118">問題の修正方法についての説明。プロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9b76b-118">A description of how you think the problem should be fixed, for which you are prompted.</span></span>

<span data-ttu-id="9b76b-119">すべてのソースコード ファイルのコピーが `file` に含まれるため、できるだけ短いプログラムで (疑わしい) コードの欠陥を再現することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9b76b-119">Because a copy of all source-code files is included in `file`, you may want to reproduce the (suspected) code defect in the shortest possible program.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9b76b-120">`-bugreport` オプションを指定すると、機密情報が含まれる可能性のあるファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="9b76b-120">The `-bugreport` option produces a file that contains potentially sensitive information.</span></span> <span data-ttu-id="9b76b-121">これには、現在の時刻、コンパイラ バージョン、.NET Framework バージョン、OS バージョン、ユーザー名、コンパイラが実行されたときのコマンドライン引数、すべてのソース コード、および参照アセンブリのバイナリ形式が含まれます。</span><span class="sxs-lookup"><span data-stu-id="9b76b-121">This includes current time, compiler version, .NET Framework version, OS version, user name, the command-line arguments with which the compiler was run, all source code, and the binary form of any referenced assembly.</span></span> <span data-ttu-id="9b76b-122">このオプションには、Web.config ファイルで ASP.NET アプリケーションのサーバー側コンパイルのコマンドライン オプションを指定することでアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="9b76b-122">This option can be accessed by specifying command-line options in the Web.config file for a server-side compilation of an ASP.NET application.</span></span> <span data-ttu-id="9b76b-123">これを回避するには、Machine.config ファイルを変更して、ユーザーがサーバーでコンパイルできないようにします。</span><span class="sxs-lookup"><span data-stu-id="9b76b-123">To prevent this, modify the Machine.config file to disallow users from compiling on the server.</span></span>

<span data-ttu-id="9b76b-124">このオプションが `-errorreport:prompt`、`-errorreport:queue`、または `-errorreport:send` と共に使用され、アプリケーションで内部コンパイラ エラーが発生した場合、`file` 内の情報が Microsoft Corporation に送信されます。</span><span class="sxs-lookup"><span data-stu-id="9b76b-124">If this option is used with `-errorreport:prompt`, `-errorreport:queue`, or `-errorreport:send`, and your application encounters an internal compiler error, the information in `file` is sent to Microsoft Corporation.</span></span> <span data-ttu-id="9b76b-125">その情報は、Microsoft のエンジニアがエラーの原因を特定するのに役立ちます。また、Visual Basic の次のリリースの向上に役立つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="9b76b-125">That information will help Microsoft engineers identify the cause of the error and may help improve the next release of Visual Basic.</span></span> <span data-ttu-id="9b76b-126">既定では、情報は Microsoft に送信されません。</span><span class="sxs-lookup"><span data-stu-id="9b76b-126">By default, no information is sent to Microsoft.</span></span> <span data-ttu-id="9b76b-127">しかし、既定で有効になっている `-errorreport:queue` を使用して、アプリケーションをコンパイルすると、アプリケーションによってそのエラー レポートが収集されます。</span><span class="sxs-lookup"><span data-stu-id="9b76b-127">However, when you compile an application by using `-errorreport:queue`, which is enabled by default, the application collects its error reports.</span></span> <span data-ttu-id="9b76b-128">その後、コンピューターの管理者がログインすると、エラー レポート システムにポップアップ ウィンドウが表示され、ログオン後に発生したエラー レポートを管理者が Microsoft に転送できるようになります。</span><span class="sxs-lookup"><span data-stu-id="9b76b-128">Then, when the computer's administrator logs in, the error reporting system displays a pop-up window that enables the administrator to forward to Microsoft any error reports that occurred since the logon.</span></span>

> [!NOTE]
> <span data-ttu-id="9b76b-129">`-bugreport` オプションは、Visual Studio 開発環境内からは利用できません。これはコマンド ラインからコンパイルするときにのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="9b76b-129">The `-bugreport` option is not available from within the Visual Studio development environment; it is available only when you compile from the command line.</span></span>

## <a name="example"></a><span data-ttu-id="9b76b-130">例</span><span class="sxs-lookup"><span data-stu-id="9b76b-130">Example</span></span>

<span data-ttu-id="9b76b-131">次の例では、*T2.vb* をコンパイルし、すべてのバグ レポート情報を *Problem.txt* ファイルに配置します。</span><span class="sxs-lookup"><span data-stu-id="9b76b-131">The following example compiles *T2.vb* and puts all bug-reporting information in the file *Problem.txt*.</span></span>

```console
vbc -bugreport:problem.txt t2.vb
```

## <a name="see-also"></a><span data-ttu-id="9b76b-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="9b76b-132">See also</span></span>

- [<span data-ttu-id="9b76b-133">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="9b76b-133">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="9b76b-134">-debug (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9b76b-134">-debug (Visual Basic)</span></span>](debug.md)
- [<span data-ttu-id="9b76b-135">-errorreport</span><span class="sxs-lookup"><span data-stu-id="9b76b-135">-errorreport</span></span>](errorreport.md)
- [<span data-ttu-id="9b76b-136">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="9b76b-136">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- <span data-ttu-id="9b76b-137">[securityPolicy の trustLevel 要素 (ASP.NET 設定スキーマ)](/previous-versions/dotnet/netframework-4.0/as399f0x(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="9b76b-137">[trustLevel Element for securityPolicy (ASP.NET Settings Schema)](/previous-versions/dotnet/netframework-4.0/as399f0x(v=vs.100))</span></span>
