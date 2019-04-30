---
title: FindPrivateKey サンプルの WCF
ms.date: 12/04/2017
helpviewer_keywords:
- FindPrivateKey
ms.assetid: 16b54116-0ceb-4413-af0c-753bb2a785a6
ms.openlocfilehash: 72e2f49ae7c39b4a0486ec053ff1164c2d833cbe
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61990094"
---
# <a name="findprivatekey-sample"></a><span data-ttu-id="b661e-102">FindPrivateKey サンプル</span><span class="sxs-lookup"><span data-stu-id="b661e-102">FindPrivateKey sample</span></span>

<span data-ttu-id="b661e-103">証明書ストア内の特定の X.509 証明書に関連付けられている秘密キー ファイルの場所と名前を見つけることが困難な場合があります。</span><span class="sxs-lookup"><span data-stu-id="b661e-103">It can be difficult to find the location and name of the private key file associated with a specific X.509 certificate in the certificate store.</span></span> <span data-ttu-id="b661e-104">FindPrivateKey.exe ツールを使用すると、この処理を容易に実行できます。</span><span class="sxs-lookup"><span data-stu-id="b661e-104">The FindPrivateKey.exe tool facilitates this process.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b661e-105">FindPrivateKey は、使用する前にコンパイルする必要があるサンプルです。</span><span class="sxs-lookup"><span data-stu-id="b661e-105">FindPrivateKey is a sample that needs to be compiled prior to use.</span></span> <span data-ttu-id="b661e-106">参照してください、 [FindPrivateKey プロジェクトをビルドする](#to-build-the-findprivatekey-project)FindPrivateKey ツールをビルドする方法についてのセクション。</span><span class="sxs-lookup"><span data-stu-id="b661e-106">See the [To build the FindPrivateKey project](#to-build-the-findprivatekey-project) section for instructions on how to build the FindPrivateKey tool.</span></span>

<span data-ttu-id="b661e-107">X.509 証明書は、コンピューターの管理者または任意のユーザーによってインストールされます。</span><span class="sxs-lookup"><span data-stu-id="b661e-107">X.509 certificates are installed by an Administrator or any user in the machine.</span></span> <span data-ttu-id="b661e-108">ただし、証明書は、別のアカウントで実行されているサービスによってアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="b661e-108">However, the certificate may be accessed by a service running under a different account.</span></span> <span data-ttu-id="b661e-109">たとえば、ネットワーク サービス アカウント。</span><span class="sxs-lookup"><span data-stu-id="b661e-109">For example, the NETWORK SERVICE account.</span></span>

<span data-ttu-id="b661e-110">別のアカウントでは、秘密キー ファイルへアクセスできない場合があります。これは、証明書が最初にこのアカウントによってインストールされていないからです。</span><span class="sxs-lookup"><span data-stu-id="b661e-110">This account may not have access to the private key file because the certificate was not installed by it originally.</span></span> <span data-ttu-id="b661e-111">FindPrivateKey ツールでは、指定された X.509 証明書の秘密キー ファイルの場所を検索できます。</span><span class="sxs-lookup"><span data-stu-id="b661e-111">The FindPrivateKey tool gives you the location of a given X.509 Certificate's private key file.</span></span> <span data-ttu-id="b661e-112">特定の X.509 証明書の秘密キー ファイルの場所がわかれば、このファイルに対するアクセス許可の追加または削除を実行できます。</span><span class="sxs-lookup"><span data-stu-id="b661e-112">You can add permissions or remove permissions to this file once you know the location of the particular X.509 certificates' private key file.</span></span>

<span data-ttu-id="b661e-113">セキュリティ証明書を使用するサンプルの FindPrivateKey ツールを使用して、 *Setup.bat*ファイル。</span><span class="sxs-lookup"><span data-stu-id="b661e-113">The samples that use certificates for security use the FindPrivateKey tool in the *Setup.bat* file.</span></span> <span data-ttu-id="b661e-114">秘密キー ファイルが見つかったら、その他のツールをなど、使用できる*Cacls.exe*ファイルに適切なアクセス権を設定します。</span><span class="sxs-lookup"><span data-stu-id="b661e-114">Once the private key file has been found, you can use other tools such as *Cacls.exe* to set the appropriate access rights onto the file.</span></span>

<span data-ttu-id="b661e-115">自己ホスト型の実行可能ファイルなどのユーザー アカウントで Windows Communication Foundation (WCF) サービスを実行している場合は、ユーザー アカウントがファイルに読み取り専用アクセスを持つことを確認します。</span><span class="sxs-lookup"><span data-stu-id="b661e-115">When running a Windows Communication Foundation (WCF) service under a user account, such as a self-hosted executable, ensure that the user account has read-only access to the file.</span></span> <span data-ttu-id="b661e-116">WCF サービスでは、インターネット インフォメーション サービス (IIS) を実行するときに、サービスが実行する既定のアカウントは IIS 7 と以前のバージョンで、ネットワーク サービスまたは IIS 7.5、およびそれ以降のバージョンのアプリケーション プール Id です。</span><span class="sxs-lookup"><span data-stu-id="b661e-116">When running a WCF service under Internet Information Services (IIS) the default accounts that the service runs under are the NETWORK SERVICE on IIS 7 and earlier versions, or Application Pool Identity on IIS 7.5 and later versions.</span></span> <span data-ttu-id="b661e-117">詳細については、次を参照してください。[アプリケーション プール Id](/iis/manage/configuring-security/application-pool-identities)します。</span><span class="sxs-lookup"><span data-stu-id="b661e-117">For more information, see [Application Pool Identities](/iis/manage/configuring-security/application-pool-identities).</span></span>

## <a name="examples"></a><span data-ttu-id="b661e-118">使用例</span><span class="sxs-lookup"><span data-stu-id="b661e-118">Examples</span></span>

<span data-ttu-id="b661e-119">対象のプロセスは読み取り権限がない証明書にアクセスするときに次の例のような例外メッセージを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b661e-119">When accessing a certificate for which the process doesn't have read privilege, you see an exception message similar to the following example:</span></span>

```
System.ArgumentException was unhandled
Message="The certificate 'CN=localhost' must have a private key that is capable of key exchange.  The process must have access rights for the private key."
Source="System.ServiceModel"
```

<span data-ttu-id="b661e-120">これが発生して FindPrivateKey ツールを使用して、秘密キー ファイルを検索し、サービスが実行されているプロセスの右へのアクセスを設定します。</span><span class="sxs-lookup"><span data-stu-id="b661e-120">When this occurs, use the FindPrivateKey tool to find the private key file, and then set the access right for the process that the service is running under.</span></span> <span data-ttu-id="b661e-121">たとえば、これは行えます Cacls.exe ツールを使用して次の例に示すように。</span><span class="sxs-lookup"><span data-stu-id="b661e-121">For example, this can be done with the Cacls.exe tool as shown in the following example:</span></span>

```
cacls.exe "C:\Documents and Settings\All Users\Application Data\Microsoft\Crypto\RSA\MachineKeys\8aeda5eb81555f14f8f9960745b5a40d_38f7de48-5ee9-452d-8a5a-92789d7110b1" /E /G "NETWORK SERVICE":R
```

#### <a name="to-build-the-findprivatekey-project"></a><span data-ttu-id="b661e-122">FindPrivateKey プロジェクトをビルドするには</span><span class="sxs-lookup"><span data-stu-id="b661e-122">To build the FindPrivateKey project</span></span>

<span data-ttu-id="b661e-123">プロジェクトをダウンロードするには、次を参照してください。 [Windows Communication Foundation (WCF) と .NET Framework 4 向けの Windows Workflow Foundation (WF) サンプル](https://www.microsoft.com/download/details.aspx?id=21459)します。</span><span class="sxs-lookup"><span data-stu-id="b661e-123">To download the project, visit [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459).</span></span>

1. <span data-ttu-id="b661e-124">開いている[!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)]に移動し、 *WF_WCF_Samples\WCF\Setup\FindPrivateKey\CS*サンプルがインストールされているディレクトリの場所の下のフォルダー。</span><span class="sxs-lookup"><span data-stu-id="b661e-124">Open [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] and navigate to the *WF_WCF_Samples\WCF\Setup\FindPrivateKey\CS* folder under the directory location where you installed the sample.</span></span>

2. <span data-ttu-id="b661e-125">.sln ファイルのアイコンをダブルクリックして、このファイルを Visual Studio で開きます。</span><span class="sxs-lookup"><span data-stu-id="b661e-125">Double-click the .sln file icon to open the file in Visual Studio.</span></span>

3. <span data-ttu-id="b661e-126">**ビルド**メニューの **ソリューションのリビルド**します。</span><span class="sxs-lookup"><span data-stu-id="b661e-126">In the **Build** menu, select **Rebuild Solution**.</span></span>

4. <span data-ttu-id="b661e-127">ソリューションをビルドするには、ファイルが生成されます。FindPrivateKey.exe します。</span><span class="sxs-lookup"><span data-stu-id="b661e-127">Building the solution generates the file: FindPrivateKey.exe.</span></span>

## <a name="conventionscommand-line-entries"></a><span data-ttu-id="b661e-128">規則-コマンドラインのエントリ</span><span class="sxs-lookup"><span data-stu-id="b661e-128">Conventions—Command-Line entries</span></span>

 <span data-ttu-id="b661e-129">"[*オプション*]"は省略可能なパラメーターのセットを表します。</span><span class="sxs-lookup"><span data-stu-id="b661e-129">"[*option*]" represents an optional set of parameters.</span></span>

 <span data-ttu-id="b661e-130">"{*オプション*}"は必須パラメーターのセットを表します。</span><span class="sxs-lookup"><span data-stu-id="b661e-130">"{*option*}" represents a mandatory set of parameters.</span></span>

 <span data-ttu-id="b661e-131">"*option1* &#124; *option2*"オプションのセットから選択を表します。</span><span class="sxs-lookup"><span data-stu-id="b661e-131">"*option1* &#124; *option2*" represents a choice between sets of options.</span></span>

 <span data-ttu-id="b661e-132">"\<*値*>"を入力するパラメーター値を表します。</span><span class="sxs-lookup"><span data-stu-id="b661e-132">"\<*value*>" represents a parameter value to be entered.</span></span>

## <a name="usage"></a><span data-ttu-id="b661e-133">使用法</span><span class="sxs-lookup"><span data-stu-id="b661e-133">Usage</span></span>

```
FindPrivateKey <storeName> <storeLocation> [{ {-n <subjectName>} | {-t <thumbprint>} } [-f | -d | -a]]
```

<span data-ttu-id="b661e-134">この場合、</span><span class="sxs-lookup"><span data-stu-id="b661e-134">Where:</span></span>

```
       <subjectName> The subject name of the certificate
       <thumbprint>  The thumbprint of the certificate (You can use the Certmgr.exe tool to find this)
       -f            output file name only
       -d            output directory only
       -a            output absolute file name
```

<span data-ttu-id="b661e-135">コマンド プロンプト パラメーターが指定されていない場合は、このヘルプ テキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b661e-135">If no parameters are specified at the command prompt, then this help text is displayed.</span></span>

## <a name="examples"></a><span data-ttu-id="b661e-136">使用例</span><span class="sxs-lookup"><span data-stu-id="b661e-136">Examples</span></span>

<span data-ttu-id="b661e-137">この例のサブジェクト名を持つ証明書のファイル名を検索する"CN = localhost"、現在のユーザーの個人用ストアにします。</span><span class="sxs-lookup"><span data-stu-id="b661e-137">This example finds the filename of the certificate with a subject name of "CN=localhost", in the Personal store of the Current User.</span></span>

```
FindPrivateKey My CurrentUser -n "CN=localhost"
```

<span data-ttu-id="b661e-138">この例のサブジェクト名を持つ証明書のファイル名を検索する"CN = localhost"、個人用の出力ディレクトリの完全なパスと、現在のユーザーのストアします。</span><span class="sxs-lookup"><span data-stu-id="b661e-138">This example finds the filename of the certificate with a subject name of "CN=localhost", in the Personal store of the Current User and output the full directory path.</span></span>

```
FindPrivateKey My CurrentUser -n "CN=localhost" -a
```

<span data-ttu-id="b661e-139">この例では、ローカル コンピューターの Personal ストアで、"03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52" というサムプリントを持つ証明書のファイル名を検索します。</span><span class="sxs-lookup"><span data-stu-id="b661e-139">This example finds the filename of the certificate with a thumbprint of "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52", in the Personal store of the Local Computer.</span></span>

```
FindPrivateKey My LocalMachine -t "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52"
```
