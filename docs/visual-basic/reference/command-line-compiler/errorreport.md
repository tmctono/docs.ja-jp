---
title: -errorreport
ms.date: 08/14/2018
helpviewer_keywords:
- -errorreport compiler option [Visual Basic]
- /errorreport compiler option [Visual Basic]
- errorreport compiler option [Visual Basic]
ms.assetid: a7fe83a2-a6d8-460c-8dad-79a8f433f501
ms.openlocfilehash: 5471f0783eee5e2c14cf0f140094d5c292a73756
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61663259"
---
# <a name="-errorreport"></a><span data-ttu-id="c1a80-102">-errorreport</span><span class="sxs-lookup"><span data-stu-id="c1a80-102">-errorreport</span></span>

<span data-ttu-id="c1a80-103">Visual Basic コンパイラが内部コンパイラ エラーを報告する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="c1a80-103">Specifies how the Visual Basic compiler should report internal compiler errors.</span></span>

## <a name="syntax"></a><span data-ttu-id="c1a80-104">構文</span><span class="sxs-lookup"><span data-stu-id="c1a80-104">Syntax</span></span>

```
-errorreport:{ prompt | queue | send | none }
```

## <a name="remarks"></a><span data-ttu-id="c1a80-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="c1a80-105">Remarks</span></span>

<span data-ttu-id="c1a80-106">このオプションは、microsoft Visual Basic チームに Visual Basic 内部コンパイラ エラー (ICE) を報告する便利な手段を提供します。</span><span class="sxs-lookup"><span data-stu-id="c1a80-106">This option provides a convenient way to report a Visual Basic internal compiler error (ICE) to the Visual Basic team at Microsoft.</span></span> <span data-ttu-id="c1a80-107">既定では、コンパイラによってありませんマイクロソフトに情報。</span><span class="sxs-lookup"><span data-stu-id="c1a80-107">By default, the compiler sends no information to Microsoft.</span></span> <span data-ttu-id="c1a80-108">ただし、内部コンパイラ エラーが発生した場合このオプションを使用できます、エラーを Microsoft に報告します。</span><span class="sxs-lookup"><span data-stu-id="c1a80-108">However, if you do encounter an internal compiler error, this option allows you to report the error to Microsoft.</span></span> <span data-ttu-id="c1a80-109">この情報は、Microsoft のエンジニアが原因の特定に役立つし、Visual Basic の次期リリースの改善に役立てます。</span><span class="sxs-lookup"><span data-stu-id="c1a80-109">That information will help Microsoft engineers identify the cause and may help improve the next release of Visual Basic.</span></span>

<span data-ttu-id="c1a80-110">レポートを送信するユーザーの機能は、コンピューターとユーザー ポリシーのアクセス許可によって異なります。</span><span class="sxs-lookup"><span data-stu-id="c1a80-110">A user's ability to send reports depends on machine and user policy permissions.</span></span>

<span data-ttu-id="c1a80-111">次の表に、効果、`-errorreport`オプション。</span><span class="sxs-lookup"><span data-stu-id="c1a80-111">The following table summarizes the effect of the `-errorreport` option.</span></span>

|<span data-ttu-id="c1a80-112">オプション</span><span class="sxs-lookup"><span data-stu-id="c1a80-112">Option</span></span>|<span data-ttu-id="c1a80-113">動作</span><span class="sxs-lookup"><span data-stu-id="c1a80-113">Behavior</span></span>|
|---|---|
|`prompt`|<span data-ttu-id="c1a80-114">内部コンパイラ エラーが発生する場合は、コンパイラが収集された正確なデータを表示できるように、ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c1a80-114">If an internal compiler error occurs, a dialog box comes up so that you can view the exact data that the compiler collected.</span></span> <span data-ttu-id="c1a80-115">エラー報告の機密情報があるかを判断し、マイクロソフトに送信するかどうかを判断することできます。</span><span class="sxs-lookup"><span data-stu-id="c1a80-115">You can determine if there is any sensitive information in the error report and make a decision on whether to send it to Microsoft.</span></span> <span data-ttu-id="c1a80-116">送信することを決定するコンピューターおよびユーザー ポリシー設定で許可する場合は、コンパイラは、データを Microsoft に送信します。</span><span class="sxs-lookup"><span data-stu-id="c1a80-116">If you decide to send it, and the machine and user policy settings allow it, the compiler sends the data to Microsoft.</span></span>|
|`queue`|<span data-ttu-id="c1a80-117">エラー レポートを待ち行列に入れます。</span><span class="sxs-lookup"><span data-stu-id="c1a80-117">Queues the error report.</span></span> <span data-ttu-id="c1a80-118">前回のログに記録されたすべてのエラーを報告するには管理者特権でログインすると (ことが求められない 3 日間に 2 回以上のエラー レポートを送信する)。</span><span class="sxs-lookup"><span data-stu-id="c1a80-118">When you log in with administrator privileges, you can report any failures since the last time you were logged in (you will not be prompted to send reports for failures more than once every three days).</span></span> <span data-ttu-id="c1a80-119">これは、既定の動作と、`-errorreport`オプションが指定されていません。</span><span class="sxs-lookup"><span data-stu-id="c1a80-119">This is the default behavior when the `-errorreport` option is not specified.</span></span>|
|`send`|<span data-ttu-id="c1a80-120">内部コンパイラ エラーが発生するコンピューターとユーザー ポリシーの設定で許可する場合は、コンパイラは、データを Microsoft に送信します。</span><span class="sxs-lookup"><span data-stu-id="c1a80-120">If an internal compiler error occurs, and the machine and user policy settings allow it, the compiler sends the data to Microsoft.</span></span><br /><br /> <span data-ttu-id="c1a80-121">オプション`-errorreport:send`によってレポートが有効になっている場合は、Microsoft にエラー情報を自動的に送信しようとしています、 [Windows エラー報告](/windows/desktop/wer/windows-error-reporting)システムの設定。</span><span class="sxs-lookup"><span data-stu-id="c1a80-121">The option `-errorreport:send` attempts to automatically send error information to Microsoft if reporting is enabled by the [Windows Error Reporting](/windows/desktop/wer/windows-error-reporting) system settings.</span></span> |
|`none`|<span data-ttu-id="c1a80-122">内部コンパイラ エラーが発生する場合、収集またはされませんがマイクロソフトに送信します。</span><span class="sxs-lookup"><span data-stu-id="c1a80-122">If an internal compiler error occurs, it will not be collected or sent to Microsoft.</span></span>|

<span data-ttu-id="c1a80-123">コンパイラは、通常、いくつかのソース コードを含む、エラー発生時にスタックを含むデータを送信します。</span><span class="sxs-lookup"><span data-stu-id="c1a80-123">The compiler sends data that includes the stack at the time of the error, which usually includes some source code.</span></span> <span data-ttu-id="c1a80-124">場合`-errorreport`を併用、 [-bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)オプション、ソース ファイル全体が送信されます。</span><span class="sxs-lookup"><span data-stu-id="c1a80-124">If `-errorreport` is used with the [-bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) option, then the entire source file is sent.</span></span>

<span data-ttu-id="c1a80-125">このオプションで最も多く使用、 [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)オプションの詳細は Microsoft のエンジニアが、エラーを簡単に再現できるためです。</span><span class="sxs-lookup"><span data-stu-id="c1a80-125">This option is best used with the [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) option, because it allows Microsoft engineers to more easily reproduce the error.</span></span>

> [!NOTE]
> <span data-ttu-id="c1a80-126">`-errorreport`オプションは、Visual Studio 開発環境内からは使用できません。 コマンドラインからコンパイルする場合にのみ使用可能なです。</span><span class="sxs-lookup"><span data-stu-id="c1a80-126">The `-errorreport` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>

## <a name="example"></a><span data-ttu-id="c1a80-127">例</span><span class="sxs-lookup"><span data-stu-id="c1a80-127">Example</span></span>

<span data-ttu-id="c1a80-128">次のコードをコンパイルしようとしました。 `T2.vb`、コンパイラには、内部コンパイラ エラーが発生すると、エラー レポートを Microsoft に送信することが確認します。</span><span class="sxs-lookup"><span data-stu-id="c1a80-128">The following code attempts to compile `T2.vb`, and if the compiler encounters an internal compiler error, it prompts you to send the error report to Microsoft.</span></span>

```
vbc -errorreport:prompt t2.vb
```

## <a name="see-also"></a><span data-ttu-id="c1a80-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="c1a80-129">See also</span></span>

- [<span data-ttu-id="c1a80-130">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="c1a80-130">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="c1a80-131">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="c1a80-131">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="c1a80-132">-bugreport</span><span class="sxs-lookup"><span data-stu-id="c1a80-132">-bugreport</span></span>](../../../visual-basic/reference/command-line-compiler/bugreport.md)
