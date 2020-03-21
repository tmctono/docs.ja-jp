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
ms.openlocfilehash: f7cfcc3b9d5a717c23175cd15aa48ae97c828e57
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154817"
---
# <a name="network-element-network-settings"></a><span data-ttu-id="99c36-102">\<ネットワーク>要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="99c36-102">\<network> Element (Network Settings)</span></span>
<span data-ttu-id="99c36-103">外部簡易メール転送プロトコル (SMTP) サーバーのネットワーク オプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="99c36-103">Configures the network options for an external Simple Mail Transport Protocol (SMTP) server.</span></span>  

<span data-ttu-id="99c36-104">[**\<構成>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="99c36-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="99c36-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="99c36-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="99c36-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<メール設定>**](mailsettings-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="99c36-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)</span></span>\
<span data-ttu-id="99c36-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<smtp>**](smtp-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="99c36-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<smtp>**](smtp-element-network-settings.md)</span></span>\
<span data-ttu-id="99c36-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<ネットワーク>**</span><span class="sxs-lookup"><span data-stu-id="99c36-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<network>**</span></span>

## <a name="syntax"></a><span data-ttu-id="99c36-109">構文</span><span class="sxs-lookup"><span data-stu-id="99c36-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="99c36-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="99c36-110">Attributes and Elements</span></span>  
 <span data-ttu-id="99c36-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="99c36-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="99c36-112">属性</span><span class="sxs-lookup"><span data-stu-id="99c36-112">Attributes</span></span>  
  
|<span data-ttu-id="99c36-113">属性</span><span class="sxs-lookup"><span data-stu-id="99c36-113">Attribute</span></span>|<span data-ttu-id="99c36-114">説明</span><span class="sxs-lookup"><span data-stu-id="99c36-114">Description</span></span>|  
|---------------|-----------------|  
|`clientDomain`|<span data-ttu-id="99c36-115">SMTP メール サーバーに接続するために最初の SMTP プロトコル要求で使用するクライアント ドメイン名を指定します。</span><span class="sxs-lookup"><span data-stu-id="99c36-115">Specifies the client domain name to use in the initial SMTP protocol request to connect to the SMTP mail server.</span></span> <span data-ttu-id="99c36-116">既定値は、要求を送信するローカル コンピューターのローカル ホスト名です。</span><span class="sxs-lookup"><span data-stu-id="99c36-116">The default value is the localhost name of the local computer sending the request.</span></span>|  
|`defaultCredentials`|<span data-ttu-id="99c36-117">SMTP トランザクションの SMTP メール サーバーにアクセスするために既定のユーザー資格情報を使用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="99c36-117">Specifies whether the default user credentials should be used to access the SMTP mail server for SMTP transactions.</span></span> <span data-ttu-id="99c36-118">既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="99c36-118">The default value is `false`.</span></span>|  
|`enableSsl`|<span data-ttu-id="99c36-119">SMTP メール サーバーへのアクセスに SSL を使用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="99c36-119">Specifies whether SSL is used to access an SMTP mail server.</span></span> <span data-ttu-id="99c36-120">既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="99c36-120">The default value is `false`.</span></span>|  
|`host`|<span data-ttu-id="99c36-121">SMTP トランザクションに使用する SMTP メール サーバーのホスト名を指定します。</span><span class="sxs-lookup"><span data-stu-id="99c36-121">Specifies the hostname of the SMTP mail server to use for SMTP transactions.</span></span> <span data-ttu-id="99c36-122">この属性には既定値はありません。</span><span class="sxs-lookup"><span data-stu-id="99c36-122">This attribute has no default value.</span></span>|  
|`password`|<span data-ttu-id="99c36-123">SMTP メール サーバーへの認証に使用するパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="99c36-123">Specifies the password to use for authentication to the SMTP mail server.</span></span> <span data-ttu-id="99c36-124">この属性には既定値はありません。</span><span class="sxs-lookup"><span data-stu-id="99c36-124">This attribute has no default value.</span></span>|  
|`port`|<span data-ttu-id="99c36-125">SMTP メール サーバーへの接続に使用するポート番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="99c36-125">Specifies the port number to use to connect to the SMTP mail server.</span></span> <span data-ttu-id="99c36-126">既定値は 25 です。</span><span class="sxs-lookup"><span data-stu-id="99c36-126">The default value is 25.</span></span>|  
|`targetName`|<span data-ttu-id="99c36-127">SMTP トランザクションに拡張保護を使用する場合に認証に使用するサービス プロバイダー名 (SPN) を指定します。</span><span class="sxs-lookup"><span data-stu-id="99c36-127">Specifies the Service Provider Name (SPN) to use for authentication when using extended protection for SMTP transactions.</span></span> <span data-ttu-id="99c36-128">この属性には既定値はありません。</span><span class="sxs-lookup"><span data-stu-id="99c36-128">This attribute has no default value.</span></span>|  
|`userName`|<span data-ttu-id="99c36-129">SMTP メール サーバーへの認証に使用するユーザー名を指定します。</span><span class="sxs-lookup"><span data-stu-id="99c36-129">Specifies the user name to use for authentication to the SMTP mail server.</span></span> <span data-ttu-id="99c36-130">この属性には既定値はありません。</span><span class="sxs-lookup"><span data-stu-id="99c36-130">This attribute has no default value.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="99c36-131">子要素</span><span class="sxs-lookup"><span data-stu-id="99c36-131">Child Elements</span></span>  
 <span data-ttu-id="99c36-132">[なし] :</span><span class="sxs-lookup"><span data-stu-id="99c36-132">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="99c36-133">親要素</span><span class="sxs-lookup"><span data-stu-id="99c36-133">Parent Elements</span></span>  
  
|<span data-ttu-id="99c36-134">要素</span><span class="sxs-lookup"><span data-stu-id="99c36-134">Element</span></span>|<span data-ttu-id="99c36-135">説明</span><span class="sxs-lookup"><span data-stu-id="99c36-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="99c36-136">\<smtp>要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="99c36-136">\<smtp> Element (Network Settings)</span></span>](smtp-element-network-settings.md)|<span data-ttu-id="99c36-137">簡易メール転送プロトコル (SMTP) メール送信オプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="99c36-137">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="99c36-138">解説</span><span class="sxs-lookup"><span data-stu-id="99c36-138">Remarks</span></span>  
 <span data-ttu-id="99c36-139">一部の SMTP サーバーでは、使用する前にサーバーに対して自分自身を認証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="99c36-139">Some SMTP servers require that you authenticate yourself to the server before use.</span></span> <span data-ttu-id="99c36-140">ホストのデフォルトのネットワーク資格情報を使用して自分自身を認証する場合は、属性を`defaultCredentials`に`true`設定します。</span><span class="sxs-lookup"><span data-stu-id="99c36-140">If you want to authenticate yourself using the default network credentials on your host, set the `defaultCredentials` attribute to `true`.</span></span> <span data-ttu-id="99c36-141">この<xref:System.Net.Configuration.SmtpNetworkElement.DefaultCredentials%2A?displayProperty=nameWithType>プロパティを使用して、適用可能な構成ファイルから`defaultCredentials`属性の現在の値を取得できます。</span><span class="sxs-lookup"><span data-stu-id="99c36-141">The <xref:System.Net.Configuration.SmtpNetworkElement.DefaultCredentials%2A?displayProperty=nameWithType> property can be used to get the current value of the `defaultCredentials` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="99c36-142">基本認証 (ユーザー名とパスワード) を使用して、SMTP サーバーに対して自分自身を認証することもできます。</span><span class="sxs-lookup"><span data-stu-id="99c36-142">You can also use basic authentication (a user name and password) to authenticate yourself to the SMTP server.</span></span> <span data-ttu-id="99c36-143">このオプションを使用するには、指定した SMTP サーバーの有効なユーザー名とパスワードを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="99c36-143">To use this option, you must specify a valid user name and password for the specified SMTP server.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="99c36-144">基本認証では、 `userName` `password`と の値が暗号化されずにサーバーに送信されます。</span><span class="sxs-lookup"><span data-stu-id="99c36-144">Basic authentication sends the `userName` and `password` values to the server unencrypted.</span></span> <span data-ttu-id="99c36-145">ネットワーク トラフィックを監視しているユーザーは誰でも、資格情報を表示して、サーバーに接続するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="99c36-145">Anyone monitoring network traffic can view your credentials and use them to connect to the server.</span></span> <span data-ttu-id="99c36-146">Kerberos や NT LAN マネージャ (NTLM) など、より安全な認証メカニズムの使用を検討する必要があります。が`defaultCredentials`設定`true`されている場合、サーバーがこれらのプロトコルをサポートしている場合は、Kerberos または NTLM が使用されます。</span><span class="sxs-lookup"><span data-stu-id="99c36-146">You should consider using a more secure authentication mechanism, such as Kerberos or NT LAN Manager (NTLM.) If `defaultCredentials` is `true`, Kerberos or NTLM will be used if the server supports these protocols.</span></span>  
  
 <span data-ttu-id="99c36-147">基本認証と既定のネットワーク資格情報のオプションは相互に排他的です。ユーザー名と`defaultCredentials`パスワード`true`を指定して設定すると、デフォルトのネットワーク資格情報が使用され、基本認証データは無視されます。</span><span class="sxs-lookup"><span data-stu-id="99c36-147">The basic authentication and default network credentials options are mutually exclusive; if you set `defaultCredentials` to `true` and specify a user name and password, the default network credential is used, and the basic authentication data is ignored.</span></span>  
  
 <span data-ttu-id="99c36-148">基本認証の 場合は`userName`、 を指定する場合は`password`、メール サーバーに対する認証を自分で指定する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="99c36-148">For basic authentication if you specify a `userName`, you should also specify a `password` to authentication yourself to the mail server.</span></span>  
  
 <span data-ttu-id="99c36-149">この<xref:System.Net.Configuration.SmtpNetworkElement.UserName%2A?displayProperty=nameWithType>プロパティを使用して、適用可能な構成ファイルから`userName`属性の現在の値を取得できます。</span><span class="sxs-lookup"><span data-stu-id="99c36-149">The <xref:System.Net.Configuration.SmtpNetworkElement.UserName%2A?displayProperty=nameWithType> property can be used to get the current value of the `userName` attribute from applicable configuration files.</span></span> <span data-ttu-id="99c36-150">この<xref:System.Net.Configuration.SmtpNetworkElement.Password%2A?displayProperty=nameWithType>プロパティを使用して、適用可能な構成ファイルから`password`属性の現在の値を取得できます。</span><span class="sxs-lookup"><span data-stu-id="99c36-150">The <xref:System.Net.Configuration.SmtpNetworkElement.Password%2A?displayProperty=nameWithType> property can be used to get the current value of the `password` attribute from applicable configuration files.</span></span> <span data-ttu-id="99c36-151">通常`password`、セキュリティ上の理由から、属性は構成ファイルに入力されません。</span><span class="sxs-lookup"><span data-stu-id="99c36-151">A `password` attribute would not normally be entered in configuration files for security reasons.</span></span>  
  
 <span data-ttu-id="99c36-152">この`clientDomain`属性は、最初の SMTP プロトコル要求で使用されるクライアント ドメイン名を SMTP サーバーに変更します。</span><span class="sxs-lookup"><span data-stu-id="99c36-152">The `clientDomain` attribute changes the client domain name used in the initial SMTP protocol request to an SMTP server.</span></span> <span data-ttu-id="99c36-153">属性`clientDomain`は、デフォルトで使用されるローカルホスト名ではなく、ローカルマシンの完全修飾ドメイン名に設定できます。</span><span class="sxs-lookup"><span data-stu-id="99c36-153">The `clientDomain` attribute can be set to the fully-qualified domain name of the local machine, rather than the localhost name that is used by default.</span></span> <span data-ttu-id="99c36-154">これにより、SMTP プロトコル標準への準拠性が向上します。</span><span class="sxs-lookup"><span data-stu-id="99c36-154">This provides greater compliance with the SMTP protocol standards.</span></span> <span data-ttu-id="99c36-155">既定値は、要求を送信するローカル コンピューターのローカル ホスト名です。</span><span class="sxs-lookup"><span data-stu-id="99c36-155">The default value is the localhost name of the local computer sending the request.</span></span> <span data-ttu-id="99c36-156">この<xref:System.Net.Configuration.SmtpNetworkElement.ClientDomain%2A?displayProperty=nameWithType>プロパティを使用して、適用可能な構成ファイルから`clientDomain`属性の現在の値を取得できます。</span><span class="sxs-lookup"><span data-stu-id="99c36-156">The <xref:System.Net.Configuration.SmtpNetworkElement.ClientDomain%2A?displayProperty=nameWithType> property can be used to get the current value of the `clientDomain` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="99c36-157">この`targetName`属性は、拡張保護を使用する場合に認証に使用されます。</span><span class="sxs-lookup"><span data-stu-id="99c36-157">The `targetName` attribute is used for authentication when using extended protection.</span></span> <span data-ttu-id="99c36-158">デフォルト値は、ホスト>が\<\<SMTP メール・サーバーのホスト名である「SMTPSVC/ホスト・>」の形式です。</span><span class="sxs-lookup"><span data-stu-id="99c36-158">The default value is of the form "SMTPSVC/\<host>" where \<host> is the hostname of the SMTP mail server.</span></span> <span data-ttu-id="99c36-159">この<xref:System.Net.Configuration.SmtpNetworkElement.TargetName%2A?displayProperty=nameWithType>プロパティを使用して、適用可能な構成ファイルから`targetName`属性の現在の値を取得できます。</span><span class="sxs-lookup"><span data-stu-id="99c36-159">The <xref:System.Net.Configuration.SmtpNetworkElement.TargetName%2A?displayProperty=nameWithType> property can be used to get the current value of the `targetName` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="99c36-160">この`enableSsl`属性は、SSL を使用して SMTP メール・サーバーにアクセスするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="99c36-160">The `enableSsl` attribute specifies whether SSL is used to access an SMTP mail server.</span></span> <span data-ttu-id="99c36-161">この<xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>クラスは、RFC 3207 で定義されているトランスポート層セキュリティ経由でのセキュリティで保護された SMTP の SMTP サービス拡張のみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="99c36-161">The <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType> class only supports the SMTP Service Extension for Secure SMTP over Transport Layer Security as defined in RFC 3207.</span></span> <span data-ttu-id="99c36-162">このモードでは、SMTP セッションは暗号化されていないチャネルで開始され、クライアントから STARTTLS コマンドが発行され、SSL を使用した通信のセキュリティ保護に切り替わります。</span><span class="sxs-lookup"><span data-stu-id="99c36-162">In this mode, the SMTP session begins on an unencrypted channel, then a STARTTLS command is issued by the client to the server to switch to secure communication using SSL.</span></span> <span data-ttu-id="99c36-163">詳細については、インターネット技術標準化委員会 (IETF) が発行した RFC 3207 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99c36-163">See RFC 3207 published by the Internet Engineering Task Force (IETF) for more information.</span></span>  
  
 <span data-ttu-id="99c36-164">代替接続方式は、プロトコル・コマンドが送信される前に SSL セッションが事前に確立される場所です。</span><span class="sxs-lookup"><span data-stu-id="99c36-164">An alternate connection method is where an SSL session is established up front before any protocol commands are sent.</span></span> <span data-ttu-id="99c36-165">この接続方法は SMTPS と呼ばれる場合があり、デフォルトではポート 465 が使用されます。</span><span class="sxs-lookup"><span data-stu-id="99c36-165">This connection method is sometimes called SMTPS and by default uses port 465.</span></span> <span data-ttu-id="99c36-166">SSL を使用するこの代替接続方式は、現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="99c36-166">This alternate connection method using SSL is not currently supported.</span></span>  
  
 <span data-ttu-id="99c36-167">この<xref:System.Net.Configuration.SmtpNetworkElement.EnableSsl%2A?displayProperty=nameWithType>プロパティを使用して、適用可能な構成ファイルから`enableSsl`属性の現在の値を取得できます。</span><span class="sxs-lookup"><span data-stu-id="99c36-167">The <xref:System.Net.Configuration.SmtpNetworkElement.EnableSsl%2A?displayProperty=nameWithType> property can be used to get the current value of the `enableSsl` attribute from applicable configuration files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="99c36-168">例</span><span class="sxs-lookup"><span data-stu-id="99c36-168">Example</span></span>  
 <span data-ttu-id="99c36-169">次の例では、既定のネットワーク資格情報を使用して電子メールを送信するための適切な SMTP パラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="99c36-169">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="99c36-170">関連項目</span><span class="sxs-lookup"><span data-stu-id="99c36-170">See also</span></span>

- <xref:System.Net.Configuration.SmtpNetworkElement?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- [<span data-ttu-id="99c36-171">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="99c36-171">Network Settings Schema</span></span>](index.md)
