---
title: -errorreport
ms.date: 08/14/2018
helpviewer_keywords:
- -errorreport compiler option [Visual Basic]
- /errorreport compiler option [Visual Basic]
- errorreport compiler option [Visual Basic]
ms.assetid: a7fe83a2-a6d8-460c-8dad-79a8f433f501
ms.openlocfilehash: a9741f7a8283f8603e02dae5abea151c6ee5d75e
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775666"
---
# <a name="-errorreport"></a><span data-ttu-id="3772f-102">-errorreport</span><span class="sxs-lookup"><span data-stu-id="3772f-102">-errorreport</span></span>

<span data-ttu-id="3772f-103">Visual Basic コンパイラが内部コンパイラエラーを報告する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="3772f-103">Specifies how the Visual Basic compiler should report internal compiler errors.</span></span>

## <a name="syntax"></a><span data-ttu-id="3772f-104">構文</span><span class="sxs-lookup"><span data-stu-id="3772f-104">Syntax</span></span>

```console
-errorreport:{ prompt | queue | send | none }
```

## <a name="remarks"></a><span data-ttu-id="3772f-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="3772f-105">Remarks</span></span>

<span data-ttu-id="3772f-106">このオプションは、Microsoft の Visual Basic チームに Visual Basic 内部コンパイラエラー (ICE) を報告する便利な方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="3772f-106">This option provides a convenient way to report a Visual Basic internal compiler error (ICE) to the Visual Basic team at Microsoft.</span></span> <span data-ttu-id="3772f-107">既定では、コンパイラは Microsoft に情報を送信しません。</span><span class="sxs-lookup"><span data-stu-id="3772f-107">By default, the compiler sends no information to Microsoft.</span></span> <span data-ttu-id="3772f-108">ただし、内部コンパイラエラーが発生した場合は、このオプションを使用すると、エラーを Microsoft に報告できます。</span><span class="sxs-lookup"><span data-stu-id="3772f-108">However, if you do encounter an internal compiler error, this option allows you to report the error to Microsoft.</span></span> <span data-ttu-id="3772f-109">この情報は、Microsoft のエンジニアが原因を特定するのに役立ちます。また、Visual Basic の次のリリースの向上に役立つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="3772f-109">That information will help Microsoft engineers identify the cause and may help improve the next release of Visual Basic.</span></span>

<span data-ttu-id="3772f-110">ユーザーがレポートを送信できるかどうかは、コンピューターとユーザーのポリシーのアクセス許可によって異なります。</span><span class="sxs-lookup"><span data-stu-id="3772f-110">A user's ability to send reports depends on machine and user policy permissions.</span></span>

<span data-ttu-id="3772f-111">次の表は、`-errorreport` オプションの効果をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="3772f-111">The following table summarizes the effect of the `-errorreport` option.</span></span>

|<span data-ttu-id="3772f-112">オプション</span><span class="sxs-lookup"><span data-stu-id="3772f-112">Option</span></span>|<span data-ttu-id="3772f-113">動作</span><span class="sxs-lookup"><span data-stu-id="3772f-113">Behavior</span></span>|
|---|---|
|`prompt`|<span data-ttu-id="3772f-114">内部コンパイラエラーが発生した場合は、コンパイラによって収集された正確なデータを表示するためのダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3772f-114">If an internal compiler error occurs, a dialog box comes up so that you can view the exact data that the compiler collected.</span></span> <span data-ttu-id="3772f-115">エラー報告に機密情報があるかどうかを確認し、Microsoft に送信するかどうかを決定することができます。</span><span class="sxs-lookup"><span data-stu-id="3772f-115">You can determine if there is any sensitive information in the error report and make a decision on whether to send it to Microsoft.</span></span> <span data-ttu-id="3772f-116">送信する場合、コンピューターとユーザーのポリシー設定によって許可されている場合、コンパイラはデータを Microsoft に送信します。</span><span class="sxs-lookup"><span data-stu-id="3772f-116">If you decide to send it, and the machine and user policy settings allow it, the compiler sends the data to Microsoft.</span></span>|
|`queue`|<span data-ttu-id="3772f-117">エラー レポートを待ち行列に入れます。</span><span class="sxs-lookup"><span data-stu-id="3772f-117">Queues the error report.</span></span> <span data-ttu-id="3772f-118">管理者特権でログインすると、最後にログインした後に発生したすべてのエラーを報告することができます (エラーの報告を3日ごとに複数回送信するように求めるメッセージは表示されません)。</span><span class="sxs-lookup"><span data-stu-id="3772f-118">When you log in with administrator privileges, you can report any failures since the last time you were logged in (you will not be prompted to send reports for failures more than once every three days).</span></span> <span data-ttu-id="3772f-119">これは、`-errorreport` オプションが指定されていない場合の既定の動作です。</span><span class="sxs-lookup"><span data-stu-id="3772f-119">This is the default behavior when the `-errorreport` option is not specified.</span></span>|
|`send`|<span data-ttu-id="3772f-120">内部コンパイラエラーが発生し、コンピューターとユーザーのポリシー設定で許可されている場合、コンパイラはデータを Microsoft に送信します。</span><span class="sxs-lookup"><span data-stu-id="3772f-120">If an internal compiler error occurs, and the machine and user policy settings allow it, the compiler sends the data to Microsoft.</span></span><br /><br /> <span data-ttu-id="3772f-121">オプション `-errorreport:send`、 [Windows エラー報告](/windows/desktop/wer/windows-error-reporting)システム設定によってレポートが有効になっている場合に、自動的にエラー情報を Microsoft に送信しようとします。</span><span class="sxs-lookup"><span data-stu-id="3772f-121">The option `-errorreport:send` attempts to automatically send error information to Microsoft if reporting is enabled by the [Windows Error Reporting](/windows/desktop/wer/windows-error-reporting) system settings.</span></span> |
|`none`|<span data-ttu-id="3772f-122">内部コンパイラエラーが発生した場合、そのエラーは収集されず、マイクロソフトに送信されません。</span><span class="sxs-lookup"><span data-stu-id="3772f-122">If an internal compiler error occurs, it will not be collected or sent to Microsoft.</span></span>|

<span data-ttu-id="3772f-123">コンパイラは、エラー発生時にスタックを含むデータを送信します。通常は、ソースコードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3772f-123">The compiler sends data that includes the stack at the time of the error, which usually includes some source code.</span></span> <span data-ttu-id="3772f-124">[-Bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)オプションと共に `-errorreport` を使用すると、ソースファイル全体が送信されます。</span><span class="sxs-lookup"><span data-stu-id="3772f-124">If `-errorreport` is used with the [-bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) option, then the entire source file is sent.</span></span>

<span data-ttu-id="3772f-125">このオプションは、Microsoft のエンジニアがより簡単にエラーを再現できるようにするため、 [-bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)オプションと共に使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3772f-125">This option is best used with the [-bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) option, because it allows Microsoft engineers to more easily reproduce the error.</span></span>

> [!NOTE]
> <span data-ttu-id="3772f-126">@No__t_0 オプションは、Visual Studio 開発環境内からは使用できません。これは、コマンドラインからコンパイルする場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="3772f-126">The `-errorreport` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>

## <a name="example"></a><span data-ttu-id="3772f-127">例</span><span class="sxs-lookup"><span data-stu-id="3772f-127">Example</span></span>

<span data-ttu-id="3772f-128">次のコードは、`T2.vb` のコンパイルを試みます。コンパイラが内部コンパイラエラーを検出した場合は、Microsoft にエラーレポートを送信するように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3772f-128">The following code attempts to compile `T2.vb`, and if the compiler encounters an internal compiler error, it prompts you to send the error report to Microsoft.</span></span>

```console
vbc -errorreport:prompt t2.vb
```

## <a name="see-also"></a><span data-ttu-id="3772f-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="3772f-129">See also</span></span>

- [<span data-ttu-id="3772f-130">Visual Basic コマンドラインコンパイラ</span><span class="sxs-lookup"><span data-stu-id="3772f-130">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="3772f-131">コンパイルコマンドラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="3772f-131">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="3772f-132">-bugreport</span><span class="sxs-lookup"><span data-stu-id="3772f-132">-bugreport</span></span>](../../../visual-basic/reference/command-line-compiler/bugreport.md)
