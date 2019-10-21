---
title: '方法: 開発中に使用する一時的な証明書を作成する'
ms.date: 03/30/2017
helpviewer_keywords:
- certificates [WCF], creating temporary certificates
- temporary certificates [WCF]
ms.assetid: bc5f6637-5513-4d27-99bb-51aad7741e4a
ms.openlocfilehash: e2df35959f9821c65d694079aefa0ae6ba01897f
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053303"
---
# <a name="how-to-create-temporary-certificates-for-use-during-development"></a><span data-ttu-id="19344-102">方法: 開発中に使用する一時的な証明書を作成する</span><span class="sxs-lookup"><span data-stu-id="19344-102">How to: Create Temporary Certificates for Use During Development</span></span>

<span data-ttu-id="19344-103">Windows Communication Foundation (WCF) を使用してセキュリティで保護されたサービスまたはクライアントを開発する場合、資格情報として使用される x.509 証明書を指定することが必要になることがよくあります。</span><span class="sxs-lookup"><span data-stu-id="19344-103">When developing a secure service or client using Windows Communication Foundation (WCF), it is often necessary to supply an X.509 certificate to be used as a credential.</span></span> <span data-ttu-id="19344-104">証明書は通常、単独ではなく、いくつもの証明書が信頼チェーンとしてつながった形で存在しており、その最上位に位置するルート証明機関の証明書は、各コンピューターの [信頼されたルート証明機関] の証明書ストアに格納されています。</span><span class="sxs-lookup"><span data-stu-id="19344-104">The certificate typically is part of a chain of certificates with a root authority found in the Trusted Root Certification Authorities store of the computer.</span></span> <span data-ttu-id="19344-105">証明書を調べて順に信頼チェーンをたどっていくと、たとえば所属する会社や事業部門が運営する、ルート証明機関に到達します。</span><span class="sxs-lookup"><span data-stu-id="19344-105">Having a certificate chain enables you to scope a set of certificates where typically the root authority is from your organization or business unit.</span></span> <span data-ttu-id="19344-106">開発時にこの過程をエミュレートするためには、セキュリティ要件を満たす 2 種類の証明書を作る必要があります。</span><span class="sxs-lookup"><span data-stu-id="19344-106">To emulate this at development time, you can create two certificates to satisfy the security requirements.</span></span> <span data-ttu-id="19344-107">1 つは自己署名証明書で、[信頼されたルート証明機関] の証明書ストアに配置します。もう 1 つは、先の自己署名証明書を使って署名を施した証明書で、[ローカル コンピューター] の [個人] ストア、または [現在のユーザー] の [個人] ストアに配置します。</span><span class="sxs-lookup"><span data-stu-id="19344-107">The first is a self-signed certificate that is placed in the Trusted Root Certification Authorities store, and the second certificate is created from the first and is placed in either the Personal store of the Local Machine location, or the Personal store of the Current User location.</span></span> <span data-ttu-id="19344-108">このトピックでは、Powershell の[新しい SelfSignedCertificate](/powershell/module/pkiclient/new-selfsignedcertificate)コマンドレットを使用して、これら2つの証明書を作成する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="19344-108">This topic walks through the steps to create these two certificates using the Powershell [New-SelfSignedCertificate)](/powershell/module/pkiclient/new-selfsignedcertificate) cmdlet.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="19344-109">新しい SelfSignedCertificate コマンドレットによって生成される証明書は、テスト目的でのみ提供されます。</span><span class="sxs-lookup"><span data-stu-id="19344-109">The certificates that the New-SelfSignedCertificate cmdlet generates are provided for testing purposes only.</span></span> <span data-ttu-id="19344-110">実際にサービスやクライアントを業務に使用する際には、証明機関から取得した、適切な証明書が必要です。</span><span class="sxs-lookup"><span data-stu-id="19344-110">When deploying a service or client, be sure to use an appropriate certificate provided by a certification authority.</span></span> <span data-ttu-id="19344-111">これは、組織内の Windows Server 証明書サーバーまたはサードパーティのいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="19344-111">This could either be from a Windows Server certificate server in your organization or a third party.</span></span>
>
> <span data-ttu-id="19344-112">既定では、[新しい-SelfSignedCertificate](/powershell/module/pkiclient/new-selfsignedcertificate)コマンドレットは、自己署名の証明書を作成しますが、これらの証明書は安全ではありません。</span><span class="sxs-lookup"><span data-stu-id="19344-112">By default, the [New-SelfSignedCertificate](/powershell/module/pkiclient/new-selfsignedcertificate) cmdlet creates certificates that are self-signed and these certificates are insecure.</span></span> <span data-ttu-id="19344-113">自己署名証明書を信頼されたルート証明機関ストアに配置すると、展開環境をより厳密にシミュレートする開発環境を作成できます。</span><span class="sxs-lookup"><span data-stu-id="19344-113">Placing the self-signed certificates in the Trusted Root Certification Authorities store enables you to create a development environment that more closely simulates your deployment environment.</span></span>

 <span data-ttu-id="19344-114">証明書の作成と使用の詳細については、「[証明書の使用](working-with-certificates.md)使用」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19344-114">For more information about creating and using certificates, see [Working with Certificates](working-with-certificates.md).</span></span> <span data-ttu-id="19344-115">証明書を資格情報として使用する方法の詳細については、「[サービスおよびクライアントのセキュリティ保護](securing-services-and-clients.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19344-115">For more information about using a certificate as a credential, see [Securing Services and Clients](securing-services-and-clients.md).</span></span> <span data-ttu-id="19344-116">Microsoft Authenticode テクノロジの使用方法については、「 [Authenticode Overviews and Tutorials (Authenticode の概要とチュートリアル)](https://go.microsoft.com/fwlink/?LinkId=88919)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19344-116">For a tutorial about using Microsoft Authenticode technology, see [Authenticode Overviews and Tutorials](https://go.microsoft.com/fwlink/?LinkId=88919).</span></span>

## <a name="to-create-a-self-signed-root-authority-certificate-and-export-the-private-key"></a><span data-ttu-id="19344-117">自己署名ルート証明書を作成して秘密キーをエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="19344-117">To create a self-signed root authority certificate and export the private key</span></span>

<span data-ttu-id="19344-118">次のコマンドは、現在のユーザーの個人用ストアでサブジェクト名が "RootCA" の自己署名証明書を作成します。</span><span class="sxs-lookup"><span data-stu-id="19344-118">The following command creates a self-signed certificate with a subject name of "RootCA" in the Current User Personal store.</span></span>

```powershell
$rootcert = New-SelfSignedCertificate -CertStoreLocation Cert:\CurrentUser\My -DnsName "RootCA" -TextExtension @("2.5.29.19={text}CA=true") -KeyUsage CertSign,CrlSign,DigitalSignature
```

<span data-ttu-id="19344-119">証明書を PFX ファイルにエクスポートして、後の手順で必要な場所にインポートできるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="19344-119">We need to export the certificate to a PFX file so that it can be imported to where it's needed in a later step.</span></span> <span data-ttu-id="19344-120">証明書を秘密キーと共にエクスポートする場合は、パスワードを保護するためにパスワードが必要です。</span><span class="sxs-lookup"><span data-stu-id="19344-120">When exporting a certificate with the private key, a password is needed to protect it.</span></span> <span data-ttu-id="19344-121">パスワード`SecureString`をに保存し、 [get-pfxcertificate](/powershell/module/pkiclient/export-pfxcertificate)コマンドレットを使用して、関連付けられている秘密キーを持つ証明書を PFX ファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="19344-121">We save the password in a `SecureString` and use the [Export-PfxCertificate](/powershell/module/pkiclient/export-pfxcertificate) cmdlet to export the certificate with the associated private key to a PFX file.</span></span> <span data-ttu-id="19344-122">また、[証明書のエクスポート](/powershell/module/pkiclient/export-certificate)コマンドレットを使用して、公開証明書のみを CRT ファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="19344-122">We also save just the public certificate into a CRT file using the [Export-Certificate](/powershell/module/pkiclient/export-certificate) cmdlet.</span></span>

```powershell
[System.Security.SecureString]$rootcertPassword = ConvertTo-SecureString -String "password" -Force -AsPlainText
[String]$rootCertPath = Join-Path -Path 'cert:\CurrentUser\My\' -ChildPath "$($rootcert.Thumbprint)"
Export-PfxCertificate -Cert $rootCertPath -FilePath 'RootCA.pfx' -Password $rootcertPassword
Export-Certificate -Cert $rootCertPath -FilePath 'RootCA.crt'
```

## <a name="to-create-a-new-certificate-signed-by-a-root-authority-certificate"></a><span data-ttu-id="19344-123">ルート証明書によって署名された新しい証明書を作成するには</span><span class="sxs-lookup"><span data-stu-id="19344-123">To create a new certificate signed by a root authority certificate</span></span>

<span data-ttu-id="19344-124">発行者の秘密キーを使用して`RootCA` 、サブジェクト名が "signedbyrootca" で署名された証明書を作成するコマンドを次に示します。</span><span class="sxs-lookup"><span data-stu-id="19344-124">The following command creates a certificate signed by the `RootCA` with a subject name of "SignedByRootCA" using the private key of the issuer.</span></span>

```powershell
$testCert = New-SelfSignedCertificate -CertStoreLocation Cert:\LocalMachine\My -DnsName "SignedByRootCA" -KeyExportPolicy Exportable -KeyLength 2048 -KeyUsage DigitalSignature,KeyEncipherment -Signer $rootCert
```

<span data-ttu-id="19344-125">同様に、秘密キーを含む署名入り証明書を PFX ファイルに保存し、公開キーだけを CRT ファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="19344-125">Similarly, we save the signed certificate with private key into a PFX file and just the public key into a CRT file.</span></span>

```powershell
[String]$testCertPath = Join-Path -Path 'cert:\LocalMachine\My\' -ChildPath "$($testCert.Thumbprint)"
Export-PfxCertificate -Cert $testCertPath -FilePath testcert.pfx -Password $rootcertPassword
Export-Certificate -Cert $testCertPath -FilePath testcert.crt
```

## <a name="installing-a-certificate-in-the-trusted-root-certification-authorities-store"></a><span data-ttu-id="19344-126">信頼されたルート証明機関の証明書ストアに証明書をインストールする</span><span class="sxs-lookup"><span data-stu-id="19344-126">Installing a Certificate in the Trusted Root Certification Authorities Store</span></span>

<span data-ttu-id="19344-127">作成された自己署名証明書は、[信頼されたルート証明機関] の証明書ストアにインストールできます。</span><span class="sxs-lookup"><span data-stu-id="19344-127">Once a self-signed certificate is created, you can install it in the Trusted Root Certification Authorities store.</span></span> <span data-ttu-id="19344-128">この証明書で署名された証明書は、この時点で信頼できるものと見なされるようになります。</span><span class="sxs-lookup"><span data-stu-id="19344-128">Any certificates that are signed with the certificate at this point are trusted by the computer.</span></span> <span data-ttu-id="19344-129">したがって、この証明書が不要になった場合は、直ちに証明書ストアから削除してください。</span><span class="sxs-lookup"><span data-stu-id="19344-129">For this reason, delete the certificate from the store as soon as you no longer need it.</span></span> <span data-ttu-id="19344-130">この証明書を削除すると、それを使って署名した証明書は認証されなくなります。</span><span class="sxs-lookup"><span data-stu-id="19344-130">When you delete this root authority certificate, all other certificates that signed with it become unauthorized.</span></span> <span data-ttu-id="19344-131">ルート証明機関の証明書は、必要に応じて一連の証明書を有効化する手段の 1 つにすぎません。</span><span class="sxs-lookup"><span data-stu-id="19344-131">Root authority certificates are simply a mechanism whereby a group of certificates can be scoped as necessary.</span></span> <span data-ttu-id="19344-132">たとえばピアツーピア アプリケーションの場合、証明書が提示されれば相手の識別情報を信頼できるので、ルート証明機関は必要ないのが普通です。</span><span class="sxs-lookup"><span data-stu-id="19344-132">For example, in peer-to-peer applications, there is typically no need for a root authority because you simply trust the identity of an individual by its supplied certificate.</span></span>

### <a name="to-install-a-self-signed-certificate-in-the-trusted-root-certification-authorities"></a><span data-ttu-id="19344-133">自己署名証明書を信頼されたルート証明機関としてインストールするには</span><span class="sxs-lookup"><span data-stu-id="19344-133">To install a self-signed certificate in the Trusted Root Certification Authorities</span></span>

1. <span data-ttu-id="19344-134">証明書スナップインを開きます。</span><span class="sxs-lookup"><span data-stu-id="19344-134">Open the certificate snap-in.</span></span> <span data-ttu-id="19344-135">詳細については、「[方法 :MMC スナップ](how-to-view-certificates-with-the-mmc-snap-in.md)インを使用して証明書を表示します。</span><span class="sxs-lookup"><span data-stu-id="19344-135">For more information, see [How to: View Certificates with the MMC Snap-in](how-to-view-certificates-with-the-mmc-snap-in.md).</span></span>

2. <span data-ttu-id="19344-136">証明書の格納先となる、 **[ローカル コンピューター]** または **[現在のユーザー]** のフォルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="19344-136">Open the folder to store the certificate, either the **Local Computer** or the **Current User**.</span></span>

3. <span data-ttu-id="19344-137">**[信頼されたルート証明機関]** フォルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="19344-137">Open the **Trusted Root Certification Authorities** folder.</span></span>

4. <span data-ttu-id="19344-138">**[証明書]** フォルダーを右クリックして、 **[すべてのタスク]** メニューの **[インポート]** を実行します。</span><span class="sxs-lookup"><span data-stu-id="19344-138">Right-click the **Certificates** folder and click **All Tasks**, then click **Import**.</span></span>

5. <span data-ttu-id="19344-139">画面に表示されるウィザードの指示に従って、RootCA .pfx をストアにインポートします。</span><span class="sxs-lookup"><span data-stu-id="19344-139">Follow the on-screen wizard instructions to import the RootCA.pfx into the store.</span></span>

## <a name="using-certificates-with-wcf"></a><span data-ttu-id="19344-140">WCF での証明書の使用</span><span class="sxs-lookup"><span data-stu-id="19344-140">Using certificates With WCF</span></span>

<span data-ttu-id="19344-141">一時的な証明書を設定したら、それを使用して、クライアント資格情報の種類として証明書を指定する WCF ソリューションを開発できます。</span><span class="sxs-lookup"><span data-stu-id="19344-141">Once you have set up the temporary certificates, you can use them to develop WCF solutions that specify certificates as a client credential type.</span></span> <span data-ttu-id="19344-142">たとえば、次の XML 構成では、メッセージ セキュリティを設定して、クライアント資格情報の種類として証明書を指定しています。</span><span class="sxs-lookup"><span data-stu-id="19344-142">For example, the following XML configuration specifies message security and a certificate as the client credential type.</span></span>

### <a name="to-specify-a-certificate-as-the-client-credential-type"></a><span data-ttu-id="19344-143">クライアント資格情報の種類として証明書を指定するには</span><span class="sxs-lookup"><span data-stu-id="19344-143">To specify a certificate as the client credential type</span></span>

1. <span data-ttu-id="19344-144">サービスの構成ファイルで、次の XML を使用して、セキュリティ モードをメッセージに、クライアント資格情報の種類を証明書に設定します。</span><span class="sxs-lookup"><span data-stu-id="19344-144">In the configuration file for a service, use the following XML to set the security mode to message, and the client credential type to certificate.</span></span>

    ```xml
    <bindings>
      <wsHttpBinding>
        <binding name="CertificateForClient">
          <security>
            <message clientCredentialType="Certificate" />
          </security>
        </binding>
      </wsHttpBinding>
    </bindings>
    ```

2. <span data-ttu-id="19344-145">クライアントの構成ファイルで、次の XML を使用して、証明書がユーザーのストアに存在することを指定します。また、SubjectName フィールドで値 "CohoWinery" を検索して見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="19344-145">In the configuration file for a client, use the following XML to specify that the certificate is found in the user’s store, and can be found by searching the SubjectName field for the value "CohoWinery."</span></span>

    ```xml
    <behaviors>
      <endpointBehaviors>
        <behavior name="CertForClient">
          <clientCredentials>
            <clientCertificate findValue="CohoWinery" x509FindType="FindBySubjectName" />
          </clientCredentials>
        </behavior>
      </endpointBehaviors>
    </behaviors>
    ```

<span data-ttu-id="19344-146">WCF での証明書の使用に関する詳細については、「 [証明書の使用](working-with-certificates.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19344-146">For more information about using certificates in WCF, see [Working with Certificates](working-with-certificates.md).</span></span>

## <a name="net-framework-security"></a><span data-ttu-id="19344-147">.NET Framework のセキュリティ</span><span class="sxs-lookup"><span data-stu-id="19344-147">.NET Framework security</span></span>

<span data-ttu-id="19344-148">一時的なルート証明書は、不要になったら **[信頼されたルート証明機関]** フォルダーや **[個人]** フォルダーから確実に削除してください。削除するには、証明書を右クリックし、 **[削除]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="19344-148">Be sure to delete any temporary root authority certificates from the **Trusted Root Certification Authorities** and **Personal** folders by right-clicking the certificate, then clicking **Delete**.</span></span>

## <a name="see-also"></a><span data-ttu-id="19344-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="19344-149">See also</span></span>

- [<span data-ttu-id="19344-150">証明書の使用</span><span class="sxs-lookup"><span data-stu-id="19344-150">Working with Certificates</span></span>](working-with-certificates.md)
- [<span data-ttu-id="19344-151">方法: MMC スナップインを使用して証明書を表示する</span><span class="sxs-lookup"><span data-stu-id="19344-151">How to: View Certificates with the MMC Snap-in</span></span>](how-to-view-certificates-with-the-mmc-snap-in.md)
- [<span data-ttu-id="19344-152">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="19344-152">Securing Services and Clients</span></span>](securing-services-and-clients.md)
