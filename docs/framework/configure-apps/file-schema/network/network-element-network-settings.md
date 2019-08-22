---
title: <network> 要素 (ネットワーク設定)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#network
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp/network
helpviewer_keywords:
- <network> element
- network element
ms.assetid: 2c2c6ad4-ed11-48ab-b28e-2bc0ba9b42c7
ms.openlocfilehash: 40d89f7bd7a1f4a38a1c4030a86405e09c497899
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659316"
---
# <a name="network-element-network-settings"></a><span data-ttu-id="d6168-102">\<network > 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="d6168-102">\<network> Element (Network Settings)</span></span>
<span data-ttu-id="d6168-103">外部の簡易メール転送プロトコル (SMTP) サーバーのネットワークオプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="d6168-103">Configures the network options for an external Simple Mail Transport Protocol (SMTP) server.</span></span>  
  
 <span data-ttu-id="d6168-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="d6168-104">\<configuration></span></span>  
<span data-ttu-id="d6168-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="d6168-105">\<system.net></span></span>  
<span data-ttu-id="d6168-106">\<mailSettings></span><span class="sxs-lookup"><span data-stu-id="d6168-106">\<mailSettings></span></span>  
<span data-ttu-id="d6168-107">\<smtp></span><span class="sxs-lookup"><span data-stu-id="d6168-107">\<smtp></span></span>  
<span data-ttu-id="d6168-108">\<network></span><span class="sxs-lookup"><span data-stu-id="d6168-108">\<network></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6168-109">構文</span><span class="sxs-lookup"><span data-stu-id="d6168-109">Syntax</span></span>  
  
```xml  
<network  
  clientDomain="string"   
  defaultCredentials="true|false"  
  enableSsl="true|false"  
  host="string"   
  password="string"  
  port="integer"   
  targetName="string"  
  userName="string"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d6168-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="d6168-110">Attributes and Elements</span></span>  
 <span data-ttu-id="d6168-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="d6168-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d6168-112">属性</span><span class="sxs-lookup"><span data-stu-id="d6168-112">Attributes</span></span>  
  
|<span data-ttu-id="d6168-113">属性</span><span class="sxs-lookup"><span data-stu-id="d6168-113">Attribute</span></span>|<span data-ttu-id="d6168-114">説明</span><span class="sxs-lookup"><span data-stu-id="d6168-114">Description</span></span>|  
|---------------|-----------------|  
|`clientDomain`|<span data-ttu-id="d6168-115">SMTP メールサーバーに接続するための最初の SMTP プロトコル要求で使用するクライアントドメイン名を指定します。</span><span class="sxs-lookup"><span data-stu-id="d6168-115">Specifies the client domain name to use in the initial SMTP protocol request to connect to the SMTP mail server.</span></span> <span data-ttu-id="d6168-116">既定値は、要求を送信しているローカルコンピューターの localhost 名です。</span><span class="sxs-lookup"><span data-stu-id="d6168-116">The default value is the localhost name of the local computer sending the request.</span></span>|  
|`defaultCredentials`|<span data-ttu-id="d6168-117">Smtp トランザクションの SMTP メールサーバーへのアクセスに、既定のユーザー資格情報を使用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="d6168-117">Specifies whether the default user credentials should be used to access the SMTP mail server for SMTP transactions.</span></span> <span data-ttu-id="d6168-118">既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="d6168-118">The default value is `false`.</span></span>|  
|`enableSsl`|<span data-ttu-id="d6168-119">SMTP メールサーバーへのアクセスに SSL を使用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="d6168-119">Specifies whether SSL is used to access an SMTP mail server.</span></span> <span data-ttu-id="d6168-120">既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="d6168-120">The default value is `false`.</span></span>|  
|`host`|<span data-ttu-id="d6168-121">SMTP トランザクションに使用する SMTP メールサーバーのホスト名を指定します。</span><span class="sxs-lookup"><span data-stu-id="d6168-121">Specifies the hostname of the SMTP mail server to use for SMTP transactions.</span></span> <span data-ttu-id="d6168-122">この属性には既定値はありません。</span><span class="sxs-lookup"><span data-stu-id="d6168-122">This attribute has no default value.</span></span>|  
|`password`|<span data-ttu-id="d6168-123">SMTP メールサーバーへの認証に使用するパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="d6168-123">Specifies the password to use for authentication to the SMTP mail server.</span></span> <span data-ttu-id="d6168-124">この属性には既定値はありません。</span><span class="sxs-lookup"><span data-stu-id="d6168-124">This attribute has no default value.</span></span>|  
|`port`|<span data-ttu-id="d6168-125">SMTP メールサーバーへの接続に使用するポート番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="d6168-125">Specifies the port number to use to connect to the SMTP mail server.</span></span> <span data-ttu-id="d6168-126">既定値は、25 です。</span><span class="sxs-lookup"><span data-stu-id="d6168-126">The default value is 25.</span></span>|  
|`targetName`|<span data-ttu-id="d6168-127">SMTP トランザクションの拡張保護を使用するときに認証に使用するサービスプロバイダー名 (SPN) を指定します。</span><span class="sxs-lookup"><span data-stu-id="d6168-127">Specifies the Service Provider Name (SPN) to use for authentication when using extended protection for SMTP transactions.</span></span> <span data-ttu-id="d6168-128">この属性には既定値はありません。</span><span class="sxs-lookup"><span data-stu-id="d6168-128">This attribute has no default value.</span></span>|  
|`userName`|<span data-ttu-id="d6168-129">SMTP メールサーバーへの認証に使用するユーザー名を指定します。</span><span class="sxs-lookup"><span data-stu-id="d6168-129">Specifies the user name to use for authentication to the SMTP mail server.</span></span> <span data-ttu-id="d6168-130">この属性には既定値はありません。</span><span class="sxs-lookup"><span data-stu-id="d6168-130">This attribute has no default value.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d6168-131">子要素</span><span class="sxs-lookup"><span data-stu-id="d6168-131">Child Elements</span></span>  
 <span data-ttu-id="d6168-132">なし。</span><span class="sxs-lookup"><span data-stu-id="d6168-132">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d6168-133">親要素</span><span class="sxs-lookup"><span data-stu-id="d6168-133">Parent Elements</span></span>  
  
|<span data-ttu-id="d6168-134">要素</span><span class="sxs-lookup"><span data-stu-id="d6168-134">Element</span></span>|<span data-ttu-id="d6168-135">説明</span><span class="sxs-lookup"><span data-stu-id="d6168-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d6168-136">\<smtp> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="d6168-136">\<smtp> Element (Network Settings)</span></span>](smtp-element-network-settings.md)|<span data-ttu-id="d6168-137">簡易メール転送プロトコル (SMTP) 電子メールの送信オプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="d6168-137">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d6168-138">Remarks</span><span class="sxs-lookup"><span data-stu-id="d6168-138">Remarks</span></span>  
 <span data-ttu-id="d6168-139">一部の SMTP サーバーでは、使用する前にサーバーに対して認証を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6168-139">Some SMTP servers require that you authenticate yourself to the server before use.</span></span> <span data-ttu-id="d6168-140">ホストで既定のネットワーク資格情報を使用して認証する場合は、 `defaultCredentials`属性をに`true`設定します。</span><span class="sxs-lookup"><span data-stu-id="d6168-140">If you want to authenticate yourself using the default network credentials on your host, set the `defaultCredentials` attribute to `true`.</span></span> <span data-ttu-id="d6168-141">プロパティ<xref:System.Net.Configuration.SmtpNetworkElement.DefaultCredentials%2A?displayProperty=nameWithType>は、適用可能`defaultCredentials`な構成ファイルから属性の現在の値を取得するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="d6168-141">The <xref:System.Net.Configuration.SmtpNetworkElement.DefaultCredentials%2A?displayProperty=nameWithType> property can be used to get the current value of the `defaultCredentials` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="d6168-142">基本認証 (ユーザー名とパスワード) を使用して、SMTP サーバーに対する認証を行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="d6168-142">You can also use basic authentication (a user name and password) to authenticate yourself to the SMTP server.</span></span> <span data-ttu-id="d6168-143">このオプションを使用するには、指定した SMTP サーバーの有効なユーザー名とパスワードを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6168-143">To use this option, you must specify a valid user name and password for the specified SMTP server.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d6168-144">基本認証は、 `userName`および`password`の値を暗号化せずにサーバーに送信します。</span><span class="sxs-lookup"><span data-stu-id="d6168-144">Basic authentication sends the `userName` and `password` values to the server unencrypted.</span></span> <span data-ttu-id="d6168-145">ネットワークトラフィックを監視するすべてのユーザーは、資格情報を表示し、それらを使用してサーバーに接続できます。</span><span class="sxs-lookup"><span data-stu-id="d6168-145">Anyone monitoring network traffic can view your credentials and use them to connect to the server.</span></span> <span data-ttu-id="d6168-146">Kerberos や NT LAN Manager (NTLM) など、より安全な認証メカニズムの使用を検討する必要があります。`defaultCredentials` が`true`の場合、サーバーがこれらのプロトコルをサポートする場合、Kerberos または NTLM が使用されます。</span><span class="sxs-lookup"><span data-stu-id="d6168-146">You should consider using a more secure authentication mechanism, such as Kerberos or NT LAN Manager (NTLM.) If `defaultCredentials` is `true`, Kerberos or NTLM will be used if the server supports these protocols.</span></span>  
  
 <span data-ttu-id="d6168-147">基本認証および既定のネットワーク資格情報オプションは、同時には指定できません。をに`defaultCredentials` `true`設定し、ユーザー名とパスワードを指定した場合、既定のネットワーク資格情報が使用され、基本認証データは無視されます。</span><span class="sxs-lookup"><span data-stu-id="d6168-147">The basic authentication and default network credentials options are mutually exclusive; if you set `defaultCredentials` to `true` and specify a user name and password, the default network credential is used, and the basic authentication data is ignored.</span></span>  
  
 <span data-ttu-id="d6168-148">基本認証でを指定`userName`する場合は、メールサーバーに対して自分で認証`password`を行うようにを指定する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="d6168-148">For basic authentication if you specify a `userName`, you should also specify a `password` to authentication yourself to the mail server.</span></span>  
  
 <span data-ttu-id="d6168-149">プロパティ<xref:System.Net.Configuration.SmtpNetworkElement.UserName%2A?displayProperty=nameWithType>は、適用可能`userName`な構成ファイルから属性の現在の値を取得するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="d6168-149">The <xref:System.Net.Configuration.SmtpNetworkElement.UserName%2A?displayProperty=nameWithType> property can be used to get the current value of the `userName` attribute from applicable configuration files.</span></span> <span data-ttu-id="d6168-150">プロパティ<xref:System.Net.Configuration.SmtpNetworkElement.Password%2A?displayProperty=nameWithType>は、適用可能`password`な構成ファイルから属性の現在の値を取得するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="d6168-150">The <xref:System.Net.Configuration.SmtpNetworkElement.Password%2A?displayProperty=nameWithType> property can be used to get the current value of the `password` attribute from applicable configuration files.</span></span> <span data-ttu-id="d6168-151">通常`password` 、セキュリティ上の理由から、属性を構成ファイルに入力することはできません。</span><span class="sxs-lookup"><span data-stu-id="d6168-151">A `password` attribute would not normally be entered in configuration files for security reasons.</span></span>  
  
 <span data-ttu-id="d6168-152">属性`clientDomain`は、smtp プロトコルの初期要求で使用されるクライアントのドメイン名を smtp サーバーに変更します。</span><span class="sxs-lookup"><span data-stu-id="d6168-152">The `clientDomain` attribute changes the client domain name used in the initial SMTP protocol request to an SMTP server.</span></span> <span data-ttu-id="d6168-153">属性`clientDomain`は、既定で使用される localhost 名ではなく、ローカルコンピューターの完全修飾ドメイン名に設定できます。</span><span class="sxs-lookup"><span data-stu-id="d6168-153">The `clientDomain` attribute can be set to the fully-qualified domain name of the local machine, rather than the localhost name that is used by default.</span></span> <span data-ttu-id="d6168-154">これにより、SMTP プロトコル標準への準拠が向上します。</span><span class="sxs-lookup"><span data-stu-id="d6168-154">This provides greater compliance with the SMTP protocol standards.</span></span> <span data-ttu-id="d6168-155">既定値は、要求を送信しているローカルコンピューターの localhost 名です。</span><span class="sxs-lookup"><span data-stu-id="d6168-155">The default value is the localhost name of the local computer sending the request.</span></span> <span data-ttu-id="d6168-156">プロパティ<xref:System.Net.Configuration.SmtpNetworkElement.ClientDomain%2A?displayProperty=nameWithType>は、適用可能`clientDomain`な構成ファイルから属性の現在の値を取得するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="d6168-156">The <xref:System.Net.Configuration.SmtpNetworkElement.ClientDomain%2A?displayProperty=nameWithType> property can be used to get the current value of the `clientDomain` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="d6168-157">拡張`targetName`保護を使用する場合、この属性は認証に使用されます。</span><span class="sxs-lookup"><span data-stu-id="d6168-157">The `targetName` attribute is used for authentication when using extended protection.</span></span> <span data-ttu-id="d6168-158">既定値は "SMTPSVC/\<host >" の形式です。ここ\<で、host > は SMTP メールサーバーのホスト名です。</span><span class="sxs-lookup"><span data-stu-id="d6168-158">The default value is of the form "SMTPSVC/\<host>" where \<host> is the hostname of the SMTP mail server.</span></span> <span data-ttu-id="d6168-159">プロパティ<xref:System.Net.Configuration.SmtpNetworkElement.TargetName%2A?displayProperty=nameWithType>は、適用可能`targetName`な構成ファイルから属性の現在の値を取得するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="d6168-159">The <xref:System.Net.Configuration.SmtpNetworkElement.TargetName%2A?displayProperty=nameWithType> property can be used to get the current value of the `targetName` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="d6168-160">属性`enableSsl`では、SMTP メールサーバーへのアクセスに SSL を使用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="d6168-160">The `enableSsl` attribute specifies whether SSL is used to access an SMTP mail server.</span></span> <span data-ttu-id="d6168-161"><xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>クラスでサポートされているのは、RFC 3207 で定義されているトランスポート層セキュリティ経由の Secure smtp に対する smtp サービス拡張のみです。</span><span class="sxs-lookup"><span data-stu-id="d6168-161">The <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType> class only supports the SMTP Service Extension for Secure SMTP over Transport Layer Security as defined in RFC 3207.</span></span> <span data-ttu-id="d6168-162">このモードでは、暗号化されていないチャネルで SMTP セッションが開始され、SSL を使用してセキュリティで保護された通信に切り替えるために、クライアントからサーバーに STARTTLS コマンドが発行されます。</span><span class="sxs-lookup"><span data-stu-id="d6168-162">In this mode, the SMTP session begins on an unencrypted channel, then a STARTTLS command is issued by the client to the server to switch to secure communication using SSL.</span></span> <span data-ttu-id="d6168-163">詳細については、インターネット技術標準化委員会 (IETF) によって発行された RFC 3207 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6168-163">See RFC 3207 published by the Internet Engineering Task Force (IETF) for more information.</span></span>  
  
 <span data-ttu-id="d6168-164">代替の接続方法では、プロトコルコマンドが送信される前に、SSL セッションが事前に確立されます。</span><span class="sxs-lookup"><span data-stu-id="d6168-164">An alternate connection method is where an SSL session is established up front before any protocol commands are sent.</span></span> <span data-ttu-id="d6168-165">この接続方法は SMTPS とも呼ばれ、既定ではポート465を使用します。</span><span class="sxs-lookup"><span data-stu-id="d6168-165">This connection method is sometimes called SMTPS and by default uses port 465.</span></span> <span data-ttu-id="d6168-166">SSL を使用したこの代替接続方法は、現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="d6168-166">This alternate connection method using SSL is not currently supported.</span></span>  
  
 <span data-ttu-id="d6168-167">プロパティ<xref:System.Net.Configuration.SmtpNetworkElement.EnableSsl%2A?displayProperty=nameWithType>は、適用可能`enableSsl`な構成ファイルから属性の現在の値を取得するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="d6168-167">The <xref:System.Net.Configuration.SmtpNetworkElement.EnableSsl%2A?displayProperty=nameWithType> property can be used to get the current value of the `enableSsl` attribute from applicable configuration files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d6168-168">例</span><span class="sxs-lookup"><span data-stu-id="d6168-168">Example</span></span>  
 <span data-ttu-id="d6168-169">次の例では、既定のネットワーク資格情報を使用して電子メールを送信するための適切な SMTP パラメーターを指定しています。</span><span class="sxs-lookup"><span data-stu-id="d6168-169">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="Network">  
        <network  
          clientDomain="www.contoso.com"  
          defaultCredentials="true"  
          enableSsl="false"  
          host="mail.contoso.com"  
          port="25"  
        />  
      </smtp>  
    </mailSettings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d6168-170">関連項目</span><span class="sxs-lookup"><span data-stu-id="d6168-170">See also</span></span>

- <xref:System.Net.Configuration.SmtpNetworkElement?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- [<span data-ttu-id="d6168-171">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="d6168-171">Network Settings Schema</span></span>](index.md)
