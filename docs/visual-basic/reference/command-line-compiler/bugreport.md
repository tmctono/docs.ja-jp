---
title: -bugreport
ms.date: 03/08/2018
helpviewer_keywords:
- -bugreport compiler option [Visual Basic]
- bugreport compiler option [Visual Basic]
- /bugreport compiler option [Visual Basic]
ms.assetid: e4325406-8dbd-4b48-b311-9ee0799e48bb
ms.openlocfilehash: 6ff9aa23fb6d7dee5c245ed174318f6589e7d245
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64624318"
---
# <a name="-bugreport"></a><span data-ttu-id="bf9a5-102">-bugreport</span><span class="sxs-lookup"><span data-stu-id="bf9a5-102">-bugreport</span></span>
<span data-ttu-id="bf9a5-103">バグ報告を提出するときに使用できるファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="bf9a5-103">Creates a file that you can use when you file a bug report.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf9a5-104">構文</span><span class="sxs-lookup"><span data-stu-id="bf9a5-104">Syntax</span></span>  
  
```  
-bugreport:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="bf9a5-105">引数</span><span class="sxs-lookup"><span data-stu-id="bf9a5-105">Arguments</span></span>  
  
|<span data-ttu-id="bf9a5-106">用語</span><span class="sxs-lookup"><span data-stu-id="bf9a5-106">Term</span></span>|<span data-ttu-id="bf9a5-107">定義</span><span class="sxs-lookup"><span data-stu-id="bf9a5-107">Definition</span></span>|  
|---|---|  
|`file`|<span data-ttu-id="bf9a5-108">必須。</span><span class="sxs-lookup"><span data-stu-id="bf9a5-108">Required.</span></span> <span data-ttu-id="bf9a5-109">バグ レポートを格納するファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="bf9a5-109">The name of the file that will contain your bug report.</span></span> <span data-ttu-id="bf9a5-110">ファイル名を引用符で囲みます ("")、名前にスペースが含まれている場合。</span><span class="sxs-lookup"><span data-stu-id="bf9a5-110">Enclose the file name in quotation marks (" ") if the name contains a space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bf9a5-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="bf9a5-111">Remarks</span></span>  
 <span data-ttu-id="bf9a5-112">次の情報に追加されます`file`:</span><span class="sxs-lookup"><span data-stu-id="bf9a5-112">The following information is added to `file`:</span></span>  
  
- <span data-ttu-id="bf9a5-113">コンパイルですべてのソース コード ファイルのコピー。</span><span class="sxs-lookup"><span data-stu-id="bf9a5-113">A copy of all source-code files in the compilation.</span></span>  
  
- <span data-ttu-id="bf9a5-114">コンパイルで使用されるコンパイラ オプションの一覧。</span><span class="sxs-lookup"><span data-stu-id="bf9a5-114">A list of the compiler options used in the compilation.</span></span>  
  
- <span data-ttu-id="bf9a5-115">コンパイラ、共通言語ランタイム、およびオペレーティング システムのバージョン情報。</span><span class="sxs-lookup"><span data-stu-id="bf9a5-115">Version information about your compiler, common language runtime, and operating system.</span></span>  
  
- <span data-ttu-id="bf9a5-116">コンパイラの出力 (指定されている場合)。</span><span class="sxs-lookup"><span data-stu-id="bf9a5-116">Compiler output, if any.</span></span>  
  
- <span data-ttu-id="bf9a5-117">求められることが、問題の説明です。</span><span class="sxs-lookup"><span data-stu-id="bf9a5-117">A description of the problem, for which you are prompted.</span></span>  
  
- <span data-ttu-id="bf9a5-118">求められることが問題をどのように考えるの説明を修正する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf9a5-118">A description of how you think the problem should be fixed, for which you are prompted.</span></span>  
  
 <span data-ttu-id="bf9a5-119">内のすべてのソース コード ファイルのコピーが含まれているため`file`、できるだけ小さなプログラムで (疑わしい) コード障害を再現したい場合があります。</span><span class="sxs-lookup"><span data-stu-id="bf9a5-119">Because a copy of all source-code files is included in `file`, you may want to reproduce the (suspected) code defect in the shortest possible program.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="bf9a5-120">`-bugreport`オプションは、機密性の高い情報を含むファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="bf9a5-120">The `-bugreport` option produces a file that contains potentially sensitive information.</span></span> <span data-ttu-id="bf9a5-121">これにより、コンパイラのバージョン、現在の時刻が含まれます。[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]バージョン、OS のバージョン、ユーザー名、、のコマンドライン引数をコンパイラが実行されたすべてのソース コードと参照アセンブリのいずれかのバイナリ形式です。</span><span class="sxs-lookup"><span data-stu-id="bf9a5-121">This includes current time, compiler version, [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] version, OS version, user name, the command-line arguments with which the compiler was run, all source code, and the binary form of any referenced assembly.</span></span> <span data-ttu-id="bf9a5-122">このオプションは、Web.config ファイルのサーバー側のコンパイルでのコマンド ライン オプションを指定することでアクセスできる、[!INCLUDE[vstecasp](~/includes/vstecasp-md.md)]アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="bf9a5-122">This option can be accessed by specifying command-line options in the Web.config file for a server-side compilation of an [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] application.</span></span> <span data-ttu-id="bf9a5-123">これを回避するには、サーバーでのコンパイルからユーザーを禁止する Machine.config ファイルを変更します。</span><span class="sxs-lookup"><span data-stu-id="bf9a5-123">To prevent this, modify the Machine.config file to disallow users from compiling on the server.</span></span>  
  
 <span data-ttu-id="bf9a5-124">このオプションを使用した場合`-errorreport:prompt`、 `-errorreport:queue`、または`-errorreport:send`、アプリケーションでの情報は、内部コンパイラ エラーが発生して`file`Microsoft Corporation に送信されます。</span><span class="sxs-lookup"><span data-stu-id="bf9a5-124">If this option is used with `-errorreport:prompt`, `-errorreport:queue`, or `-errorreport:send`, and your application encounters an internal compiler error, the information in `file` is sent to Microsoft Corporation.</span></span> <span data-ttu-id="bf9a5-125">この情報は、Microsoft のエンジニアが、エラーの原因の特定に役立つし、Visual Basic の次期リリースの改善に役立てます。</span><span class="sxs-lookup"><span data-stu-id="bf9a5-125">That information will help Microsoft engineers identify the cause of the error and may help improve the next release of Visual Basic.</span></span> <span data-ttu-id="bf9a5-126">既定では、Microsoft に情報は送信されません。</span><span class="sxs-lookup"><span data-stu-id="bf9a5-126">By default, no information is sent to Microsoft.</span></span> <span data-ttu-id="bf9a5-127">ただしを使用してアプリケーションをコンパイルするときに`-errorreport:queue`アプリケーションは、エラー レポートを収集、既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="bf9a5-127">However, when you compile an application by using `-errorreport:queue`, which is enabled by default, the application collects its error reports.</span></span> <span data-ttu-id="bf9a5-128">次に、コンピューターの管理者がログインすると、エラー レポート システムにログオン以降に発生したエラー レポートをマイクロソフトに送信できるようにするポップアップ ウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bf9a5-128">Then, when the computer's administrator logs in, the error reporting system displays a pop-up window that enables the administrator to forward to Microsoft any error reports that occurred since the logon.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bf9a5-129">`/bugreport`オプションは、Visual Studio 開発環境内からは使用できません。 コマンドラインからコンパイルするときにのみ、は使用できます。</span><span class="sxs-lookup"><span data-stu-id="bf9a5-129">The `/bugreport` option is not available from within the Visual Studio development environment; it is available only when you compile from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bf9a5-130">例</span><span class="sxs-lookup"><span data-stu-id="bf9a5-130">Example</span></span>  
 <span data-ttu-id="bf9a5-131">次の例をコンパイル`T2.vb`バグ レポートのすべての情報をファイルに格納`Problem.txt`します。</span><span class="sxs-lookup"><span data-stu-id="bf9a5-131">The following example compiles `T2.vb` and puts all bug-reporting information in the file `Problem.txt`.</span></span>  
  
```  
vbc -bugreport:problem.txt t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="bf9a5-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="bf9a5-132">See also</span></span>

- [<span data-ttu-id="bf9a5-133">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="bf9a5-133">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="bf9a5-134">-デバッグ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bf9a5-134">-debug (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/debug.md)
- [<span data-ttu-id="bf9a5-135">-errorreport</span><span class="sxs-lookup"><span data-stu-id="bf9a5-135">-errorreport</span></span>](../../../visual-basic/reference/command-line-compiler/errorreport.md)
- [<span data-ttu-id="bf9a5-136">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="bf9a5-136">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- <span data-ttu-id="bf9a5-137">[(ASP.NET 設定スキーマ) securityPolicy の trustLevel 要素](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/as399f0x(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="bf9a5-137">[trustLevel Element for securityPolicy (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/as399f0x(v=vs.100))</span></span>
