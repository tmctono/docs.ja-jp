---
title: マネージド デバッグ アシスタントによるエラーの診断
description: マネージデバッグアシスタントを使用して .NET のエラーを診断します。 Mda は、ランタイム状態情報を提供するために CLR と連携して動作するデバッグ支援です。
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
ms.openlocfilehash: ac6fdc09fb057cc55659ce076d37ab96fe2354d1
ms.sourcegitcommit: a2c8b19e813a52b91facbb5d7e3c062c7188b457
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "85416097"
---
# <a name="diagnose-errors-with-managed-debugging-assistants"></a><span data-ttu-id="347a4-104">マネージデバッグアシスタントを使用してエラーを診断する</span><span class="sxs-lookup"><span data-stu-id="347a4-104">Diagnose Errors with Managed Debugging Assistants</span></span>

<span data-ttu-id="347a4-105">マネージド デバッグ アシスタント (MDA) は、共通言語ランタイム (CLR: Common Language Runtime) と連携してランタイム状態に関する情報を提供するデバッグ支援ツールです。</span><span class="sxs-lookup"><span data-stu-id="347a4-105">Managed debugging assistants (MDAs) are debugging aids that work in conjunction with the common language runtime (CLR) to provide information on runtime state.</span></span> <span data-ttu-id="347a4-106">MDA は、これ以外の方法ではトラップできないランタイム イベントに関する情報メッセージを生成します。</span><span class="sxs-lookup"><span data-stu-id="347a4-106">The assistants generate informational messages about runtime events that you cannot otherwise trap.</span></span> <span data-ttu-id="347a4-107">MDA を使用すると、マネージド コードからアンマネージド コードへの遷移時に発生する、検出が難しいアプリケーション バグを分離できます。</span><span class="sxs-lookup"><span data-stu-id="347a4-107">You can use MDAs to isolate hard-to-find application bugs that occur when transitioning between managed and unmanaged code.</span></span>

<span data-ttu-id="347a4-108">すべての Mda を[有効または無効](#enable-and-disable-mdas)にするには、Windows レジストリにキーを追加するか、環境変数を設定します。</span><span class="sxs-lookup"><span data-stu-id="347a4-108">You can [enable or disable](#enable-and-disable-mdas) all MDAs by adding a key to the Windows registry or by setting an environment variable.</span></span> <span data-ttu-id="347a4-109">特定の MDA を有効にするには、アプリケーション構成設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="347a4-109">You can enable specific MDAs by using application configuration settings.</span></span> <span data-ttu-id="347a4-110">一部の MDA については、アプリケーションの構成ファイルで追加の構成設定を個別に設定できます。</span><span class="sxs-lookup"><span data-stu-id="347a4-110">You can set additional configuration settings for some individual MDAs in the application's configuration file.</span></span> <span data-ttu-id="347a4-111">この構成ファイルはランタイムの読み込み時に解析されるため、MDA は、マネージド アプリケーションが起動する前に有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="347a4-111">Because these configuration files are parsed when the runtime is loaded, you must enable the MDA before the managed application starts.</span></span> <span data-ttu-id="347a4-112">MDA は、既に起動しているアプリケーションに対して有効にできません。</span><span class="sxs-lookup"><span data-stu-id="347a4-112">You cannot enable it for applications that have already started.</span></span>

<span data-ttu-id="347a4-113">次の表に、.NET Framework に付属している Mda を示します。</span><span class="sxs-lookup"><span data-stu-id="347a4-113">The following table lists the MDAs that ship with the .NET Framework:</span></span>

|||
|-|-|
|[<span data-ttu-id="347a4-114">asynchronousThreadAbort</span><span class="sxs-lookup"><span data-stu-id="347a4-114">asynchronousThreadAbort</span></span>](asynchronousthreadabort-mda.md)|[<span data-ttu-id="347a4-115">bindingFailure</span><span class="sxs-lookup"><span data-stu-id="347a4-115">bindingFailure</span></span>](bindingfailure-mda.md)|
|[<span data-ttu-id="347a4-116">callbackOnCollectedDelegate</span><span class="sxs-lookup"><span data-stu-id="347a4-116">callbackOnCollectedDelegate</span></span>](callbackoncollecteddelegate-mda.md)|[<span data-ttu-id="347a4-117">contextSwitchDeadlock</span><span class="sxs-lookup"><span data-stu-id="347a4-117">contextSwitchDeadlock</span></span>](contextswitchdeadlock-mda.md)|
|[<span data-ttu-id="347a4-118">dangerousThreadingAPI</span><span class="sxs-lookup"><span data-stu-id="347a4-118">dangerousThreadingAPI</span></span>](dangerousthreadingapi-mda.md)|[<span data-ttu-id="347a4-119">dateTimeInvalidLocalFormat</span><span class="sxs-lookup"><span data-stu-id="347a4-119">dateTimeInvalidLocalFormat</span></span>](datetimeinvalidlocalformat-mda.md)|
|[<span data-ttu-id="347a4-120">dirtyCastAndCallOnInterface</span><span class="sxs-lookup"><span data-stu-id="347a4-120">dirtyCastAndCallOnInterface</span></span>](dirtycastandcalloninterface-mda.md)|[<span data-ttu-id="347a4-121">disconnectedContext</span><span class="sxs-lookup"><span data-stu-id="347a4-121">disconnectedContext</span></span>](disconnectedcontext-mda.md)|
|[<span data-ttu-id="347a4-122">dllMainReturnsFalse</span><span class="sxs-lookup"><span data-stu-id="347a4-122">dllMainReturnsFalse</span></span>](dllmainreturnsfalse-mda.md)|[<span data-ttu-id="347a4-123">exceptionSwallowedOnCallFromCom</span><span class="sxs-lookup"><span data-stu-id="347a4-123">exceptionSwallowedOnCallFromCom</span></span>](exceptionswallowedoncallfromcom-mda.md)|
|[<span data-ttu-id="347a4-124">failedQI</span><span class="sxs-lookup"><span data-stu-id="347a4-124">failedQI</span></span>](failedqi-mda.md)|[<span data-ttu-id="347a4-125">fatalExecutionEngineError</span><span class="sxs-lookup"><span data-stu-id="347a4-125">fatalExecutionEngineError</span></span>](fatalexecutionengineerror-mda.md)|
|[<span data-ttu-id="347a4-126">gcManagedToUnmanaged</span><span class="sxs-lookup"><span data-stu-id="347a4-126">gcManagedToUnmanaged</span></span>](gcmanagedtounmanaged-mda.md)|[<span data-ttu-id="347a4-127">gcUnmanagedToManaged</span><span class="sxs-lookup"><span data-stu-id="347a4-127">gcUnmanagedToManaged</span></span>](gcunmanagedtomanaged-mda.md)|
|[<span data-ttu-id="347a4-128">illegalPrepareConstrainedRegion</span><span class="sxs-lookup"><span data-stu-id="347a4-128">illegalPrepareConstrainedRegion</span></span>](illegalprepareconstrainedregion-mda.md)|[<span data-ttu-id="347a4-129">invalidApartmentStateChange</span><span class="sxs-lookup"><span data-stu-id="347a4-129">invalidApartmentStateChange</span></span>](invalidapartmentstatechange-mda.md)|
|[<span data-ttu-id="347a4-130">invalidCERCall</span><span class="sxs-lookup"><span data-stu-id="347a4-130">invalidCERCall</span></span>](invalidcercall-mda.md)|[<span data-ttu-id="347a4-131">invalidFunctionPointerInDelegate</span><span class="sxs-lookup"><span data-stu-id="347a4-131">invalidFunctionPointerInDelegate</span></span>](invalidfunctionpointerindelegate-mda.md)|
|[<span data-ttu-id="347a4-132">invalidGCHandleCookie</span><span class="sxs-lookup"><span data-stu-id="347a4-132">invalidGCHandleCookie</span></span>](invalidgchandlecookie-mda.md)|[<span data-ttu-id="347a4-133">invalidIUnknown</span><span class="sxs-lookup"><span data-stu-id="347a4-133">invalidIUnknown</span></span>](invalidiunknown-mda.md)|
|[<span data-ttu-id="347a4-134">invalidMemberDeclaration</span><span class="sxs-lookup"><span data-stu-id="347a4-134">invalidMemberDeclaration</span></span>](invalidmemberdeclaration-mda.md)|[<span data-ttu-id="347a4-135">invalidOverlappedToPinvoke</span><span class="sxs-lookup"><span data-stu-id="347a4-135">invalidOverlappedToPinvoke</span></span>](invalidoverlappedtopinvoke-mda.md)|
|[<span data-ttu-id="347a4-136">invalidVariant</span><span class="sxs-lookup"><span data-stu-id="347a4-136">invalidVariant</span></span>](invalidvariant-mda.md)|[<span data-ttu-id="347a4-137">jitCompilationStart</span><span class="sxs-lookup"><span data-stu-id="347a4-137">jitCompilationStart</span></span>](jitcompilationstart-mda.md)|
|[<span data-ttu-id="347a4-138">loaderLock</span><span class="sxs-lookup"><span data-stu-id="347a4-138">loaderLock</span></span>](loaderlock-mda.md)|[<span data-ttu-id="347a4-139">loadFromContext</span><span class="sxs-lookup"><span data-stu-id="347a4-139">loadFromContext</span></span>](loadfromcontext-mda.md)|
|[<span data-ttu-id="347a4-140">marshalCleanupError</span><span class="sxs-lookup"><span data-stu-id="347a4-140">marshalCleanupError</span></span>](marshalcleanuperror-mda.md)|[<span data-ttu-id="347a4-141">marshaling</span><span class="sxs-lookup"><span data-stu-id="347a4-141">marshaling</span></span>](marshaling-mda.md)|
|[<span data-ttu-id="347a4-142">memberInfoCacheCreation</span><span class="sxs-lookup"><span data-stu-id="347a4-142">memberInfoCacheCreation</span></span>](memberinfocachecreation-mda.md)|[<span data-ttu-id="347a4-143">moduloObjectHashcode</span><span class="sxs-lookup"><span data-stu-id="347a4-143">moduloObjectHashcode</span></span>](moduloobjecthashcode-mda.md)|
|[<span data-ttu-id="347a4-144">nonComVisibleBaseClass</span><span class="sxs-lookup"><span data-stu-id="347a4-144">nonComVisibleBaseClass</span></span>](noncomvisiblebaseclass-mda.md)|[<span data-ttu-id="347a4-145">notMarshalable</span><span class="sxs-lookup"><span data-stu-id="347a4-145">notMarshalable</span></span>](notmarshalable-mda.md)|
|[<span data-ttu-id="347a4-146">openGenericCERCall</span><span class="sxs-lookup"><span data-stu-id="347a4-146">openGenericCERCall</span></span>](opengenericcercall-mda.md)|[<span data-ttu-id="347a4-147">overlappedFreeError</span><span class="sxs-lookup"><span data-stu-id="347a4-147">overlappedFreeError</span></span>](overlappedfreeerror-mda.md)|
|[<span data-ttu-id="347a4-148">pInvokeLog</span><span class="sxs-lookup"><span data-stu-id="347a4-148">pInvokeLog</span></span>](pinvokelog-mda.md)|[<span data-ttu-id="347a4-149">pInvokeStackImbalance</span><span class="sxs-lookup"><span data-stu-id="347a4-149">pInvokeStackImbalance</span></span>](pinvokestackimbalance-mda.md)|
|[<span data-ttu-id="347a4-150">raceOnRCWCleanup</span><span class="sxs-lookup"><span data-stu-id="347a4-150">raceOnRCWCleanup</span></span>](raceonrcwcleanup-mda.md)|[<span data-ttu-id="347a4-151">再</span><span class="sxs-lookup"><span data-stu-id="347a4-151">reentrancy</span></span>](reentrancy-mda.md)|
|[<span data-ttu-id="347a4-152">releaseHandleFailed</span><span class="sxs-lookup"><span data-stu-id="347a4-152">releaseHandleFailed</span></span>](releasehandlefailed-mda.md)|[<span data-ttu-id="347a4-153">reportAvOnComRelease</span><span class="sxs-lookup"><span data-stu-id="347a4-153">reportAvOnComRelease</span></span>](reportavoncomrelease-mda.md)|
|[<span data-ttu-id="347a4-154">streamWriterBufferedDataLost</span><span class="sxs-lookup"><span data-stu-id="347a4-154">streamWriterBufferedDataLost</span></span>](streamwriterbuffereddatalost-mda.md)|[<span data-ttu-id="347a4-155">virtualCERCall</span><span class="sxs-lookup"><span data-stu-id="347a4-155">virtualCERCall</span></span>](virtualcercall-mda.md)|

<span data-ttu-id="347a4-156">既定では、.NET Framework はすべてのマネージド デバッガーに対して MDA のサブセットをアクティブにします。</span><span class="sxs-lookup"><span data-stu-id="347a4-156">By default, the .NET Framework activates a subset of MDAs for all managed debuggers.</span></span> <span data-ttu-id="347a4-157">Visual Studio で既定のセットを表示するには**Windows**  >  、[**デバッグ**] メニューの [Windows**例外設定**] を選択し、[**マネージデバッグアシスタント**] の一覧を展開します。</span><span class="sxs-lookup"><span data-stu-id="347a4-157">You can view the default set in Visual Studio by choosing **Windows** > **Exception Settings** on the **Debug** menu, and then expanding the **Managed Debugging Assistants** list.</span></span>

![Visual Studio の [例外設定] ウィンドウ](./media/diagnosing-errors-with-managed-debugging-assistants/exception-settings-mdas.png)

## <a name="enable-and-disable-mdas"></a><span data-ttu-id="347a4-159">Mda を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="347a4-159">Enable and Disable MDAs</span></span>

<span data-ttu-id="347a4-160">MDA は、レジストリ キー、環境変数、およびアプリケーション構成設定を使用して有効または無効にできます。</span><span class="sxs-lookup"><span data-stu-id="347a4-160">You can enable and disable MDAs by using a registry key, an environment variable, and application configuration settings.</span></span> <span data-ttu-id="347a4-161">アプリケーション構成設定を使用するには、レジストリ キーまたは環境変数を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="347a4-161">You must enable either the registry key or the environment variable to use the application configuration settings.</span></span>

> [!TIP]
> <span data-ttu-id="347a4-162">Mda を無効にする代わりに、MDA の通知を受信するたびに、Visual Studio が MDA ダイアログボックスを表示しないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="347a4-162">Instead of disabling MDAs, you can prevent Visual Studio from displaying the MDA dialog box whenever an MDA notification is received.</span></span> <span data-ttu-id="347a4-163">これを行うには、[デバッグ] メニューの [ **Windows**例外設定] をクリックし、[  >  **Exception Settings** **マネージデバッグアシスタント**] の一覧を展開して、個々の MDA に対して [スローされ**たときにブレーク**] チェックボックスをオンまたはオフにします。 **Debug**</span><span class="sxs-lookup"><span data-stu-id="347a4-163">To do that, choose **Windows** > **Exception Settings** on the **Debug** menu, expand the **Managed Debugging Assistants** list, and then select or clear the **Break When Thrown** check box for the individual MDA.</span></span>

### <a name="registry-key"></a><span data-ttu-id="347a4-164">レジストリ キー</span><span class="sxs-lookup"><span data-stu-id="347a4-164">Registry Key</span></span>

<span data-ttu-id="347a4-165">Mda を有効にするには、HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft を追加し\*\* \\ ます。Windows レジストリの Netframework\ MDA\*\*サブキー (型 REG_SZ、値 1)。</span><span class="sxs-lookup"><span data-stu-id="347a4-165">To enable MDAs, add the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework\MDA** subkey (type REG_SZ, value 1) in the Windows registry.</span></span> <span data-ttu-id="347a4-166">次の例を、 *Mdaenable*という名前のテキストファイルにコピーします。Windows レジストリエディター (RegEdit.exe) を開き、[**ファイル**] メニューの [**インポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="347a4-166">Copy the following example into a text file named *MDAEnable.reg*. Open the Windows Registry Editor (RegEdit.exe), and from the **File** menu choose **Import**.</span></span> <span data-ttu-id="347a4-167">*Mdaenable .reg*ファイルを選択して、そのコンピューターで mda を有効にします。</span><span class="sxs-lookup"><span data-stu-id="347a4-167">Select the *MDAEnable.reg* file to enable MDAs on that computer.</span></span> <span data-ttu-id="347a4-168">サブキーを文字列値**1** (DWORD 値**1**以外) に設定すると、 *ApplicationName*.mda.config ファイルから MDA 設定を読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="347a4-168">Setting the subkey to string value of **1** (not DWORD value of **1**) enables the reading of MDA settings from the *ApplicationName.suffix*.mda.config file.</span></span> <span data-ttu-id="347a4-169">たとえば、メモ帳の MDA 構成ファイルには、notepad.exe.mda.config という名前が付けられます。</span><span class="sxs-lookup"><span data-stu-id="347a4-169">For example, the MDA configuration file for Notepad would be named notepad.exe.mda.config.</span></span>

```text
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework]
"MDA"="1"
```

<span data-ttu-id="347a4-170">64 ビット オペレーティング システム上で 32 ビット アプリケーションを実行しているコンピューターでは、MDA キーは次のように設定します。</span><span class="sxs-lookup"><span data-stu-id="347a4-170">If the computer is running a 32-bit application on a 64-bit operating system, then the MDA key should be set like the following:</span></span>

```text
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\.NETFramework]
"MDA"="1"
```

<span data-ttu-id="347a4-171">詳細については[、「アプリケーション固有の構成設定](#application-specific-configuration-settings)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="347a4-171">See [Application-Specific Configuration Settings](#application-specific-configuration-settings) for more information.</span></span> <span data-ttu-id="347a4-172">レジストリ設定は、COMPLUS_MDA 環境変数でオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="347a4-172">The registry setting can be overridden by the COMPLUS_MDA environment variable.</span></span> <span data-ttu-id="347a4-173">詳細については、「[環境変数](#environment-variable)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="347a4-173">See [Environment Variable](#environment-variable) for more information.</span></span>

<span data-ttu-id="347a4-174">Mda を無効にするには、Windows レジストリエディターを使用して、MDA サブキーを**0** (ゼロ) に設定します。</span><span class="sxs-lookup"><span data-stu-id="347a4-174">To disable MDAs, set the MDA subkey to **0** (zero) using the Windows Registry Editor.</span></span>

<span data-ttu-id="347a4-175">MDA には、レジストリ キーを追加しなくても、デバッガーにアタッチされているアプリケーションを実行すると既定で有効になるものがあります。</span><span class="sxs-lookup"><span data-stu-id="347a4-175">By default, some MDAs are enabled when you run an application that is attached to a debugger, even without adding the registry key.</span></span> <span data-ttu-id="347a4-176">これらのアシスタントを無効にするには、このセクションで前述したように*Mdadisable .reg*ファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="347a4-176">You can disable these assistants by running the *MDADisable.reg* file as described earlier in this section.</span></span>

### <a name="environment-variable"></a><span data-ttu-id="347a4-177">環境変数</span><span class="sxs-lookup"><span data-stu-id="347a4-177">Environment Variable</span></span>

<span data-ttu-id="347a4-178">MDA のアクティブ化は、COMPLUS_MDA 環境変数によって制御することもできます。この環境変数はレジストリ キーをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="347a4-178">MDA activation can also controlled by the environment variable COMPLUS_MDA, which overrides the registry key.</span></span> <span data-ttu-id="347a4-179">COMPLUS_MDA の文字列は、MDA 名やその他の特殊制御文字列の、セミコロンで区切られたリストで、大文字小文字の区別はありません。</span><span class="sxs-lookup"><span data-stu-id="347a4-179">The COMPLUS_MDA string is a case-insensitive, semicolon-delimited list of MDA names or other special control strings.</span></span> <span data-ttu-id="347a4-180">マネージド デバッガーやアンマネージド デバッガーの下で起動すると、MDA のセットが既定で有効になります。</span><span class="sxs-lookup"><span data-stu-id="347a4-180">Starting under a managed or unmanaged debugger enables a set of MDAs by default.</span></span> <span data-ttu-id="347a4-181">そのためには、デバッガーの下で既定で有効にする MDA のリスト (セミコロン区切り) を、環境変数またはレジストリ キーの値の前に暗黙的に付加します。</span><span class="sxs-lookup"><span data-stu-id="347a4-181">This is done by implicitly prepending the semicolon-delimited list of MDAs enabled by default under debuggers to the value of the environment variable or registry key.</span></span> <span data-ttu-id="347a4-182">特殊制御文字列は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="347a4-182">The special control strings are the following:</span></span>

- <span data-ttu-id="347a4-183">`0` - すべての MDA を非アクティブにします。</span><span class="sxs-lookup"><span data-stu-id="347a4-183">`0` - Deactivates all MDAs.</span></span>

- <span data-ttu-id="347a4-184">`1` - *ApplicationName*.mda.config から MDA の設定を読み取ります。</span><span class="sxs-lookup"><span data-stu-id="347a4-184">`1` - Reads MDA settings from *ApplicationName*.mda.config.</span></span>

- <span data-ttu-id="347a4-185">`managedDebugger` - デバッガーの下でマネージド実行可能ファイルを起動すると、暗黙的にアクティブ化されているすべての MDA が明示的にアクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="347a4-185">`managedDebugger` - Explicitly activates all MDAs that are implicitly activated when a managed executable is started under a debugger.</span></span>

- <span data-ttu-id="347a4-186">`unmanagedDebugger` - デバッガーの下でアンマネージ実行可能ファイルを起動すると、暗黙的にアクティブ化されているすべての MDA が明示的にアクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="347a4-186">`unmanagedDebugger` - Explicitly activates all MDAs that are implicitly activated when an unmanaged executable is started under a debugger.</span></span>

<span data-ttu-id="347a4-187">競合する設定がある場合は、最新の設定が以前の設定を次のようにオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="347a4-187">If there are conflicting settings, the most recent settings override previous settings:</span></span>

- <span data-ttu-id="347a4-188">`COMPLUS_MDA=0` は、デバッガーの下で暗黙的に有効化されている MDA を含め、すべての MDA を無効にします。</span><span class="sxs-lookup"><span data-stu-id="347a4-188">`COMPLUS_MDA=0` disables all MDAs, including those implicitly enabled under a debugger.</span></span>

- <span data-ttu-id="347a4-189">`COMPLUS_MDA=gcUnmanagedToManaged` は、デバッガーの下で暗黙的に有効化される MDA に加えて `gcUnmanagedToManaged` も有効にします。</span><span class="sxs-lookup"><span data-stu-id="347a4-189">`COMPLUS_MDA=gcUnmanagedToManaged` enables `gcUnmanagedToManaged` in addition to any MDAs that are implicitly enabled under a debugger.</span></span>

- <span data-ttu-id="347a4-190">`COMPLUS_MDA=0;gcUnmanagedToManaged` は `gcUnmanagedToManaged` を有効にしますが、デバッガーの下で別途暗黙的に有効化されている MDA を無効にします。</span><span class="sxs-lookup"><span data-stu-id="347a4-190">`COMPLUS_MDA=0;gcUnmanagedToManaged` enables `gcUnmanagedToManaged` but disables MDAs that would otherwise be implicitly enabled under a debugger.</span></span>

### <a name="application-specific-configuration-settings"></a><span data-ttu-id="347a4-191">アプリケーション固有の構成設定</span><span class="sxs-lookup"><span data-stu-id="347a4-191">Application-Specific Configuration Settings</span></span>

<span data-ttu-id="347a4-192">アプリケーションの MDA 構成ファイルでは、一部のアシスタントを個別に有効化、無効化、および構成できます。</span><span class="sxs-lookup"><span data-stu-id="347a4-192">You can enable, disable, and configure some assistants individually in the MDA configuration file for the application.</span></span> <span data-ttu-id="347a4-193">MDA を構成する目的でアプリケーション構成ファイルの使用を有効にするには、MDA レジストリ キーまたは COMPLUS_MDA 環境変数を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="347a4-193">To enable the use of an application configuration file for configuring MDAs, either the MDA registry key or the COMPLUS_MDA environment variable must be set.</span></span> <span data-ttu-id="347a4-194">アプリケーション構成ファイルは、通常、アプリケーションの実行可能ファイル (.exe) と同じディレクトリに置かれます。</span><span class="sxs-lookup"><span data-stu-id="347a4-194">The application configuration file is typically located in the same directory as the application's executable (.exe) file.</span></span> <span data-ttu-id="347a4-195">ファイル名の形式は*ApplicationName*.mda.config; です。たとえば、notepad.exe.mda.config のようにします。アプリケーション構成ファイルで有効になっているアシスタントには、そのアシスタントの動作を制御するために特別に設計された属性または要素が含まれている場合があります。</span><span class="sxs-lookup"><span data-stu-id="347a4-195">The file name takes the form *ApplicationName*.mda.config; for example, notepad.exe.mda.config. Assistants that are enabled in the application configuration file may have attributes or elements specifically designed to control that assistant's behavior.</span></span>

<span data-ttu-id="347a4-196">次の例は、[マーシャリング](marshaling-mda.md)を有効化および構成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="347a4-196">The following example shows how to enable and configure the [marshaling](marshaling-mda.md):</span></span>

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

<span data-ttu-id="347a4-197">`Marshaling` MDA では、アプリケーションでのマネージド コードからアンマネージド コードへの遷移ごとに、アンマネージド型にマーシャリングされるマネージド型についての情報が出力されます。</span><span class="sxs-lookup"><span data-stu-id="347a4-197">The `Marshaling` MDA emits information about the managed type that is being marshaled to an unmanaged type for each managed-to-unmanaged transition in the application.</span></span> <span data-ttu-id="347a4-198">MDA は、 `Marshaling` **Methodfilter**および**fieldfilter**子要素で指定されたメソッドと構造体のフィールドの名前をそれぞれフィルター処理することもできます。</span><span class="sxs-lookup"><span data-stu-id="347a4-198">The `Marshaling` MDA can also filter the names of the method and structure fields supplied in the **methodFilter** and **fieldFilter** child elements, respectively.</span></span>

<span data-ttu-id="347a4-199">次の例では、既定の設定を使用して複数の Mda を有効にする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="347a4-199">The following example shows how to enable multiple MDAs by using their default settings:</span></span>

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
> <span data-ttu-id="347a4-200">構成ファイルに複数のアシスタントを指定する場合は、アルファベット順に記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="347a4-200">When you specify more than one assistant in a configuration file, you must list them in alphabetical order.</span></span> <span data-ttu-id="347a4-201">たとえば、`virtualCERCall` MDA と `invalidCERCall` MDA の両方を有効にする場合は、`<invalidCERCall />` エントリ、`<virtualCERCall />` エントリの順に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="347a4-201">For example, if you want to enable both the `virtualCERCall` and the `invalidCERCall` MDAs, you must add the `<invalidCERCall />` entry before the `<virtualCERCall />` entry.</span></span> <span data-ttu-id="347a4-202">エントリがアルファベット順になっていない場合、ハンドルされない無効な構成ファイルであることを示す例外メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="347a4-202">If the entries are not in alphabetical order, an unhandled invalid configuration file exception message is displayed.</span></span>

## <a name="mda-exceptions"></a><span data-ttu-id="347a4-203">MDA の例外</span><span class="sxs-lookup"><span data-stu-id="347a4-203">MDA exceptions</span></span>

<span data-ttu-id="347a4-204">MDA が有効になっている場合、デバッガーでコードが実行されていなくても、アクティブになります。</span><span class="sxs-lookup"><span data-stu-id="347a4-204">When an MDA is enabled, it's active even when your code is not executing under a debugger.</span></span> <span data-ttu-id="347a4-205">デバッガーが存在しない場合に MDA イベントが発生した場合、そのイベントはハンドルされない例外とは異なりますが、イベント メッセージはハンドルされない例外のダイアログ ボックスに表示されます。</span><span class="sxs-lookup"><span data-stu-id="347a4-205">If an MDA event is raised when a debugger is not present, the event message is presented in an unhandled exception dialog box, although it is not an unhandled exception.</span></span> <span data-ttu-id="347a4-206">このダイアログ ボックスが表示されないようにするには、デバッグ環境でコードを実行しているのではないときに、MDA を有効にする設定を削除します。</span><span class="sxs-lookup"><span data-stu-id="347a4-206">To avoid the dialog box, remove the MDA-enabling settings when your code is not executing in a debugging environment.</span></span>

<span data-ttu-id="347a4-207">Visual Studio 統合開発環境 (IDE: integrated development environment) でコードを実行すると、特定の MDA イベントに対して表示される [例外] ダイアログボックスを使用しないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="347a4-207">When your code executes in the Visual Studio integrated development environment (IDE), you can avoid the exception dialog box that appears for specific MDA events.</span></span> <span data-ttu-id="347a4-208">これを行うには、[**デバッグ**] メニューの [ **Windows**  >  **例外設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="347a4-208">To do that, on the **Debug** menu, choose **Windows** > **Exception Settings**.</span></span> <span data-ttu-id="347a4-209">[**例外設定**] ウィンドウで、[**マネージデバッグアシスタント**] の一覧を展開し、個々の MDA に対して [スローされ**たときにブレークする**] チェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="347a4-209">In the **Exception Settings** window, expand the **Managed Debugging Assistants** list, and then clear the **Break When Thrown** check box for the individual MDA.</span></span> <span data-ttu-id="347a4-210">また、このダイアログボックスを使用して、MDA の例外ダイアログボックスの表示を*有効*にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="347a4-210">You can also use this dialog box to *enable* the display of MDA exception dialog boxes.</span></span>

## <a name="mda-output"></a><span data-ttu-id="347a4-211">MDA の出力</span><span class="sxs-lookup"><span data-stu-id="347a4-211">MDA Output</span></span>

<span data-ttu-id="347a4-212">MDA の出力は次の例のようになります。 mda からの出力が表示され `PInvokeStackImbalance` ます。</span><span class="sxs-lookup"><span data-stu-id="347a4-212">MDA output is similar to the following example, which shows the output from the `PInvokeStackImbalance` MDA:</span></span>

<span data-ttu-id="347a4-213">**PInvoke 関数 ' MDATest! ' を呼び出しています。MDATest. Program:: StdCall ' がスタックを不均衡にしました。マネージ PInvoke 署名がアンマネージターゲットシグネチャと一致しないことが原因である可能性があります。PInvoke 署名の呼び出し規約とパラメーターが、ターゲットのアンマネージシグネチャと一致することを確認します。**</span><span class="sxs-lookup"><span data-stu-id="347a4-213">**A call to PInvoke function 'MDATest!MDATest.Program::StdCall' has unbalanced the stack. This is likely because the managed PInvoke signature does not match the unmanaged target signature. Check that the calling convention and parameters of the PInvoke signature match the target unmanaged signature.**</span></span>

## <a name="see-also"></a><span data-ttu-id="347a4-214">関連項目</span><span class="sxs-lookup"><span data-stu-id="347a4-214">See also</span></span>

- [<span data-ttu-id="347a4-215">デバッグ、トレース、およびプロファイリング</span><span class="sxs-lookup"><span data-stu-id="347a4-215">Debugging, Tracing, and Profiling</span></span>](index.md)
