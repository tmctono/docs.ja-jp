---
title: -errorreport
ms.date: 08/14/2018
helpviewer_keywords:
- -errorreport compiler option [Visual Basic]
- /errorreport compiler option [Visual Basic]
- errorreport compiler option [Visual Basic]
ms.assetid: a7fe83a2-a6d8-460c-8dad-79a8f433f501
ms.openlocfilehash: b6a1c8fce17e3e5a54366c2ff4dff4e6aa668f56
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408661"
---
# <a name="-errorreport"></a><span data-ttu-id="a7767-102">-errorreport</span><span class="sxs-lookup"><span data-stu-id="a7767-102">-errorreport</span></span>

<span data-ttu-id="a7767-103">Visual Basic コンパイラで内部コンパイラ エラーを報告する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="a7767-103">Specifies how the Visual Basic compiler should report internal compiler errors.</span></span>

## <a name="syntax"></a><span data-ttu-id="a7767-104">構文</span><span class="sxs-lookup"><span data-stu-id="a7767-104">Syntax</span></span>

```console
-errorreport:{ prompt | queue | send | none }
```

## <a name="remarks"></a><span data-ttu-id="a7767-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="a7767-105">Remarks</span></span>

<span data-ttu-id="a7767-106">このオプションでは、Microsoft の Visual Basic チームに Visual Basic 内部コンパイラ エラー (ICE) を報告する便利な方法が提供されます。</span><span class="sxs-lookup"><span data-stu-id="a7767-106">This option provides a convenient way to report a Visual Basic internal compiler error (ICE) to the Visual Basic team at Microsoft.</span></span> <span data-ttu-id="a7767-107">既定では、コンパイラによって Microsoft に情報が送信されることはありません。</span><span class="sxs-lookup"><span data-stu-id="a7767-107">By default, the compiler sends no information to Microsoft.</span></span> <span data-ttu-id="a7767-108">ただし、このオプションを使用すると、内部コンパイラ エラーが発生した場合に、エラーを Microsoft に報告することができます。</span><span class="sxs-lookup"><span data-stu-id="a7767-108">However, if you do encounter an internal compiler error, this option allows you to report the error to Microsoft.</span></span> <span data-ttu-id="a7767-109">その情報は、Microsoft のエンジニアが原因を特定するのに役立ちます。また、Visual Basic の次のリリースの向上に役立つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="a7767-109">That information will help Microsoft engineers identify the cause and may help improve the next release of Visual Basic.</span></span>

<span data-ttu-id="a7767-110">マシンまたはユーザー ポリシーによるアクセス許可によっては、レポートを送信できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="a7767-110">A user's ability to send reports depends on machine and user policy permissions.</span></span>

<span data-ttu-id="a7767-111">次の表に、`-errorreport` オプションの結果をまとめています。</span><span class="sxs-lookup"><span data-stu-id="a7767-111">The following table summarizes the effect of the `-errorreport` option.</span></span>

|<span data-ttu-id="a7767-112">オプション</span><span class="sxs-lookup"><span data-stu-id="a7767-112">Option</span></span>|<span data-ttu-id="a7767-113">動作</span><span class="sxs-lookup"><span data-stu-id="a7767-113">Behavior</span></span>|
|---|---|
|`prompt`|<span data-ttu-id="a7767-114">内部コンパイラ エラーが発生すると、コンパイラによって収集された正確なデータを表示するためのダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a7767-114">If an internal compiler error occurs, a dialog box comes up so that you can view the exact data that the compiler collected.</span></span> <span data-ttu-id="a7767-115">エラー レポートに機密情報が含まれているかどうかを確認し、Microsoft に送信するかどうかを決定することができます。</span><span class="sxs-lookup"><span data-stu-id="a7767-115">You can determine if there is any sensitive information in the error report and make a decision on whether to send it to Microsoft.</span></span> <span data-ttu-id="a7767-116">送信する場合、マシンとユーザーのポリシー設定でそれが許可されていれば、コンパイラによってデータが Microsoft に送信されます。</span><span class="sxs-lookup"><span data-stu-id="a7767-116">If you decide to send it, and the machine and user policy settings allow it, the compiler sends the data to Microsoft.</span></span>|
|`queue`|<span data-ttu-id="a7767-117">エラー レポートを待ち行列に入れます。</span><span class="sxs-lookup"><span data-stu-id="a7767-117">Queues the error report.</span></span> <span data-ttu-id="a7767-118">管理者特権でログインすると、最後にログインした後に発生したすべてのエラーを報告することができます (エラーの報告を 3 日ごとに複数回送信するように求めるメッセージは表示されません)。</span><span class="sxs-lookup"><span data-stu-id="a7767-118">When you log in with administrator privileges, you can report any failures since the last time you were logged in (you will not be prompted to send reports for failures more than once every three days).</span></span> <span data-ttu-id="a7767-119">`-errorreport` オプションが指定されていない場合は、これが既定の動作です。</span><span class="sxs-lookup"><span data-stu-id="a7767-119">This is the default behavior when the `-errorreport` option is not specified.</span></span>|
|`send`|<span data-ttu-id="a7767-120">内部コンパイラ エラーが発生した場合、マシンとユーザーのポリシー設定で許可されていれば、コンパイラによってデータが Microsoft に送信されます。</span><span class="sxs-lookup"><span data-stu-id="a7767-120">If an internal compiler error occurs, and the machine and user policy settings allow it, the compiler sends the data to Microsoft.</span></span><br /><br /> <span data-ttu-id="a7767-121">オプション `-errorreport:send` では、[Windows エラー報告](/windows/desktop/wer/windows-error-reporting)システム設定でレポートが有効になっている場合、Microsoft にエラー情報を自動的に送信するよう試みられます。</span><span class="sxs-lookup"><span data-stu-id="a7767-121">The option `-errorreport:send` attempts to automatically send error information to Microsoft if reporting is enabled by the [Windows Error Reporting](/windows/desktop/wer/windows-error-reporting) system settings.</span></span> |
|`none`|<span data-ttu-id="a7767-122">内部コンパイラ エラーが発生すると、そのエラーは収集されず、Microsoft に送信されません。</span><span class="sxs-lookup"><span data-stu-id="a7767-122">If an internal compiler error occurs, it will not be collected or sent to Microsoft.</span></span>|

<span data-ttu-id="a7767-123">コンパイラによって、エラー発生時にスタックを含むデータが送信されます。これには通常、いくつかのソース コードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a7767-123">The compiler sends data that includes the stack at the time of the error, which usually includes some source code.</span></span> <span data-ttu-id="a7767-124">`-errorreport` を [-bugreport](bugreport.md) オプションと共に使用すると、ソース ファイル全体が送信されます。</span><span class="sxs-lookup"><span data-stu-id="a7767-124">If `-errorreport` is used with the [-bugreport](bugreport.md) option, then the entire source file is sent.</span></span>

<span data-ttu-id="a7767-125">Microsoft のエンジニアがエラーをより簡単に再現できるようになるため、このオプションを [-bugreport](bugreport.md) オプションと共に使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a7767-125">This option is best used with the [-bugreport](bugreport.md) option, because it allows Microsoft engineers to more easily reproduce the error.</span></span>

> [!NOTE]
> <span data-ttu-id="a7767-126">`-errorreport` オプションは、Visual Studio 開発環境からは利用できません。これはコマンド ラインからコンパイルするときにのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="a7767-126">The `-errorreport` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>

## <a name="example"></a><span data-ttu-id="a7767-127">例</span><span class="sxs-lookup"><span data-stu-id="a7767-127">Example</span></span>

<span data-ttu-id="a7767-128">次のコードでは、`T2.vb` のコンパイルが試行されます。コンパイラで内部コンパイラ エラーが発生した場合は、Microsoft にエラー レポートを送信するように求められます。</span><span class="sxs-lookup"><span data-stu-id="a7767-128">The following code attempts to compile `T2.vb`, and if the compiler encounters an internal compiler error, it prompts you to send the error report to Microsoft.</span></span>

```console
vbc -errorreport:prompt t2.vb
```

## <a name="see-also"></a><span data-ttu-id="a7767-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="a7767-129">See also</span></span>

- [<span data-ttu-id="a7767-130">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="a7767-130">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="a7767-131">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="a7767-131">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- [<span data-ttu-id="a7767-132">-bugreport</span><span class="sxs-lookup"><span data-stu-id="a7767-132">-bugreport</span></span>](bugreport.md)
