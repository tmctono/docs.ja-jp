---
title: <network> 要素 (ネットワーク設定)
description: <network>Network settings 要素は、.NET Framework の外部 SMTP サーバーオプションのネットワークオプションを構成します。
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#network
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp/network
helpviewer_keywords:
- <network> element
- network element
ms.assetid: 2c2c6ad4-ed11-48ab-b28e-2bc0ba9b42c7
ms.openlocfilehash: cd142febc0b3aacf1be7978178a6a05d9b9aebbf
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91190281"
---
# <a name="network-element-network-settings"></a><span data-ttu-id="dcdca-103">\<network> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="dcdca-103">\<network> Element (Network Settings)</span></span>

<span data-ttu-id="dcdca-104">外部の簡易メール転送プロトコル (SMTP) サーバーのネットワークオプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="dcdca-104">Configures the network options for an external Simple Mail Transport Protocol (SMTP) server.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<smtp>**](smtp-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<network>**

## <a name="syntax"></a><span data-ttu-id="dcdca-105">構文</span><span class="sxs-lookup"><span data-stu-id="dcdca-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dcdca-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="dcdca-106">Attributes and Elements</span></span>  

 <span data-ttu-id="dcdca-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="dcdca-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dcdca-108">属性</span><span class="sxs-lookup"><span data-stu-id="dcdca-108">Attributes</span></span>  
  
|<span data-ttu-id="dcdca-109">属性</span><span class="sxs-lookup"><span data-stu-id="dcdca-109">Attribute</span></span>|<span data-ttu-id="dcdca-110">[説明]</span><span class="sxs-lookup"><span data-stu-id="dcdca-110">Description</span></span>|  
|---------------|-----------------|  
|`clientDomain`|<span data-ttu-id="dcdca-111">SMTP メールサーバーに接続するための最初の SMTP プロトコル要求で使用するクライアントドメイン名を指定します。</span><span class="sxs-lookup"><span data-stu-id="dcdca-111">Specifies the client domain name to use in the initial SMTP protocol request to connect to the SMTP mail server.</span></span> <span data-ttu-id="dcdca-112">既定値は、要求を送信しているローカルコンピューターの localhost 名です。</span><span class="sxs-lookup"><span data-stu-id="dcdca-112">The default value is the localhost name of the local computer sending the request.</span></span>|  
|`defaultCredentials`|<span data-ttu-id="dcdca-113">Smtp トランザクションの SMTP メールサーバーへのアクセスに、既定のユーザー資格情報を使用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="dcdca-113">Specifies whether the default user credentials should be used to access the SMTP mail server for SMTP transactions.</span></span> <span data-ttu-id="dcdca-114">既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="dcdca-114">The default value is `false`.</span></span>|  
|`enableSsl`|<span data-ttu-id="dcdca-115">SMTP メールサーバーへのアクセスに SSL を使用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="dcdca-115">Specifies whether SSL is used to access an SMTP mail server.</span></span> <span data-ttu-id="dcdca-116">既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="dcdca-116">The default value is `false`.</span></span>|  
|`host`|<span data-ttu-id="dcdca-117">SMTP トランザクションに使用する SMTP メールサーバーのホスト名を指定します。</span><span class="sxs-lookup"><span data-stu-id="dcdca-117">Specifies the hostname of the SMTP mail server to use for SMTP transactions.</span></span> <span data-ttu-id="dcdca-118">この属性には既定値はありません。</span><span class="sxs-lookup"><span data-stu-id="dcdca-118">This attribute has no default value.</span></span>|  
|`password`|<span data-ttu-id="dcdca-119">SMTP メールサーバーへの認証に使用するパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="dcdca-119">Specifies the password to use for authentication to the SMTP mail server.</span></span> <span data-ttu-id="dcdca-120">この属性には既定値はありません。</span><span class="sxs-lookup"><span data-stu-id="dcdca-120">This attribute has no default value.</span></span>|  
|`port`|<span data-ttu-id="dcdca-121">SMTP メールサーバーへの接続に使用するポート番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="dcdca-121">Specifies the port number to use to connect to the SMTP mail server.</span></span> <span data-ttu-id="dcdca-122">既定値は 25 です。</span><span class="sxs-lookup"><span data-stu-id="dcdca-122">The default value is 25.</span></span>|  
|`targetName`|<span data-ttu-id="dcdca-123">SMTP トランザクションの拡張保護を使用するときに認証に使用するサービスプロバイダー名 (SPN) を指定します。</span><span class="sxs-lookup"><span data-stu-id="dcdca-123">Specifies the Service Provider Name (SPN) to use for authentication when using extended protection for SMTP transactions.</span></span> <span data-ttu-id="dcdca-124">この属性には既定値はありません。</span><span class="sxs-lookup"><span data-stu-id="dcdca-124">This attribute has no default value.</span></span>|  
|`userName`|<span data-ttu-id="dcdca-125">SMTP メールサーバーへの認証に使用するユーザー名を指定します。</span><span class="sxs-lookup"><span data-stu-id="dcdca-125">Specifies the user name to use for authentication to the SMTP mail server.</span></span> <span data-ttu-id="dcdca-126">この属性には既定値はありません。</span><span class="sxs-lookup"><span data-stu-id="dcdca-126">This attribute has no default value.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dcdca-127">子要素</span><span class="sxs-lookup"><span data-stu-id="dcdca-127">Child Elements</span></span>  

 <span data-ttu-id="dcdca-128">なし。</span><span class="sxs-lookup"><span data-stu-id="dcdca-128">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dcdca-129">親要素</span><span class="sxs-lookup"><span data-stu-id="dcdca-129">Parent Elements</span></span>  
  
|<span data-ttu-id="dcdca-130">要素</span><span class="sxs-lookup"><span data-stu-id="dcdca-130">Element</span></span>|<span data-ttu-id="dcdca-131">説明</span><span class="sxs-lookup"><span data-stu-id="dcdca-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dcdca-132">\<smtp> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="dcdca-132">\<smtp> Element (Network Settings)</span></span>](smtp-element-network-settings.md)|<span data-ttu-id="dcdca-133">SMTP (Simple Mail Transport Protocol) メール送信オプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="dcdca-133">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dcdca-134">解説</span><span class="sxs-lookup"><span data-stu-id="dcdca-134">Remarks</span></span>  

 <span data-ttu-id="dcdca-135">一部の SMTP サーバーでは、使用する前にサーバーに対して認証を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="dcdca-135">Some SMTP servers require that you authenticate yourself to the server before use.</span></span> <span data-ttu-id="dcdca-136">ホストで既定のネットワーク資格情報を使用して認証する場合は、 `defaultCredentials` 属性をに設定 `true` します。</span><span class="sxs-lookup"><span data-stu-id="dcdca-136">If you want to authenticate yourself using the default network credentials on your host, set the `defaultCredentials` attribute to `true`.</span></span> <span data-ttu-id="dcdca-137">プロパティは、 <xref:System.Net.Configuration.SmtpNetworkElement.DefaultCredentials%2A?displayProperty=nameWithType> `defaultCredentials` 適用可能な構成ファイルから属性の現在の値を取得するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="dcdca-137">The <xref:System.Net.Configuration.SmtpNetworkElement.DefaultCredentials%2A?displayProperty=nameWithType> property can be used to get the current value of the `defaultCredentials` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="dcdca-138">基本認証 (ユーザー名とパスワード) を使用して、SMTP サーバーに対する認証を行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="dcdca-138">You can also use basic authentication (a user name and password) to authenticate yourself to the SMTP server.</span></span> <span data-ttu-id="dcdca-139">このオプションを使用するには、指定した SMTP サーバーの有効なユーザー名とパスワードを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dcdca-139">To use this option, you must specify a valid user name and password for the specified SMTP server.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="dcdca-140">基本認証は、 `userName` およびの `password` 値を暗号化せずにサーバーに送信します。</span><span class="sxs-lookup"><span data-stu-id="dcdca-140">Basic authentication sends the `userName` and `password` values to the server unencrypted.</span></span> <span data-ttu-id="dcdca-141">ネットワークトラフィックを監視するすべてのユーザーは、資格情報を表示し、それらを使用してサーバーに接続できます。</span><span class="sxs-lookup"><span data-stu-id="dcdca-141">Anyone monitoring network traffic can view your credentials and use them to connect to the server.</span></span> <span data-ttu-id="dcdca-142">Kerberos や NT LAN Manager (NTLM) など、より安全な認証メカニズムの使用を検討する必要があります。がの場合 `defaultCredentials` `true` 、サーバーがこれらのプロトコルをサポートする場合、Kerberos または NTLM が使用されます。</span><span class="sxs-lookup"><span data-stu-id="dcdca-142">You should consider using a more secure authentication mechanism, such as Kerberos or NT LAN Manager (NTLM.) If `defaultCredentials` is `true`, Kerberos or NTLM will be used if the server supports these protocols.</span></span>  
  
 <span data-ttu-id="dcdca-143">基本認証および既定のネットワーク資格情報オプションは、同時には指定できません。 `defaultCredentials` をに設定 `true` し、ユーザー名とパスワードを指定した場合、既定のネットワーク資格情報が使用され、基本認証データは無視されます。</span><span class="sxs-lookup"><span data-stu-id="dcdca-143">The basic authentication and default network credentials options are mutually exclusive; if you set `defaultCredentials` to `true` and specify a user name and password, the default network credential is used, and the basic authentication data is ignored.</span></span>  
  
 <span data-ttu-id="dcdca-144">基本認証でを指定する場合は、 `userName` メールサーバーに対して自分で認証を行うようにを指定する必要もあり `password` ます。</span><span class="sxs-lookup"><span data-stu-id="dcdca-144">For basic authentication if you specify a `userName`, you should also specify a `password` to authentication yourself to the mail server.</span></span>  
  
 <span data-ttu-id="dcdca-145">プロパティは、 <xref:System.Net.Configuration.SmtpNetworkElement.UserName%2A?displayProperty=nameWithType> `userName` 適用可能な構成ファイルから属性の現在の値を取得するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="dcdca-145">The <xref:System.Net.Configuration.SmtpNetworkElement.UserName%2A?displayProperty=nameWithType> property can be used to get the current value of the `userName` attribute from applicable configuration files.</span></span> <span data-ttu-id="dcdca-146">プロパティは、 <xref:System.Net.Configuration.SmtpNetworkElement.Password%2A?displayProperty=nameWithType> `password` 適用可能な構成ファイルから属性の現在の値を取得するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="dcdca-146">The <xref:System.Net.Configuration.SmtpNetworkElement.Password%2A?displayProperty=nameWithType> property can be used to get the current value of the `password` attribute from applicable configuration files.</span></span> <span data-ttu-id="dcdca-147">`password`通常、セキュリティ上の理由から、属性を構成ファイルに入力することはできません。</span><span class="sxs-lookup"><span data-stu-id="dcdca-147">A `password` attribute would not normally be entered in configuration files for security reasons.</span></span>  
  
 <span data-ttu-id="dcdca-148">属性は、 `clientDomain` smtp プロトコルの初期要求で使用されるクライアントのドメイン名を smtp サーバーに変更します。</span><span class="sxs-lookup"><span data-stu-id="dcdca-148">The `clientDomain` attribute changes the client domain name used in the initial SMTP protocol request to an SMTP server.</span></span> <span data-ttu-id="dcdca-149">属性は、 `clientDomain` 既定で使用される localhost 名ではなく、ローカルコンピューターの完全修飾ドメイン名に設定できます。</span><span class="sxs-lookup"><span data-stu-id="dcdca-149">The `clientDomain` attribute can be set to the fully-qualified domain name of the local machine, rather than the localhost name that is used by default.</span></span> <span data-ttu-id="dcdca-150">これにより、SMTP プロトコル標準への準拠が向上します。</span><span class="sxs-lookup"><span data-stu-id="dcdca-150">This provides greater compliance with the SMTP protocol standards.</span></span> <span data-ttu-id="dcdca-151">既定値は、要求を送信しているローカルコンピューターの localhost 名です。</span><span class="sxs-lookup"><span data-stu-id="dcdca-151">The default value is the localhost name of the local computer sending the request.</span></span> <span data-ttu-id="dcdca-152">プロパティは、 <xref:System.Net.Configuration.SmtpNetworkElement.ClientDomain%2A?displayProperty=nameWithType> `clientDomain` 適用可能な構成ファイルから属性の現在の値を取得するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="dcdca-152">The <xref:System.Net.Configuration.SmtpNetworkElement.ClientDomain%2A?displayProperty=nameWithType> property can be used to get the current value of the `clientDomain` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="dcdca-153">`targetName`拡張保護を使用する場合、この属性は認証に使用されます。</span><span class="sxs-lookup"><span data-stu-id="dcdca-153">The `targetName` attribute is used for authentication when using extended protection.</span></span> <span data-ttu-id="dcdca-154">既定値は "SMTPSVC/" の形式です \<host> 。ここ \<host> で、は SMTP メールサーバーのホスト名です。</span><span class="sxs-lookup"><span data-stu-id="dcdca-154">The default value is of the form "SMTPSVC/\<host>" where \<host> is the hostname of the SMTP mail server.</span></span> <span data-ttu-id="dcdca-155">プロパティは、 <xref:System.Net.Configuration.SmtpNetworkElement.TargetName%2A?displayProperty=nameWithType> `targetName` 適用可能な構成ファイルから属性の現在の値を取得するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="dcdca-155">The <xref:System.Net.Configuration.SmtpNetworkElement.TargetName%2A?displayProperty=nameWithType> property can be used to get the current value of the `targetName` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="dcdca-156">属性では、 `enableSsl` SMTP メールサーバーへのアクセスに SSL を使用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="dcdca-156">The `enableSsl` attribute specifies whether SSL is used to access an SMTP mail server.</span></span> <span data-ttu-id="dcdca-157">クラスでサポートされているのは、 <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType> RFC 3207 で定義されているトランスポート層セキュリティ経由の SECURE smtp に対する Smtp サービス拡張のみです。</span><span class="sxs-lookup"><span data-stu-id="dcdca-157">The <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType> class only supports the SMTP Service Extension for Secure SMTP over Transport Layer Security as defined in RFC 3207.</span></span> <span data-ttu-id="dcdca-158">このモードでは、暗号化されていないチャネルで SMTP セッションが開始され、SSL を使用してセキュリティで保護された通信に切り替えるために、クライアントからサーバーに STARTTLS コマンドが発行されます。</span><span class="sxs-lookup"><span data-stu-id="dcdca-158">In this mode, the SMTP session begins on an unencrypted channel, then a STARTTLS command is issued by the client to the server to switch to secure communication using SSL.</span></span> <span data-ttu-id="dcdca-159">詳細については、インターネット技術標準化委員会 (IETF) によって発行された RFC 3207 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dcdca-159">See RFC 3207 published by the Internet Engineering Task Force (IETF) for more information.</span></span>  
  
 <span data-ttu-id="dcdca-160">代替の接続方法では、プロトコルコマンドが送信される前に、SSL セッションが事前に確立されます。</span><span class="sxs-lookup"><span data-stu-id="dcdca-160">An alternate connection method is where an SSL session is established up front before any protocol commands are sent.</span></span> <span data-ttu-id="dcdca-161">この接続方法は SMTPS とも呼ばれ、既定ではポート465を使用します。</span><span class="sxs-lookup"><span data-stu-id="dcdca-161">This connection method is sometimes called SMTPS and by default uses port 465.</span></span> <span data-ttu-id="dcdca-162">SSL を使用したこの代替接続方法は、現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="dcdca-162">This alternate connection method using SSL is not currently supported.</span></span>  
  
 <span data-ttu-id="dcdca-163">プロパティは、 <xref:System.Net.Configuration.SmtpNetworkElement.EnableSsl%2A?displayProperty=nameWithType> `enableSsl` 適用可能な構成ファイルから属性の現在の値を取得するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="dcdca-163">The <xref:System.Net.Configuration.SmtpNetworkElement.EnableSsl%2A?displayProperty=nameWithType> property can be used to get the current value of the `enableSsl` attribute from applicable configuration files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dcdca-164">例</span><span class="sxs-lookup"><span data-stu-id="dcdca-164">Example</span></span>  

 <span data-ttu-id="dcdca-165">次の例では、既定のネットワーク資格情報を使用して電子メールを送信するための適切な SMTP パラメーターを指定しています。</span><span class="sxs-lookup"><span data-stu-id="dcdca-165">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="dcdca-166">関連項目</span><span class="sxs-lookup"><span data-stu-id="dcdca-166">See also</span></span>

- <xref:System.Net.Configuration.SmtpNetworkElement?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- [<span data-ttu-id="dcdca-167">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="dcdca-167">Network Settings Schema</span></span>](index.md)
