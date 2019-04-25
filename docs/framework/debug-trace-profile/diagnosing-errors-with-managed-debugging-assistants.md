---
title: マネージド デバッグ アシスタントによるエラーの診断
ms.date: 08/14/2018
f1_keywords:
- EHMDA
helpviewer_keywords:
- run-time error debugging
- managed code, run-time debugging
- resource debugging
- registry, MDAs
- common language runtime, debugging
- MDAs (managed debugging assistants)
- configuration files [.NET Framework], debugging runtime events
- messages, managed debugging assistants
- application configuration files, managed debugging assistants
- debugging [.NET Framework], managed debugging assistants
- environment variables, MDAs
- access violation debugging [.NET Framework]
- diagnostics, managed debugging assistants
- unmanaged code, run-time debugging
- default debug output stream
- memory, debugging
- app.config files, managed debugging assistants
- managed debugging assistants (MDAs)
- debugging [.NET Framework], run-time errors
- trapping events
- runtime, error debugging
- disabling MDAs
- output, managed debugging assistants
- errors [.NET Framework], managed debugging assistants
ms.assetid: 76994ee6-9fa9-4059-b813-26578d24427c
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b745fa6a78ab2a7ab0b3a94c9921883d3c56c1b7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61874623"
---
# <a name="diagnose-errors-with-managed-debugging-assistants"></a><span data-ttu-id="3f42c-102">マネージ デバッグ アシスタントによるエラーを診断します。</span><span class="sxs-lookup"><span data-stu-id="3f42c-102">Diagnose Errors with Managed Debugging Assistants</span></span>

<span data-ttu-id="3f42c-103">マネージド デバッグ アシスタント (MDA) は、共通言語ランタイム (CLR: Common Language Runtime) と連携してランタイム状態に関する情報を提供するデバッグ支援ツールです。</span><span class="sxs-lookup"><span data-stu-id="3f42c-103">Managed debugging assistants (MDAs) are debugging aids that work in conjunction with the common language runtime (CLR) to provide information on runtime state.</span></span> <span data-ttu-id="3f42c-104">MDA は、これ以外の方法ではトラップできないランタイム イベントに関する情報メッセージを生成します。</span><span class="sxs-lookup"><span data-stu-id="3f42c-104">The assistants generate informational messages about runtime events that you cannot otherwise trap.</span></span> <span data-ttu-id="3f42c-105">MDA を使用すると、マネージド コードからアンマネージド コードへの遷移時に発生する、検出が難しいアプリケーション バグを分離できます。</span><span class="sxs-lookup"><span data-stu-id="3f42c-105">You can use MDAs to isolate hard-to-find application bugs that occur when transitioning between managed and unmanaged code.</span></span>

<span data-ttu-id="3f42c-106">できます[有効または無効に](#enable-and-disable-mdas)すべての Mda を Windows レジストリにキーを追加するか、環境変数を設定します。</span><span class="sxs-lookup"><span data-stu-id="3f42c-106">You can [enable or disable](#enable-and-disable-mdas) all MDAs by adding a key to the Windows registry or by setting an environment variable.</span></span> <span data-ttu-id="3f42c-107">特定の MDA を有効にするには、アプリケーション構成設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="3f42c-107">You can enable specific MDAs by using application configuration settings.</span></span> <span data-ttu-id="3f42c-108">一部の MDA については、アプリケーションの構成ファイルで追加の構成設定を個別に設定できます。</span><span class="sxs-lookup"><span data-stu-id="3f42c-108">You can set additional configuration settings for some individual MDAs in the application's configuration file.</span></span> <span data-ttu-id="3f42c-109">この構成ファイルはランタイムの読み込み時に解析されるため、MDA は、マネージド アプリケーションが起動する前に有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f42c-109">Because these configuration files are parsed when the runtime is loaded, you must enable the MDA before the managed application starts.</span></span> <span data-ttu-id="3f42c-110">MDA は、既に起動しているアプリケーションに対して有効にできません。</span><span class="sxs-lookup"><span data-stu-id="3f42c-110">You cannot enable it for applications that have already started.</span></span>

<span data-ttu-id="3f42c-111">次の表では、.NET Framework に付属する Mda を示します。</span><span class="sxs-lookup"><span data-stu-id="3f42c-111">The following table lists the MDAs that ship with the .NET Framework:</span></span>

|||
|-|-|
|[<span data-ttu-id="3f42c-112">asynchronousThreadAbort</span><span class="sxs-lookup"><span data-stu-id="3f42c-112">asynchronousThreadAbort</span></span>](../../../docs/framework/debug-trace-profile/asynchronousthreadabort-mda.md)|[<span data-ttu-id="3f42c-113">bindingFailure</span><span class="sxs-lookup"><span data-stu-id="3f42c-113">bindingFailure</span></span>](../../../docs/framework/debug-trace-profile/bindingfailure-mda.md)|
|[<span data-ttu-id="3f42c-114">callbackOnCollectedDelegate</span><span class="sxs-lookup"><span data-stu-id="3f42c-114">callbackOnCollectedDelegate</span></span>](../../../docs/framework/debug-trace-profile/callbackoncollecteddelegate-mda.md)|[<span data-ttu-id="3f42c-115">contextSwitchDeadlock</span><span class="sxs-lookup"><span data-stu-id="3f42c-115">contextSwitchDeadlock</span></span>](../../../docs/framework/debug-trace-profile/contextswitchdeadlock-mda.md)|
|[<span data-ttu-id="3f42c-116">dangerousThreadingAPI</span><span class="sxs-lookup"><span data-stu-id="3f42c-116">dangerousThreadingAPI</span></span>](../../../docs/framework/debug-trace-profile/dangerousthreadingapi-mda.md)|[<span data-ttu-id="3f42c-117">dateTimeInvalidLocalFormat</span><span class="sxs-lookup"><span data-stu-id="3f42c-117">dateTimeInvalidLocalFormat</span></span>](../../../docs/framework/debug-trace-profile/datetimeinvalidlocalformat-mda.md)|
|[<span data-ttu-id="3f42c-118">dirtyCastAndCallOnInterface</span><span class="sxs-lookup"><span data-stu-id="3f42c-118">dirtyCastAndCallOnInterface</span></span>](../../../docs/framework/debug-trace-profile/dirtycastandcalloninterface-mda.md)|[<span data-ttu-id="3f42c-119">disconnectedContext</span><span class="sxs-lookup"><span data-stu-id="3f42c-119">disconnectedContext</span></span>](../../../docs/framework/debug-trace-profile/disconnectedcontext-mda.md)|
|[<span data-ttu-id="3f42c-120">dllMainReturnsFalse</span><span class="sxs-lookup"><span data-stu-id="3f42c-120">dllMainReturnsFalse</span></span>](../../../docs/framework/debug-trace-profile/dllmainreturnsfalse-mda.md)|[<span data-ttu-id="3f42c-121">exceptionSwallowedOnCallFromCom</span><span class="sxs-lookup"><span data-stu-id="3f42c-121">exceptionSwallowedOnCallFromCom</span></span>](../../../docs/framework/debug-trace-profile/exceptionswallowedoncallfromcom-mda.md)|
|[<span data-ttu-id="3f42c-122">failedQI</span><span class="sxs-lookup"><span data-stu-id="3f42c-122">failedQI</span></span>](../../../docs/framework/debug-trace-profile/failedqi-mda.md)|[<span data-ttu-id="3f42c-123">fatalExecutionEngineError</span><span class="sxs-lookup"><span data-stu-id="3f42c-123">fatalExecutionEngineError</span></span>](../../../docs/framework/debug-trace-profile/fatalexecutionengineerror-mda.md)|
|[<span data-ttu-id="3f42c-124">gcManagedToUnmanaged</span><span class="sxs-lookup"><span data-stu-id="3f42c-124">gcManagedToUnmanaged</span></span>](../../../docs/framework/debug-trace-profile/gcmanagedtounmanaged-mda.md)|[<span data-ttu-id="3f42c-125">gcUnmanagedToManaged</span><span class="sxs-lookup"><span data-stu-id="3f42c-125">gcUnmanagedToManaged</span></span>](../../../docs/framework/debug-trace-profile/gcunmanagedtomanaged-mda.md)|
|[<span data-ttu-id="3f42c-126">illegalPrepareConstrainedRegion</span><span class="sxs-lookup"><span data-stu-id="3f42c-126">illegalPrepareConstrainedRegion</span></span>](../../../docs/framework/debug-trace-profile/illegalprepareconstrainedregion-mda.md)|[<span data-ttu-id="3f42c-127">invalidApartmentStateChange</span><span class="sxs-lookup"><span data-stu-id="3f42c-127">invalidApartmentStateChange</span></span>](../../../docs/framework/debug-trace-profile/invalidapartmentstatechange-mda.md)|
|[<span data-ttu-id="3f42c-128">invalidCERCall</span><span class="sxs-lookup"><span data-stu-id="3f42c-128">invalidCERCall</span></span>](../../../docs/framework/debug-trace-profile/invalidcercall-mda.md)|[<span data-ttu-id="3f42c-129">invalidFunctionPointerInDelegate</span><span class="sxs-lookup"><span data-stu-id="3f42c-129">invalidFunctionPointerInDelegate</span></span>](../../../docs/framework/debug-trace-profile/invalidfunctionpointerindelegate-mda.md)|
|[<span data-ttu-id="3f42c-130">invalidGCHandleCookie</span><span class="sxs-lookup"><span data-stu-id="3f42c-130">invalidGCHandleCookie</span></span>](../../../docs/framework/debug-trace-profile/invalidgchandlecookie-mda.md)|[<span data-ttu-id="3f42c-131">invalidIUnknown</span><span class="sxs-lookup"><span data-stu-id="3f42c-131">invalidIUnknown</span></span>](../../../docs/framework/debug-trace-profile/invalidiunknown-mda.md)|
|[<span data-ttu-id="3f42c-132">invalidMemberDeclaration</span><span class="sxs-lookup"><span data-stu-id="3f42c-132">invalidMemberDeclaration</span></span>](../../../docs/framework/debug-trace-profile/invalidmemberdeclaration-mda.md)|[<span data-ttu-id="3f42c-133">invalidOverlappedToPinvoke</span><span class="sxs-lookup"><span data-stu-id="3f42c-133">invalidOverlappedToPinvoke</span></span>](../../../docs/framework/debug-trace-profile/invalidoverlappedtopinvoke-mda.md)|
|[<span data-ttu-id="3f42c-134">invalidVariant</span><span class="sxs-lookup"><span data-stu-id="3f42c-134">invalidVariant</span></span>](../../../docs/framework/debug-trace-profile/invalidvariant-mda.md)|[<span data-ttu-id="3f42c-135">jitCompilationStart</span><span class="sxs-lookup"><span data-stu-id="3f42c-135">jitCompilationStart</span></span>](../../../docs/framework/debug-trace-profile/jitcompilationstart-mda.md)|
|[<span data-ttu-id="3f42c-136">loaderLock</span><span class="sxs-lookup"><span data-stu-id="3f42c-136">loaderLock</span></span>](../../../docs/framework/debug-trace-profile/loaderlock-mda.md)|[<span data-ttu-id="3f42c-137">loadFromContext</span><span class="sxs-lookup"><span data-stu-id="3f42c-137">loadFromContext</span></span>](../../../docs/framework/debug-trace-profile/loadfromcontext-mda.md)|
|[<span data-ttu-id="3f42c-138">marshalCleanupError</span><span class="sxs-lookup"><span data-stu-id="3f42c-138">marshalCleanupError</span></span>](../../../docs/framework/debug-trace-profile/marshalcleanuperror-mda.md)|[<span data-ttu-id="3f42c-139">marshaling</span><span class="sxs-lookup"><span data-stu-id="3f42c-139">marshaling</span></span>](../../../docs/framework/debug-trace-profile/marshaling-mda.md)|
|[<span data-ttu-id="3f42c-140">memberInfoCacheCreation</span><span class="sxs-lookup"><span data-stu-id="3f42c-140">memberInfoCacheCreation</span></span>](../../../docs/framework/debug-trace-profile/memberinfocachecreation-mda.md)|[<span data-ttu-id="3f42c-141">moduloObjectHashcode</span><span class="sxs-lookup"><span data-stu-id="3f42c-141">moduloObjectHashcode</span></span>](../../../docs/framework/debug-trace-profile/moduloobjecthashcode-mda.md)|
|[<span data-ttu-id="3f42c-142">nonComVisibleBaseClass</span><span class="sxs-lookup"><span data-stu-id="3f42c-142">nonComVisibleBaseClass</span></span>](../../../docs/framework/debug-trace-profile/noncomvisiblebaseclass-mda.md)|[<span data-ttu-id="3f42c-143">notMarshalable</span><span class="sxs-lookup"><span data-stu-id="3f42c-143">notMarshalable</span></span>](../../../docs/framework/debug-trace-profile/notmarshalable-mda.md)|
|[<span data-ttu-id="3f42c-144">openGenericCERCall</span><span class="sxs-lookup"><span data-stu-id="3f42c-144">openGenericCERCall</span></span>](../../../docs/framework/debug-trace-profile/opengenericcercall-mda.md)|[<span data-ttu-id="3f42c-145">overlappedFreeError</span><span class="sxs-lookup"><span data-stu-id="3f42c-145">overlappedFreeError</span></span>](../../../docs/framework/debug-trace-profile/overlappedfreeerror-mda.md)|
|[<span data-ttu-id="3f42c-146">pInvokeLog</span><span class="sxs-lookup"><span data-stu-id="3f42c-146">pInvokeLog</span></span>](../../../docs/framework/debug-trace-profile/pinvokelog-mda.md)|[<span data-ttu-id="3f42c-147">pInvokeStackImbalance</span><span class="sxs-lookup"><span data-stu-id="3f42c-147">pInvokeStackImbalance</span></span>](../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md)|
|[<span data-ttu-id="3f42c-148">raceOnRCWCleanup</span><span class="sxs-lookup"><span data-stu-id="3f42c-148">raceOnRCWCleanup</span></span>](../../../docs/framework/debug-trace-profile/raceonrcwcleanup-mda.md)|[<span data-ttu-id="3f42c-149">reentrancy</span><span class="sxs-lookup"><span data-stu-id="3f42c-149">reentrancy</span></span>](../../../docs/framework/debug-trace-profile/reentrancy-mda.md)|
|[<span data-ttu-id="3f42c-150">releaseHandleFailed</span><span class="sxs-lookup"><span data-stu-id="3f42c-150">releaseHandleFailed</span></span>](../../../docs/framework/debug-trace-profile/releasehandlefailed-mda.md)|[<span data-ttu-id="3f42c-151">reportAvOnComRelease</span><span class="sxs-lookup"><span data-stu-id="3f42c-151">reportAvOnComRelease</span></span>](../../../docs/framework/debug-trace-profile/reportavoncomrelease-mda.md)|
|[<span data-ttu-id="3f42c-152">streamWriterBufferedDataLost</span><span class="sxs-lookup"><span data-stu-id="3f42c-152">streamWriterBufferedDataLost</span></span>](../../../docs/framework/debug-trace-profile/streamwriterbuffereddatalost-mda.md)|[<span data-ttu-id="3f42c-153">virtualCERCall</span><span class="sxs-lookup"><span data-stu-id="3f42c-153">virtualCERCall</span></span>](../../../docs/framework/debug-trace-profile/virtualcercall-mda.md)|

<span data-ttu-id="3f42c-154">既定では、.NET Framework はすべてのマネージド デバッガーに対して MDA のサブセットをアクティブにします。</span><span class="sxs-lookup"><span data-stu-id="3f42c-154">By default, the .NET Framework activates a subset of MDAs for all managed debuggers.</span></span> <span data-ttu-id="3f42c-155">選択すると、Visual Studio で設定した既定値を表示する**Windows** > **例外設定**上、**デバッグ**メニューのおよび、を展開し、**マネージ デバッグ アシスタント**一覧。</span><span class="sxs-lookup"><span data-stu-id="3f42c-155">You can view the default set in Visual Studio by choosing **Windows** > **Exception Settings** on the **Debug** menu, and then expanding the **Managed Debugging Assistants** list.</span></span>

![Visual Studio での例外設定ウィンドウ](media/diagnosing-errors-with-managed-debugging-assistants/exception-settings-mdas.png)

## <a name="enable-and-disable-mdas"></a><span data-ttu-id="3f42c-157">無効にする Mda の有効化と</span><span class="sxs-lookup"><span data-stu-id="3f42c-157">Enable and Disable MDAs</span></span>

<span data-ttu-id="3f42c-158">MDA は、レジストリ キー、環境変数、およびアプリケーション構成設定を使用して有効または無効にできます。</span><span class="sxs-lookup"><span data-stu-id="3f42c-158">You can enable and disable MDAs by using a registry key, an environment variable, and application configuration settings.</span></span> <span data-ttu-id="3f42c-159">アプリケーション構成設定を使用するには、レジストリ キーまたは環境変数を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f42c-159">You must enable either the registry key or the environment variable to use the application configuration settings.</span></span>

> [!TIP]
> <span data-ttu-id="3f42c-160">Mda を無効にすると、代わりに Visual Studio を防ぐため、MDA 通知を受け取るたびに MDA ダイアログ ボックスが表示されないことができます。</span><span class="sxs-lookup"><span data-stu-id="3f42c-160">Instead of disabling MDAs, you can prevent Visual Studio from displaying the MDA dialog box whenever an MDA notification is received.</span></span> <span data-ttu-id="3f42c-161">次のように選択します**Windows** > **例外設定**上、**デバッグ**メニューで、展開、**マネージ デバッグ アシスタント**。ボックスの一覧をオンまたはオフ、**スローされたときに中断**個々 の MDA に対してチェック ボックス。</span><span class="sxs-lookup"><span data-stu-id="3f42c-161">To do that, choose **Windows** > **Exception Settings** on the **Debug** menu, expand the **Managed Debugging Assistants** list, and then select or clear the **Break When Thrown** check box for the individual MDA.</span></span>

### <a name="registry-key"></a><span data-ttu-id="3f42c-162">レジストリ キー</span><span class="sxs-lookup"><span data-stu-id="3f42c-162">Registry Key</span></span>

<span data-ttu-id="3f42c-163">Mda を有効にするには追加、 **hkey_local_machine \software\microsoft\\します.Netframework \mda** Windows レジストリのサブキー (REG_SZ 型、値 1)。</span><span class="sxs-lookup"><span data-stu-id="3f42c-163">To enable MDAs, add the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework\MDA** subkey (type REG_SZ, value 1) in the Windows registry.</span></span> <span data-ttu-id="3f42c-164">という名前のテキスト ファイルに次の例をコピー *MDAEnable.reg*します。Windows レジストリ エディター (RegEdit.exe) を開くとの間、**ファイル**メニュー**インポート**します。</span><span class="sxs-lookup"><span data-stu-id="3f42c-164">Copy the following example into a text file named *MDAEnable.reg*. Open the Windows Registry Editor (RegEdit.exe), and from the **File** menu choose **Import**.</span></span> <span data-ttu-id="3f42c-165">選択、 *MDAEnable.reg*ファイルをそのコンピューターで Mda を有効にします。</span><span class="sxs-lookup"><span data-stu-id="3f42c-165">Select the *MDAEnable.reg* file to enable MDAs on that computer.</span></span> <span data-ttu-id="3f42c-166">サブキーの設定の文字列値に**1** (の DWORD 値ではなく**1**) から MDA の設定を読み取ることができるように、 *ApplicationName.suffix*.mda.config ファイル。</span><span class="sxs-lookup"><span data-stu-id="3f42c-166">Setting the subkey to string value of **1** (not DWORD value of **1**) enables the reading of MDA settings from the *ApplicationName.suffix*.mda.config file.</span></span> <span data-ttu-id="3f42c-167">たとえば、メモ帳の MDA 構成ファイルは notepad.exe.mda.config になります。</span><span class="sxs-lookup"><span data-stu-id="3f42c-167">For example, the MDA configuration file for Notepad would be named notepad.exe.mda.config.</span></span>

```text
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework]
"MDA"="1"
```

<span data-ttu-id="3f42c-168">64 ビット オペレーティング システム上で 32 ビット アプリケーションを実行しているコンピューターでは、MDA キーは次のように設定します。</span><span class="sxs-lookup"><span data-stu-id="3f42c-168">If the computer is running a 32-bit application on a 64-bit operating system, then the MDA key should be set like the following:</span></span>

```text
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\.NETFramework]
"MDA"="1"
```

<span data-ttu-id="3f42c-169">参照してください[アプリケーションに固有の構成設定](#application-specific-configuration-settings)詳細についてはします。</span><span class="sxs-lookup"><span data-stu-id="3f42c-169">See [Application-Specific Configuration Settings](#application-specific-configuration-settings) for more information.</span></span> <span data-ttu-id="3f42c-170">レジストリ設定は、COMPLUS_MDA 環境変数でオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="3f42c-170">The registry setting can be overridden by the COMPLUS_MDA environment variable.</span></span> <span data-ttu-id="3f42c-171">参照してください[環境変数](#environment-variable)詳細についてはします。</span><span class="sxs-lookup"><span data-stu-id="3f42c-171">See [Environment Variable](#environment-variable) for more information.</span></span>

<span data-ttu-id="3f42c-172">Mda を無効にする MDA サブキーを設定**0** (0)、Windows レジストリ エディターを使用します。</span><span class="sxs-lookup"><span data-stu-id="3f42c-172">To disable MDAs, set the MDA subkey to **0** (zero) using the Windows Registry Editor.</span></span>

<span data-ttu-id="3f42c-173">MDA には、レジストリ キーを追加しなくても、デバッガーにアタッチされているアプリケーションを実行すると既定で有効になるものがあります。</span><span class="sxs-lookup"><span data-stu-id="3f42c-173">By default, some MDAs are enabled when you run an application that is attached to a debugger, even without adding the registry key.</span></span> <span data-ttu-id="3f42c-174">実行してこれらのアシスタントを無効にすることができます、 *MDADisable.reg*ファイルのこのセクションの説明のとおりです。</span><span class="sxs-lookup"><span data-stu-id="3f42c-174">You can disable these assistants by running the *MDADisable.reg* file as described earlier in this section.</span></span>

### <a name="environment-variable"></a><span data-ttu-id="3f42c-175">環境変数</span><span class="sxs-lookup"><span data-stu-id="3f42c-175">Environment Variable</span></span>

<span data-ttu-id="3f42c-176">MDA のアクティブ化は、COMPLUS_MDA 環境変数によって制御することもできます。この環境変数はレジストリ キーをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="3f42c-176">MDA activation can also controlled by the environment variable COMPLUS_MDA, which overrides the registry key.</span></span> <span data-ttu-id="3f42c-177">COMPLUS_MDA の文字列は、MDA 名やその他の特殊制御文字列の、セミコロンで区切られたリストで、大文字小文字の区別はありません。</span><span class="sxs-lookup"><span data-stu-id="3f42c-177">The COMPLUS_MDA string is a case-insensitive, semicolon-delimited list of MDA names or other special control strings.</span></span> <span data-ttu-id="3f42c-178">マネージド デバッガーやアンマネージド デバッガーの下で起動すると、MDA のセットが既定で有効になります。</span><span class="sxs-lookup"><span data-stu-id="3f42c-178">Starting under a managed or unmanaged debugger enables a set of MDAs by default.</span></span> <span data-ttu-id="3f42c-179">そのためには、デバッガーの下で既定で有効にする MDA のリスト (セミコロン区切り) を、環境変数またはレジストリ キーの値の前に暗黙的に付加します。</span><span class="sxs-lookup"><span data-stu-id="3f42c-179">This is done by implicitly prepending the semicolon-delimited list of MDAs enabled by default under debuggers to the value of the environment variable or registry key.</span></span> <span data-ttu-id="3f42c-180">特殊制御文字列は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="3f42c-180">The special control strings are the following:</span></span>

- <span data-ttu-id="3f42c-181">`0` - すべての MDA を非アクティブにします。</span><span class="sxs-lookup"><span data-stu-id="3f42c-181">`0` - Deactivates all MDAs.</span></span>

- <span data-ttu-id="3f42c-182">`1` - *ApplicationName*.mda.config から MDA の設定を読み取ります。</span><span class="sxs-lookup"><span data-stu-id="3f42c-182">`1` - Reads MDA settings from *ApplicationName*.mda.config.</span></span>

- <span data-ttu-id="3f42c-183">`managedDebugger` - デバッガーの下でマネージド実行可能ファイルを起動すると、暗黙的にアクティブ化されているすべての MDA が明示的にアクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="3f42c-183">`managedDebugger` - Explicitly activates all MDAs that are implicitly activated when a managed executable is started under a debugger.</span></span>

- <span data-ttu-id="3f42c-184">`unmanagedDebugger` - デバッガーの下でアンマネージ実行可能ファイルを起動すると、暗黙的にアクティブ化されているすべての MDA が明示的にアクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="3f42c-184">`unmanagedDebugger` - Explicitly activates all MDAs that are implicitly activated when an unmanaged executable is started under a debugger.</span></span>

<span data-ttu-id="3f42c-185">競合する設定がある場合は、最新の設定が以前の設定を次のようにオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="3f42c-185">If there are conflicting settings, the most recent settings override previous settings:</span></span>

- <span data-ttu-id="3f42c-186">`COMPLUS_MDA=0` は、デバッガーの下で暗黙的に有効化されている MDA を含め、すべての MDA を無効にします。</span><span class="sxs-lookup"><span data-stu-id="3f42c-186">`COMPLUS_MDA=0` disables all MDAs, including those implicitly enabled under a debugger.</span></span>

- <span data-ttu-id="3f42c-187">`COMPLUS_MDA=gcUnmanagedToManaged` は、デバッガーの下で暗黙的に有効化される MDA に加えて `gcUnmanagedToManaged` も有効にします。</span><span class="sxs-lookup"><span data-stu-id="3f42c-187">`COMPLUS_MDA=gcUnmanagedToManaged` enables `gcUnmanagedToManaged` in addition to any MDAs that are implicitly enabled under a debugger.</span></span>

- <span data-ttu-id="3f42c-188">`COMPLUS_MDA=0;gcUnmanagedToManaged` は `gcUnmanagedToManaged` を有効にしますが、デバッガーの下で別途暗黙的に有効化されている MDA を無効にします。</span><span class="sxs-lookup"><span data-stu-id="3f42c-188">`COMPLUS_MDA=0;gcUnmanagedToManaged` enables `gcUnmanagedToManaged` but disables MDAs that would otherwise be implicitly enabled under a debugger.</span></span>

### <a name="application-specific-configuration-settings"></a><span data-ttu-id="3f42c-189">アプリケーション固有の構成設定</span><span class="sxs-lookup"><span data-stu-id="3f42c-189">Application-Specific Configuration Settings</span></span>

<span data-ttu-id="3f42c-190">アプリケーションの MDA 構成ファイルでは、一部のアシスタントを個別に有効化、無効化、および構成できます。</span><span class="sxs-lookup"><span data-stu-id="3f42c-190">You can enable, disable, and configure some assistants individually in the MDA configuration file for the application.</span></span> <span data-ttu-id="3f42c-191">MDA を構成する目的でアプリケーション構成ファイルの使用を有効にするには、MDA レジストリ キーまたは COMPLUS_MDA 環境変数を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f42c-191">To enable the use of an application configuration file for configuring MDAs, either the MDA registry key or the COMPLUS_MDA environment variable must be set.</span></span> <span data-ttu-id="3f42c-192">アプリケーション構成ファイルは、通常、アプリケーションの実行可能ファイル (.exe) と同じディレクトリに置かれます。</span><span class="sxs-lookup"><span data-stu-id="3f42c-192">The application configuration file is typically located in the same directory as the application's executable (.exe) file.</span></span> <span data-ttu-id="3f42c-193">このファイル名の形式は、*ApplicationName*.mda.config です (notepad.exe.mda.config など)。アプリケーション構成ファイルで有効にされたアシスタントには、そのアシスタントの動作を制御するために特別にデザインされた属性や要素が存在する場合があります。</span><span class="sxs-lookup"><span data-stu-id="3f42c-193">The file name takes the form *ApplicationName*.mda.config; for example, notepad.exe.mda.config. Assistants that are enabled in the application configuration file may have attributes or elements specifically designed to control that assistant's behavior.</span></span>

<span data-ttu-id="3f42c-194">次の例では、有効にして構成する方法を示しています、[マーシャ リング](../../../docs/framework/debug-trace-profile/marshaling-mda.md):</span><span class="sxs-lookup"><span data-stu-id="3f42c-194">The following example shows how to enable and configure the [marshaling](../../../docs/framework/debug-trace-profile/marshaling-mda.md):</span></span>

```xml
<mdaConfig>
  <assistants>
    <marshaling>
      <methodFilter>
        <match name="*"/>
      </methodFilter>
      <fieldFilter>
        <match name="*"/>
      </fieldFilter>
    </marshaling>
  </assistants>
</mdaConfig>
```

<span data-ttu-id="3f42c-195">`Marshaling` MDA では、アプリケーションでのマネージド コードからアンマネージド コードへの遷移ごとに、アンマネージド型にマーシャリングされるマネージド型についての情報が出力されます。</span><span class="sxs-lookup"><span data-stu-id="3f42c-195">The `Marshaling` MDA emits information about the managed type that is being marshaled to an unmanaged type for each managed-to-unmanaged transition in the application.</span></span> <span data-ttu-id="3f42c-196">`Marshaling` MDA は、メソッドの名前もをフィルター処理、および構造体のフィールドで、 **methodFilter**と**fieldFilter**子要素では、それぞれします。</span><span class="sxs-lookup"><span data-stu-id="3f42c-196">The `Marshaling` MDA can also filter the names of the method and structure fields supplied in the **methodFilter** and **fieldFilter** child elements, respectively.</span></span>

<span data-ttu-id="3f42c-197">次の例では、既定の設定を使用して複数の Mda を有効にする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="3f42c-197">The following example shows how to enable multiple MDAs by using their default settings:</span></span>

```xml
<mdaConfig>
  <assistants>
    <illegalPrepareConstrainedRegion />
    <invalidCERCall />
    <openGenericCERCall />
    <virtualCERCall />
  </assistants>
</mdaConfig>
```

> [!IMPORTANT]
> <span data-ttu-id="3f42c-198">構成ファイルに複数のアシスタントを指定する場合は、アルファベット順に記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f42c-198">When you specify more than one assistant in a configuration file, you must list them in alphabetical order.</span></span> <span data-ttu-id="3f42c-199">たとえば、`virtualCERCall` MDA と `invalidCERCall` MDA の両方を有効にする場合は、`<invalidCERCall />` エントリ、`<virtualCERCall />` エントリの順に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f42c-199">For example, if you want to enable both the `virtualCERCall` and the `invalidCERCall` MDAs, you must add the `<invalidCERCall />` entry before the `<virtualCERCall />` entry.</span></span> <span data-ttu-id="3f42c-200">エントリがアルファベット順になっていない場合、ハンドルされない無効な構成ファイルであることを示す例外メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3f42c-200">If the entries are not in alphabetical order, an unhandled invalid configuration file exception message is displayed.</span></span>

## <a name="mda-exceptions"></a><span data-ttu-id="3f42c-201">MDA 例外</span><span class="sxs-lookup"><span data-stu-id="3f42c-201">MDA exceptions</span></span>

<span data-ttu-id="3f42c-202">MDA を有効にするがアクティブなもときに、コードが実行されていないのデバッガーの下でします。</span><span class="sxs-lookup"><span data-stu-id="3f42c-202">When an MDA is enabled, it's active even when your code is not executing under a debugger.</span></span> <span data-ttu-id="3f42c-203">デバッガーが存在しない場合に MDA イベントが発生した場合、そのイベントはハンドルされない例外とは異なりますが、イベント メッセージはハンドルされない例外のダイアログ ボックスに表示されます。</span><span class="sxs-lookup"><span data-stu-id="3f42c-203">If an MDA event is raised when a debugger is not present, the event message is presented in an unhandled exception dialog box, although it is not an unhandled exception.</span></span> <span data-ttu-id="3f42c-204">このダイアログ ボックスが表示されないようにするには、デバッグ環境でコードを実行しているのではないときに、MDA を有効にする設定を削除します。</span><span class="sxs-lookup"><span data-stu-id="3f42c-204">To avoid the dialog box, remove the MDA-enabling settings when your code is not executing in a debugging environment.</span></span>

<span data-ttu-id="3f42c-205">Visual Studio 統合開発環境 (IDE) で、コードを実行するときは、特定の MDA イベントについて表示される [例外] ダイアログ ボックスを回避できます。</span><span class="sxs-lookup"><span data-stu-id="3f42c-205">When your code executes in the Visual Studio integrated development environment (IDE), you can avoid the exception dialog box that appears for specific MDA events.</span></span> <span data-ttu-id="3f42c-206">そのため、**デバッグ**] メニューの [選択**Windows** > **例外設定**します。</span><span class="sxs-lookup"><span data-stu-id="3f42c-206">To do that, on the **Debug** menu, choose **Windows** > **Exception Settings**.</span></span> <span data-ttu-id="3f42c-207">**例外設定**ウィンドウで、展開、**マネージ デバッグ アシスタント**、一覧表示し、オフ、**中断するとスローされます**個々 の MDA に対してチェック ボックス。</span><span class="sxs-lookup"><span data-stu-id="3f42c-207">In the **Exception Settings** window, expand the **Managed Debugging Assistants** list, and then clear the **Break When Thrown** check box for the individual MDA.</span></span> <span data-ttu-id="3f42c-208">このダイアログ ボックスを使用することもできます。*を有効にする*MDA 例外ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3f42c-208">You can also use this dialog box to *enable* the display of MDA exception dialog boxes.</span></span>

## <a name="mda-output"></a><span data-ttu-id="3f42c-209">MDA の出力</span><span class="sxs-lookup"><span data-stu-id="3f42c-209">MDA Output</span></span>

<span data-ttu-id="3f42c-210">MDA の出力は次の例は、出力を示しますに似ています、 `PInvokeStackImbalance` MDA:</span><span class="sxs-lookup"><span data-stu-id="3f42c-210">MDA output is similar to the following example, which shows the output from the `PInvokeStackImbalance` MDA:</span></span>

<span data-ttu-id="3f42c-211">**PInvoke 関数の呼び出し ' MDATest!MDATest.Program::StdCall' が、スタックのバランスが取れていません。これは、マネージ PInvoke シグネチャが非管理対象のターゲットのシグネチャと一致しないために、可能性があります。呼び出し規約と PInvoke シグネチャのパラメーターが、ターゲットのアンマネージ シグネチャを一致するかを確認します。**</span><span class="sxs-lookup"><span data-stu-id="3f42c-211">**A call to PInvoke function 'MDATest!MDATest.Program::StdCall' has unbalanced the stack. This is likely because the managed PInvoke signature does not match the unmanaged target signature. Check that the calling convention and parameters of the PInvoke signature match the target unmanaged signature.**</span></span>

## <a name="see-also"></a><span data-ttu-id="3f42c-212">関連項目</span><span class="sxs-lookup"><span data-stu-id="3f42c-212">See also</span></span>

- [<span data-ttu-id="3f42c-213">デバッグ、トレース、およびプロファイリング</span><span class="sxs-lookup"><span data-stu-id="3f42c-213">Debugging, Tracing, and Profiling</span></span>](../../../docs/framework/debug-trace-profile/index.md)
