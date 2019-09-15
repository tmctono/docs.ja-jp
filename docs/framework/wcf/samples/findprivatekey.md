---
title: FindPrivateKey サンプル-WCF
ms.date: 12/04/2017
helpviewer_keywords:
- FindPrivateKey
ms.assetid: 16b54116-0ceb-4413-af0c-753bb2a785a6
ms.openlocfilehash: 4ba4316489c1494da9421bea5c513e44c6eb50a7
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2019
ms.locfileid: "70989882"
---
# <a name="findprivatekey-sample"></a><span data-ttu-id="945a1-102">FindPrivateKey サンプル</span><span class="sxs-lookup"><span data-stu-id="945a1-102">FindPrivateKey sample</span></span>

<span data-ttu-id="945a1-103">証明書ストア内の特定の X.509 証明書に関連付けられている秘密キー ファイルの場所と名前を見つけることが困難な場合があります。</span><span class="sxs-lookup"><span data-stu-id="945a1-103">It can be difficult to find the location and name of the private key file associated with a specific X.509 certificate in the certificate store.</span></span> <span data-ttu-id="945a1-104">FindPrivateKey.exe ツールを使用すると、この処理を容易に実行できます。</span><span class="sxs-lookup"><span data-stu-id="945a1-104">The FindPrivateKey.exe tool facilitates this process.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="945a1-105">FindPrivateKey は、使用する前にコンパイルする必要があるサンプルです。</span><span class="sxs-lookup"><span data-stu-id="945a1-105">FindPrivateKey is a sample that needs to be compiled prior to use.</span></span> <span data-ttu-id="945a1-106">FindPrivateKey ツールのビルド方法については、「 [FindPrivateKey プロジェクトをビルドするに](#to-build-the-findprivatekey-project)は」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="945a1-106">See the [To build the FindPrivateKey project](#to-build-the-findprivatekey-project) section for instructions on how to build the FindPrivateKey tool.</span></span>

<span data-ttu-id="945a1-107">X.509 証明書は、コンピューターの管理者または任意のユーザーによってインストールされます。</span><span class="sxs-lookup"><span data-stu-id="945a1-107">X.509 certificates are installed by an Administrator or any user in the machine.</span></span> <span data-ttu-id="945a1-108">ただし、別のアカウントで実行されているサービスが証明書にアクセスする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="945a1-108">However, the certificate may be accessed by a service running under a different account.</span></span> <span data-ttu-id="945a1-109">たとえば、NETWORK SERVICE アカウントなどです。</span><span class="sxs-lookup"><span data-stu-id="945a1-109">For example, the NETWORK SERVICE account.</span></span>

<span data-ttu-id="945a1-110">別のアカウントでは、秘密キー ファイルへアクセスできない場合があります。これは、証明書が最初にこのアカウントによってインストールされていないからです。</span><span class="sxs-lookup"><span data-stu-id="945a1-110">This account may not have access to the private key file because the certificate was not installed by it originally.</span></span> <span data-ttu-id="945a1-111">FindPrivateKey ツールでは、指定された X.509 証明書の秘密キー ファイルの場所を検索できます。</span><span class="sxs-lookup"><span data-stu-id="945a1-111">The FindPrivateKey tool gives you the location of a given X.509 Certificate's private key file.</span></span> <span data-ttu-id="945a1-112">特定の X.509 証明書の秘密キー ファイルの場所がわかれば、このファイルに対するアクセス許可の追加または削除を実行できます。</span><span class="sxs-lookup"><span data-stu-id="945a1-112">You can add permissions or remove permissions to this file once you know the location of the particular X.509 certificates' private key file.</span></span>

<span data-ttu-id="945a1-113">セキュリティのために証明書を使用するサンプルでは、*セットアップの .bat*ファイルで FindPrivateKey ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="945a1-113">The samples that use certificates for security use the FindPrivateKey tool in the *Setup.bat* file.</span></span> <span data-ttu-id="945a1-114">秘密キーファイルが見つかったら、 *cacls.exe*などの他のツールを使用して、ファイルに対する適切なアクセス権を設定できます。</span><span class="sxs-lookup"><span data-stu-id="945a1-114">Once the private key file has been found, you can use other tools such as *Cacls.exe* to set the appropriate access rights onto the file.</span></span>

<span data-ttu-id="945a1-115">自己ホスト型実行可能ファイルなどのユーザーアカウントで Windows Communication Foundation (WCF) サービスを実行する場合は、そのユーザーアカウントにファイルへの読み取り専用アクセス権があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="945a1-115">When running a Windows Communication Foundation (WCF) service under a user account, such as a self-hosted executable, ensure that the user account has read-only access to the file.</span></span> <span data-ttu-id="945a1-116">インターネットインフォメーションサービス (IIS) で WCF サービスを実行する場合、サービスを実行する既定のアカウントは、IIS 7 以前のバージョンのネットワークサービス、または IIS 7.5 以降のバージョンのアプリケーションプール Id です。</span><span class="sxs-lookup"><span data-stu-id="945a1-116">When running a WCF service under Internet Information Services (IIS) the default accounts that the service runs under are the NETWORK SERVICE on IIS 7 and earlier versions, or Application Pool Identity on IIS 7.5 and later versions.</span></span> <span data-ttu-id="945a1-117">詳細については、「[アプリケーションプール id](/iis/manage/configuring-security/application-pool-identities)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="945a1-117">For more information, see [Application Pool Identities](/iis/manage/configuring-security/application-pool-identities).</span></span>

## <a name="examples"></a><span data-ttu-id="945a1-118">使用例</span><span class="sxs-lookup"><span data-stu-id="945a1-118">Examples</span></span>

<span data-ttu-id="945a1-119">プロセスに読み取り権限がない証明書にアクセスすると、次の例のような例外メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="945a1-119">When accessing a certificate for which the process doesn't have read privilege, you see an exception message similar to the following example:</span></span>

```output
System.ArgumentException was unhandled
Message="The certificate 'CN=localhost' must have a private key that is capable of key exchange.  The process must have access rights for the private key."
Source="System.ServiceModel"
```

<span data-ttu-id="945a1-120">この場合は、FindPrivateKey ツールを使用して秘密キーファイルを検索し、サービスが実行されているプロセスのアクセス権を設定します。</span><span class="sxs-lookup"><span data-stu-id="945a1-120">When this occurs, use the FindPrivateKey tool to find the private key file, and then set the access right for the process that the service is running under.</span></span> <span data-ttu-id="945a1-121">たとえば、次の例に示すように、Cacls.exe ツールを使用してこれを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="945a1-121">For example, this can be done with the Cacls.exe tool as shown in the following example:</span></span>

```console
cacls.exe "C:\Documents and Settings\All Users\Application Data\Microsoft\Crypto\RSA\MachineKeys\8aeda5eb81555f14f8f9960745b5a40d_38f7de48-5ee9-452d-8a5a-92789d7110b1" /E /G "NETWORK SERVICE":R
```

#### <a name="to-build-the-findprivatekey-project"></a><span data-ttu-id="945a1-122">FindPrivateKey プロジェクトをビルドするには</span><span class="sxs-lookup"><span data-stu-id="945a1-122">To build the FindPrivateKey project</span></span>

<span data-ttu-id="945a1-123">プロジェクトをダウンロードするには、 [Windows Communication Foundation (WCF) および Windows Workflow Foundation (WF) のサンプル .NET Framework 4 を](https://www.microsoft.com/download/details.aspx?id=21459)参照してください。</span><span class="sxs-lookup"><span data-stu-id="945a1-123">To download the project, visit [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459).</span></span>

1. <span data-ttu-id="945a1-124">ファイルエクスプローラーを開き、サンプルをインストールしたディレクトリの場所にある*WF_WCF_Samples\WCF\Setup\FindPrivateKey\CS*フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="945a1-124">Open File Explorer and navigate to the *WF_WCF_Samples\WCF\Setup\FindPrivateKey\CS* folder under the directory location where you installed the sample.</span></span>

2. <span data-ttu-id="945a1-125">.sln ファイルのアイコンをダブルクリックして、このファイルを Visual Studio で開きます。</span><span class="sxs-lookup"><span data-stu-id="945a1-125">Double-click the .sln file icon to open the file in Visual Studio.</span></span>

3. <span data-ttu-id="945a1-126">**[ビルド]** メニューの **[ソリューションのリビルド]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="945a1-126">In the **Build** menu, select **Rebuild Solution**.</span></span>

4. <span data-ttu-id="945a1-127">ソリューションをビルドすると、ファイルが生成されます。FindPrivateKey。</span><span class="sxs-lookup"><span data-stu-id="945a1-127">Building the solution generates the file: FindPrivateKey.exe.</span></span>

## <a name="conventionscommand-line-entries"></a><span data-ttu-id="945a1-128">規則-コマンドラインエントリ</span><span class="sxs-lookup"><span data-stu-id="945a1-128">Conventions—Command-Line entries</span></span>

 <span data-ttu-id="945a1-129">"[*option*]" は省略可能なパラメーターのセットを表します。</span><span class="sxs-lookup"><span data-stu-id="945a1-129">"[*option*]" represents an optional set of parameters.</span></span>

 <span data-ttu-id="945a1-130">"{*option*}" は、必須パラメーターのセットを表します。</span><span class="sxs-lookup"><span data-stu-id="945a1-130">"{*option*}" represents a mandatory set of parameters.</span></span>

 <span data-ttu-id="945a1-131">"*オプション 1* &#124; *option2*" は、オプションのセット間の選択を表します。</span><span class="sxs-lookup"><span data-stu-id="945a1-131">"*option1* &#124; *option2*" represents a choice between sets of options.</span></span>

 <span data-ttu-id="945a1-132">"\<*value*>" は、入力するパラメーター値を表します。</span><span class="sxs-lookup"><span data-stu-id="945a1-132">"\<*value*>" represents a parameter value to be entered.</span></span>

## <a name="usage"></a><span data-ttu-id="945a1-133">使用方法</span><span class="sxs-lookup"><span data-stu-id="945a1-133">Usage</span></span>

```console
FindPrivateKey <storeName> <storeLocation> [{ {-n <subjectName>} | {-t <thumbprint>} } [-f | -d | -a]]
```

<span data-ttu-id="945a1-134">この場合、</span><span class="sxs-lookup"><span data-stu-id="945a1-134">Where:</span></span>

| <span data-ttu-id="945a1-135">パラメーター</span><span class="sxs-lookup"><span data-stu-id="945a1-135">Parameter</span></span>         | <span data-ttu-id="945a1-136">説明</span><span class="sxs-lookup"><span data-stu-id="945a1-136">Description</span></span>                                                                       |
|-----------------|-----------------------------------------------------------------------------------|
| `<subjectName>` | <span data-ttu-id="945a1-137">証明書のサブジェクト名</span><span class="sxs-lookup"><span data-stu-id="945a1-137">The subject name of the certificate</span></span>                                               |
| `<thumbprint>`  | <span data-ttu-id="945a1-138">証明書のサムプリント (この検索には、Certmgr.exe ツールを使用できます)</span><span class="sxs-lookup"><span data-stu-id="945a1-138">The thumbprint of the certificate (You can use the Certmgr.exe tool to find this)</span></span> |
| `-f`            | <span data-ttu-id="945a1-139">出力ファイル名のみ</span><span class="sxs-lookup"><span data-stu-id="945a1-139">output file name only</span></span>                                                             |
| `-d`            | <span data-ttu-id="945a1-140">出力ディレクトリのみ</span><span class="sxs-lookup"><span data-stu-id="945a1-140">output directory only</span></span>                                                             |
| `-a`            | <span data-ttu-id="945a1-141">出力の絶対ファイル名</span><span class="sxs-lookup"><span data-stu-id="945a1-141">output absolute file name</span></span>                                                         |

<span data-ttu-id="945a1-142">コマンドプロンプトでパラメーターが指定されていない場合は、この情報を含むヘルプテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="945a1-142">If no parameters are specified at the command prompt, then help text with this information is displayed.</span></span>

## <a name="examples"></a><span data-ttu-id="945a1-143">使用例</span><span class="sxs-lookup"><span data-stu-id="945a1-143">Examples</span></span>

<span data-ttu-id="945a1-144">この例では、現在のユーザーの個人用ストアで、サブジェクト名が "CN = localhost" の証明書のファイル名を検索します。</span><span class="sxs-lookup"><span data-stu-id="945a1-144">This example finds the filename of the certificate with a subject name of "CN=localhost", in the Personal store of the Current User.</span></span>

```console
FindPrivateKey My CurrentUser -n "CN=localhost"
```

<span data-ttu-id="945a1-145">この例では、"CN = localhost" というサブジェクト名を持つ証明書のファイル名を現在のユーザーの個人用ストアに検索し、完全なディレクトリパスを出力します。</span><span class="sxs-lookup"><span data-stu-id="945a1-145">This example finds the filename of the certificate with a subject name of "CN=localhost", in the Personal store of the Current User and output the full directory path.</span></span>

```console
FindPrivateKey My CurrentUser -n "CN=localhost" -a
```

<span data-ttu-id="945a1-146">この例では、ローカル コンピューターの Personal ストアで、"03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52" というサムプリントを持つ証明書のファイル名を検索します。</span><span class="sxs-lookup"><span data-stu-id="945a1-146">This example finds the filename of the certificate with a thumbprint of "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52", in the Personal store of the Local Computer.</span></span>

```console
FindPrivateKey My LocalMachine -t "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52"
```
