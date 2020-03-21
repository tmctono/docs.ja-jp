---
title: PII セキュリティ ロックダウン
ms.date: 03/30/2017
ms.assetid: c44fb338-9527-4dd0-8607-b8787d15acb4
ms.openlocfilehash: ad4f4a024b04a028b815faedded58713e001cab0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79144267"
---
# <a name="pii-security-lockdown"></a><span data-ttu-id="48f88-102">PII セキュリティ ロックダウン</span><span class="sxs-lookup"><span data-stu-id="48f88-102">PII Security Lockdown</span></span>
<span data-ttu-id="48f88-103">このサンプルでは、次の方法で Windows 通信基盤 (WCF) サービスのいくつかのセキュリティ関連機能を制御する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="48f88-103">This sample demonstrates how to control several security-related features of a Windows Communication Foundation (WCF) service by:</span></span>  
  
- <span data-ttu-id="48f88-104">サービスの構成ファイル内の機密情報を暗号化します。</span><span class="sxs-lookup"><span data-stu-id="48f88-104">Encrypting sensitive information in a service's configuration file.</span></span>  
  
- <span data-ttu-id="48f88-105">入れ子になったサービス サブディレクトリが設定をオーバーライドできないように、構成ファイル内の要素をロックします。</span><span class="sxs-lookup"><span data-stu-id="48f88-105">Locking elements in the configuration file so that nested service subdirectories cannot override settings.</span></span>  
  
- <span data-ttu-id="48f88-106">トレースおよびメッセージ ログで、個人を特定できる情報 (PII) のログ記録を制御します。</span><span class="sxs-lookup"><span data-stu-id="48f88-106">Controlling the logging of Personally Identifiable Information (PII) in trace and message logs.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="48f88-107">サンプルは、既にコンピューターにインストールされている場合があります。</span><span class="sxs-lookup"><span data-stu-id="48f88-107">The samples may already be installed on your computer.</span></span> <span data-ttu-id="48f88-108">続行する前に、次の (既定の) ディレクトリを確認してください。</span><span class="sxs-lookup"><span data-stu-id="48f88-108">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="48f88-109">このディレクトリが存在しない場合は[、.NET Framework 4 の Windows コミュニケーション ファウンデーション (WCF) および Windows ワークフローファウンデーション (WF) サンプル](https://www.microsoft.com/download/details.aspx?id=21459)に移動して、すべての Windows 通信基盤 (WCF) とサンプルを[!INCLUDE[wf1](../../../../includes/wf1-md.md)]ダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="48f88-109">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="48f88-110">このサンプルは、次のディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="48f88-110">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\SecurityLockdown`  
  
## <a name="discussion"></a><span data-ttu-id="48f88-111">ディスカッション</span><span class="sxs-lookup"><span data-stu-id="48f88-111">Discussion</span></span>  
 <span data-ttu-id="48f88-112">これらの各機能を単独または組み合わせて使用することにより、サービスのさまざまなセキュリティを制御できます。</span><span class="sxs-lookup"><span data-stu-id="48f88-112">Each of these features can be used separately or together to control aspects of a service's security.</span></span> <span data-ttu-id="48f88-113">これは、WCF サービスをセキュリティで保護するための決定的なガイドではありません。</span><span class="sxs-lookup"><span data-stu-id="48f88-113">This is not a definitive guide to securing a WCF service.</span></span>  
  
 <span data-ttu-id="48f88-114">.NET Framework の構成ファイルには、データベースに接続するための接続文字列などの機密情報を格納できます。</span><span class="sxs-lookup"><span data-stu-id="48f88-114">The .NET Framework configuration files can contain sensitive information such as connection strings to connect to databases.</span></span> <span data-ttu-id="48f88-115">共有の Web ホストのシナリオでは、この情報をサービスの構成ファイル内で暗号化して、構成ファイル内に含まれるデータを偶発的に表示されないようにすることが望ましい場合があります。</span><span class="sxs-lookup"><span data-stu-id="48f88-115">In shared, Web-hosted scenarios it may be desirable to encrypt this information in the configuration file for a service so that the data contained within the configuration file is resistant to casual viewing.</span></span> <span data-ttu-id="48f88-116">.NET Framework 2.0 以降のバージョンでは、Windows データ保護アプリケーション プログラミング インターフェイス (DPAPI) または RSA 暗号化プロバイダを使用して、構成ファイルの一部を暗号化できます。</span><span class="sxs-lookup"><span data-stu-id="48f88-116">.NET Framework 2.0 and later has the ability to encrypt portions of the configuration file using the Windows Data Protection application programming interface (DPAPI) or the RSA Cryptographic provider.</span></span> <span data-ttu-id="48f88-117">DPAPI または RSA を使用して aspnet_regiis.exe を実行すると、構成ファイルの選択部分を暗号化できます。</span><span class="sxs-lookup"><span data-stu-id="48f88-117">The aspnet_regiis.exe using the DPAPI or RSA can encrypt select portions of a configuration file.</span></span>  
  
 <span data-ttu-id="48f88-118">Web ホストのシナリオでは、他のサービスのサブディレクトリにサービスを設定できます。</span><span class="sxs-lookup"><span data-stu-id="48f88-118">In Web-hosted scenarios it is possible to have services in subdirectories of other services.</span></span> <span data-ttu-id="48f88-119">構成値を決定する既定の意味的方法によると、入れ子になったディレクトリ内の構成ファイルで親ディレクトリの構成値をオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="48f88-119">The default semantic for determining configuration values allows configuration files in the nested directories to override the configuration values in the parent directory.</span></span> <span data-ttu-id="48f88-120">特定の状況では、さまざまな理由でこれが望ましくない場合があります。</span><span class="sxs-lookup"><span data-stu-id="48f88-120">In certain situations this may be undesirable for a variety of reasons.</span></span> <span data-ttu-id="48f88-121">WCF サービス構成では、構成値のロックがサポートされるため、入れ子になった構成は、オーバーライドされた構成値を使用して入れ子になったサービスを実行するときに例外を生成します。</span><span class="sxs-lookup"><span data-stu-id="48f88-121">WCF service configuration supports the locking of configuration values so that nested configuration generates exceptions when a nested service is run using overridden configuration values.</span></span>  
  
 <span data-ttu-id="48f88-122">このサンプルでは、トレースおよびメッセージ ログによる、ユーザー名やパスワードなどの個人を特定できる既知の情報 (PII) のログ記録を制御する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="48f88-122">This sample demonstrates how to control the logging of known Personally Identifiable Information (PII) in trace and message logs, such as username and password.</span></span> <span data-ttu-id="48f88-123">既定では、既知の PII のログ記録は無効です。ただし特定の状況では、PII のログ記録はアプリケーションをデバック処理する際に重要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="48f88-123">By default, logging of known PII is disabled however in certain situations logging of PII can be important in debugging an application.</span></span> <span data-ttu-id="48f88-124">このサンプルは、[作業の開始に](../../../../docs/framework/wcf/samples/getting-started-sample.md)基づいています。</span><span class="sxs-lookup"><span data-stu-id="48f88-124">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span> <span data-ttu-id="48f88-125">さらに、このサンプルではトレースとメッセージ ログを使用します。</span><span class="sxs-lookup"><span data-stu-id="48f88-125">In addition, this sample uses tracing and message logging.</span></span> <span data-ttu-id="48f88-126">詳細については、「[トレースとメッセージ ログ](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md)のサンプル」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="48f88-126">For more information, see the [Tracing and Message Logging](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md) sample.</span></span>  
  
## <a name="encrypting-configuration-file-elements"></a><span data-ttu-id="48f88-127">構成ファイルの要素の暗号化</span><span class="sxs-lookup"><span data-stu-id="48f88-127">Encrypting Configuration File Elements</span></span>  
 <span data-ttu-id="48f88-128">共有 Web ホストの環境をセキュリティ保護するには、機密情報が含まれる可能性のあるデータベース接続文字列など、特定の構成要素を暗号化することが望ましい場合があります。</span><span class="sxs-lookup"><span data-stu-id="48f88-128">For security purposes in a shared Web-hosting environment, it may be desirable to encrypt certain configuration elements, such as database connection strings that may contain sensitive information.</span></span> <span data-ttu-id="48f88-129">構成要素は、.NET Framework フォルダーにあるaspnet_regiis.exe ツールを使用して暗号化できます。</span><span class="sxs-lookup"><span data-stu-id="48f88-129">A configuration element may be encrypted using the aspnet_regiis.exe tool found in the .NET Framework folder For example, %WINDIR%\Microsoft.NET\Framework\v4.0.20728.</span></span>  
  
#### <a name="to-encrypt-the-values-in-the-appsettings-section-in-webconfig-for-the-sample"></a><span data-ttu-id="48f88-130">サンプルの Web.config で appSettings セクションの値を暗号化するには</span><span class="sxs-lookup"><span data-stu-id="48f88-130">To encrypt the values in the appSettings section in Web.config for the sample</span></span>  
  
1. <span data-ttu-id="48f88-131">[実行の開始] を使用してコマンド プロンプト>開きます。</span><span class="sxs-lookup"><span data-stu-id="48f88-131">Open a command prompt by using Start->Run….</span></span> <span data-ttu-id="48f88-132">を入力`cmd`して **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="48f88-132">Type in `cmd` and click **OK**.</span></span>  
  
2. <span data-ttu-id="48f88-133">コマンド「`cd %WINDIR%\Microsoft.NET\Framework\v4.0.20728`」を実行して、現在の .NET Framework ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="48f88-133">Navigate to the current .NET Framework directory by issuing the following command: `cd %WINDIR%\Microsoft.NET\Framework\v4.0.20728`.</span></span>  
  
3. <span data-ttu-id="48f88-134">コマンド「`aspnet_regiis -pe "appSettings" -app "/servicemodelsamples" -prov "DataProtectionConfigurationProvider"`」を実行して、Web.config フォルダーの appSettings 構成設定を暗号化します。</span><span class="sxs-lookup"><span data-stu-id="48f88-134">Encrypt the appSettings configuration settings in the Web.config folder by issuing the following command: `aspnet_regiis -pe "appSettings" -app "/servicemodelsamples" -prov "DataProtectionConfigurationProvider"`.</span></span>  
  
 <span data-ttu-id="48f88-135">構成ファイルの暗号化セクションの詳細については、ASP.NET構成の DPAPI の方法 ([セキュリティで保護されたASP.NET アプリケーションの構築: 認証、承認、およびセキュリティで保護された通信](https://docs.microsoft.com/previous-versions/msp-n-p/ff649248(v=pandp.10))) と、ASP.NET構成の RSA の方法 ([[方法: RSA を使用して ASP.NET 2.0 の構成セクションを暗号化する](https://docs.microsoft.com/previous-versions/msp-n-p/ff650304(v=pandp.10))] ) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="48f88-135">More information about encrypting sections of configuration files can be found by reading a how-to on DPAPI in ASP.NET configuration ([Building Secure ASP.NET Applications: Authentication, Authorization, and Secure Communication](https://docs.microsoft.com/previous-versions/msp-n-p/ff649248(v=pandp.10))) and a how-to on RSA in ASP.NET configuration ([How To: Encrypt Configuration Sections in ASP.NET 2.0 Using RSA](https://docs.microsoft.com/previous-versions/msp-n-p/ff650304(v=pandp.10))).</span></span>  
  
## <a name="locking-configuration-file-elements"></a><span data-ttu-id="48f88-136">構成ファイルの要素のロック</span><span class="sxs-lookup"><span data-stu-id="48f88-136">Locking configuration file elements</span></span>  
 <span data-ttu-id="48f88-137">Web ホストのシナリオでは、サービスのサブディレクトリにサービスを設定できます。</span><span class="sxs-lookup"><span data-stu-id="48f88-137">In Web-hosted scenarios, it is possible to have services in subdirectories of services.</span></span> <span data-ttu-id="48f88-138">こうした状況で、サブディレクトリ内のサービスの構成値を計算するには、Machine.config 内の値を調べ、続いて親ディレクトリの任意の Web.config ファイルとマージしてディレクトリ ツリーの下層に移動します。そして最後に、サービスが含まれるディレクトリ内の Web.config ファイルをマージします。</span><span class="sxs-lookup"><span data-stu-id="48f88-138">In these situations, configuration values for the service in the subdirectory are calculated by examining values in Machine.config and successively merging with any Web.config files in parent directories moving down the directory tree and finally merging the Web.config file in the directory that contains the service.</span></span> <span data-ttu-id="48f88-139">ほとんどの構成要素での既定の動作は、サブディレクトリ内の構成ファイルが、親ディレクトリに設定されている値をオーバーライドできるようにすることです。</span><span class="sxs-lookup"><span data-stu-id="48f88-139">The default behavior for most configuration elements is to allow configuration files in subdirectories to override the values set in parent directories.</span></span> <span data-ttu-id="48f88-140">特定の状況では、サブディレクトリ内の構成ファイルが、親ディレクトリの構成に設定されている値をオーバーライドしないようにするのが望ましい場合があります。</span><span class="sxs-lookup"><span data-stu-id="48f88-140">In certain situations it may be desirable to prevent configuration files in subdirectories from overriding values set in parent directory configuration.</span></span>  
  
 <span data-ttu-id="48f88-141">.NET Framework では、構成ファイルの要素をロックして、ロックされた構成要素をオーバーライドする構成が実行時例外をスローするように設定できます。</span><span class="sxs-lookup"><span data-stu-id="48f88-141">The .NET Framework provides a way to lock configuration file elements so that configurations that override locked configuration elements throw run-time exceptions.</span></span>  
  
 <span data-ttu-id="48f88-142">構成要素をロックするには、構成ファイルのノードに対して `lockItem` 属性を指定します。たとえば、入れ子になった構成ファイル内の電卓サービスが動作を変更できないように構成ファイルの CalculatorServiceBehavior ノードをロックするには、次の構成を使用できます。</span><span class="sxs-lookup"><span data-stu-id="48f88-142">A configuration element can be locked by specifying the `lockItem` attribute for a node in the configuration file, for example, to lock the CalculatorServiceBehavior node in the configuration file so that calculator services in nested configuration files cannot change the behavior, the following configuration can be used.</span></span>  
  
```xml  
<configuration>  
   <system.serviceModel>  
      <behaviors>
          <serviceBehaviors>
             <behavior name="CalculatorServiceBehavior" lockItem="true">
               <serviceMetadata httpGetEnabled="True"/>
               <serviceDebug includeExceptionDetailInFaults="False" />
             </behavior>
          </serviceBehaviors>
       </behaviors>
    </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="48f88-143">構成要素はより詳細な単位でロックできます。</span><span class="sxs-lookup"><span data-stu-id="48f88-143">Locking of configuration elements can be more specific.</span></span> <span data-ttu-id="48f88-144">要素の一覧は、サブ要素のコレクション内にある一連の要素をロックするための `lockElements` に対する値として指定できます。</span><span class="sxs-lookup"><span data-stu-id="48f88-144">A list of elements can be specified as the value to the `lockElements` to lock a set of elements within a collection of sub-elements.</span></span> <span data-ttu-id="48f88-145">属性の一覧は、要素内にある一連の属性をロックするための `lockAttributes` に対する値として指定できます。</span><span class="sxs-lookup"><span data-stu-id="48f88-145">A list of attributes can be specified as the value to the `lockAttributes` to lock a set of attributes within an element.</span></span> <span data-ttu-id="48f88-146">要素または属性のコレクション全体をロックすることもできます。ただし、ノードで `lockAllElementsExcept` 属性または `lockAllAttributesExcept` 属性が指定されている一覧は除きます。</span><span class="sxs-lookup"><span data-stu-id="48f88-146">An entire collection of elements or attributes can be locked except for a specified list by specifying the `lockAllElementsExcept` or `lockAllAttributesExcept` attributes on a node.</span></span>  
  
## <a name="pii-logging-configuration"></a><span data-ttu-id="48f88-147">PII ログの構成</span><span class="sxs-lookup"><span data-stu-id="48f88-147">PII Logging Configuration</span></span>  
 <span data-ttu-id="48f88-148">PII のログ記録は 2 つのスイッチで制御されます。1 つは Machine.config にあるコンピューター全体の設定で、コンピューターの管理者がこれを使用することにより、PII のログ記録を許可または拒否できます。もう 1 つはアプリケーション設定で、アプリケーションの管理者がこれを使用することにより、Web.config または App.config ファイル内の各ソースで PII のログ記録の有効/無効を切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="48f88-148">Logging of PII is controlled by two switches: a computer-wide setting found in Machine.config that allows a computer administrator to permit or deny logging of PII and an application setting that allows an application administrator to toggle logging of PII for each source in a Web.config or App.config file.</span></span>  
  
 <span data-ttu-id="48f88-149">コンピュータ全体の設定は、Machine.config `enableLoggingKnownPii` `true`の`false``machineSettings`要素で or を設定することによって制御されます。たとえば、次の例では、アプリケーションが PII のログを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="48f88-149">The computer-wide setting is controlled by setting `enableLoggingKnownPii` to `true` or `false`, in the `machineSettings` element in Machine.config. For example, the following allows applications to turn on logging of PII.</span></span>  
  
```xml  
<configuration>  
    <system.serviceModel>  
        <machineSettings enableLoggingKnownPii="true" />  
    </system.serviceModel>  
</configuration>  
```  
  
> [!NOTE]
> <span data-ttu-id="48f88-150">Machine.config ファイルの既定の場所は %WINDIR%\Microsoft.NET\Framework\v2.0.50727\CONFIG です。</span><span class="sxs-lookup"><span data-stu-id="48f88-150">The Machine.config file has a default location: %WINDIR%\Microsoft.NET\Framework\v2.0.50727\CONFIG.</span></span>  
  
 <span data-ttu-id="48f88-151">`enableLoggingKnownPii` 属性が Machine.config にない場合、PII のログ記録は許可されません。</span><span class="sxs-lookup"><span data-stu-id="48f88-151">If the `enableLoggingKnownPii` attribute is not present in Machine.config, logging of PII is not allowed.</span></span>  
  
 <span data-ttu-id="48f88-152">アプリケーションで PII のログ記録を有効にするには、Web.config または App.config ファイルで、ソース要素の `logKnownPii` 属性を `true` または `false` に設定します。</span><span class="sxs-lookup"><span data-stu-id="48f88-152">Enabling logging of PII for an application is done by setting the `logKnownPii` attribute of the source element to `true` or `false` in the Web.config or App.config file.</span></span> <span data-ttu-id="48f88-153">たとえば次の例では、メッセージ ログとトレース ログの両方に対して PII のログ記録が有効になります。</span><span class="sxs-lookup"><span data-stu-id="48f88-153">For example, the following enables logging of PII for both message logging and trace logging.</span></span>  
  
```xml  
<configuration>  
    <system.diagnostics>  
        <sources>  
            <source name="System.ServiceModel.MessageLogging" logKnownPii="true">  
                <listeners>
                ...
                </listeners>  
            </source>  
            <source name="System.ServiceModel" switchValue="Verbose, ActivityTracing">  
            <listeners>  
        ...
            </listeners>  
            </source>  
        </sources>  
    </system.diagnostics>  
</configuration>  
```  
  
 <span data-ttu-id="48f88-154">`logKnownPii` 属性が指定されていない場合は、PII はログ記録されません。</span><span class="sxs-lookup"><span data-stu-id="48f88-154">If the `logKnownPii` attribute is not specified, then PII is not logged.</span></span>  
  
 <span data-ttu-id="48f88-155">PII がログ記録されるのは、`enableLoggingKnownPii` が `true` に設定されていると共に、`logKnownPii` が `true` に設定されている場合だけです。</span><span class="sxs-lookup"><span data-stu-id="48f88-155">PII is only logged if both `enableLoggingKnownPii` is set to `true`, and `logKnownPii` is set to `true`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="48f88-156">System.Diagnostics は、構成ファイルの最初に表示されているソース以外の、すべてのソースのすべての属性を無視します。</span><span class="sxs-lookup"><span data-stu-id="48f88-156">System.Diagnostics ignores all attributes on all sources except the first one listed in the configuration file.</span></span> <span data-ttu-id="48f88-157">`logKnownPii` 属性を構成ファイル内の 2 番目のソースに追加しても、結果は変わりません。</span><span class="sxs-lookup"><span data-stu-id="48f88-157">Adding the `logKnownPii` attribute to the second source in the configuration file has no effect.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="48f88-158">このサンプルを実行するには、Machine.config を手動で変更する必要があります。Machine.config を正しくない値または構文に変更すると、すべての .NET Framework アプリケーションの実行が妨げになる可能性があるため、注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="48f88-158">To run this sample involves manual modification of Machine.config. Care should be taken when modifying Machine.config as incorrect values or syntax may prevent all .NET Framework applications from running.</span></span>  
  
 <span data-ttu-id="48f88-159">また、DPAPI や RSA を使用して構成ファイルの要素を暗号化することもできます。</span><span class="sxs-lookup"><span data-stu-id="48f88-159">It is also possible to encrypt configuration file elements using DPAPI and RSA.</span></span> <span data-ttu-id="48f88-160">詳細については、次のリンクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="48f88-160">For more information, see the following links:</span></span>  
  
- <span data-ttu-id="48f88-161">[セキュリティで保護されたASP.NETアプリケーションの構築: 認証、承認、およびセキュリティで保護された通信](https://docs.microsoft.com/previous-versions/msp-n-p/ff649248(v=pandp.10))</span><span class="sxs-lookup"><span data-stu-id="48f88-161">[Building Secure ASP.NET Applications: Authentication, Authorization, and Secure Communication](https://docs.microsoft.com/previous-versions/msp-n-p/ff649248(v=pandp.10))</span></span>  
  
- <span data-ttu-id="48f88-162">[方法 : RSA を使用して ASP.NET 2.0 で構成セクションを暗号化する](https://docs.microsoft.com/previous-versions/msp-n-p/ff650304(v=pandp.10))</span><span class="sxs-lookup"><span data-stu-id="48f88-162">[How To: Encrypt Configuration Sections in ASP.NET 2.0 Using RSA](https://docs.microsoft.com/previous-versions/msp-n-p/ff650304(v=pandp.10))</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="48f88-163">サンプルを設定、ビルド、および実行するには</span><span class="sxs-lookup"><span data-stu-id="48f88-163">To set up, build and run the sample</span></span>  
  
1. <span data-ttu-id="48f88-164">[Windows コミュニケーションファウンデーション サンプルのワンタイム セットアップ手順を](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)実行したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="48f88-164">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="48f88-165">Machine.config を編集して `enableLoggingKnownPii` 属性を `true` に設定し、必要に応じて親ノードを追加します。</span><span class="sxs-lookup"><span data-stu-id="48f88-165">Edit Machine.config to set the `enableLoggingKnownPii` attribute to `true`, adding the parent nodes if necessary.</span></span>  
  
3. <span data-ttu-id="48f88-166">ソリューションの C# 版または Visual Basic .NET 版をビルドするには、「 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="48f88-166">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4. <span data-ttu-id="48f88-167">単一または複数のコンピューターにまたがる構成でサンプルを実行するには、「 [Windows コミュニケーション ファウンデーション サンプルの実行](../../../../docs/framework/wcf/samples/running-the-samples.md)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="48f88-167">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
#### <a name="to-clean-up-the-sample"></a><span data-ttu-id="48f88-168">サンプルをクリーンアップするには</span><span class="sxs-lookup"><span data-stu-id="48f88-168">To clean up the sample</span></span>  
  
1. <span data-ttu-id="48f88-169">Machine.config を編集して `enableLoggingKnownPii` 属性を `false` に設定します。</span><span class="sxs-lookup"><span data-stu-id="48f88-169">Edit Machine.config to set the `enableLoggingKnownPii` attribute to `false`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48f88-170">関連項目</span><span class="sxs-lookup"><span data-stu-id="48f88-170">See also</span></span>

- <span data-ttu-id="48f88-171">[AppFabric の監視のサンプル](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="48f88-171">[AppFabric Monitoring Samples](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span></span>
