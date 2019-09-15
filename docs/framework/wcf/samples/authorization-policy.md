---
title: 承認ポリシー
ms.date: 03/30/2017
ms.assetid: 1db325ec-85be-47d0-8b6e-3ba2fdf3dda0
ms.openlocfilehash: 9b73eea1f51454dd82ba577c4d4d5fd5a1c0efd4
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2019
ms.locfileid: "70990186"
---
# <a name="authorization-policy"></a><span data-ttu-id="d1d44-102">承認ポリシー</span><span class="sxs-lookup"><span data-stu-id="d1d44-102">Authorization Policy</span></span>

<span data-ttu-id="d1d44-103">このサンプルでは、カスタム クレーム承認ポリシーと、関連するカスタム サービス承認マネージャーを実装する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d1d44-103">This sample demonstrates how to implement a custom claim authorization policy and an associated custom service authorization manager.</span></span> <span data-ttu-id="d1d44-104">この方法は、サービスがクレームに基づくアクセス チェックをサービス操作に行う場合や、アクセス チェックを行う前に呼び出し元に特定の権限を与える場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="d1d44-104">This is useful when the service makes claim-based access checks to service operations and prior to the access checks, grants the caller certain rights.</span></span> <span data-ttu-id="d1d44-105">このサンプルでは、クレームの追加プロセスと、完了したクレーム セットに対してアクセス チェックを行うプロセスの両方を示します。</span><span class="sxs-lookup"><span data-stu-id="d1d44-105">This sample shows both the process of adding claims as well as the process for doing an access check against the finalized set of claims.</span></span> <span data-ttu-id="d1d44-106">クライアント/サーバー間のすべてのアプリケーション メッセージは署名され、暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="d1d44-106">All application messages between the client and server are signed and encrypted.</span></span> <span data-ttu-id="d1d44-107">`wsHttpBinding` バインディングを使用する際の既定では、クライアントによって提供されるユーザー名とパスワードが、有効な Windows NT アカウントへのログオンに使用されます。</span><span class="sxs-lookup"><span data-stu-id="d1d44-107">By default with the `wsHttpBinding` binding, a username and password supplied by the client are used to logon to a valid Windows NT account.</span></span> <span data-ttu-id="d1d44-108">このサンプルでは、カスタム <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> を使用してクライアントを認証する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d1d44-108">This sample demonstrates how to utilize a custom <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> to authenticate the client.</span></span> <span data-ttu-id="d1d44-109">さらにこのサンプルでは、クライアントが X.509 証明書を使用してサービスを認証する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d1d44-109">In addition this sample shows the client authenticating to the service using an X.509 certificate.</span></span> <span data-ttu-id="d1d44-110">また、<xref:System.IdentityModel.Policy.IAuthorizationPolicy> と <xref:System.ServiceModel.ServiceAuthorizationManager> の実装も示します。これらの間では、特定のユーザーに対するサービスの特定のメソッドへのアクセスが許可されます。</span><span class="sxs-lookup"><span data-stu-id="d1d44-110">This sample shows an implementation of <xref:System.IdentityModel.Policy.IAuthorizationPolicy> and <xref:System.ServiceModel.ServiceAuthorizationManager>, which between them grant access to specific methods of the service for specific users.</span></span> <span data-ttu-id="d1d44-111">このサンプルは、[メッセージセキュリティユーザー名](../../../../docs/framework/wcf/samples/message-security-user-name.md)に基づいていますが、 <xref:System.ServiceModel.ServiceAuthorizationManager>が呼び出される前に要求変換を実行する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="d1d44-111">This sample is based on the [Message Security User Name](../../../../docs/framework/wcf/samples/message-security-user-name.md), but demonstrates how to perform a claim transformation prior to the <xref:System.ServiceModel.ServiceAuthorizationManager> being called.</span></span>

> [!NOTE]
> <span data-ttu-id="d1d44-112">このサンプルのセットアップ手順とビルド手順については、このトピックの最後を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1d44-112">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

 <span data-ttu-id="d1d44-113">このサンプルで示す処理の概要は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d1d44-113">In summary, this sample demonstrates how:</span></span>

- <span data-ttu-id="d1d44-114">クライアントはユーザー名とパスワードを使用して認証される。</span><span class="sxs-lookup"><span data-stu-id="d1d44-114">The client can be authenticated using a user name-password.</span></span>

- <span data-ttu-id="d1d44-115">クライアントは X.509 証明書を使用して認証される。</span><span class="sxs-lookup"><span data-stu-id="d1d44-115">The client can be authenticated using an X.509 certificate.</span></span>

- <span data-ttu-id="d1d44-116">サーバーはクライアント資格情報をカスタム `UsernamePassword` 検証と照合する。</span><span class="sxs-lookup"><span data-stu-id="d1d44-116">The server validates the client credentials against a custom `UsernamePassword` validator.</span></span>

- <span data-ttu-id="d1d44-117">サーバーがそのサーバーの X.509 証明書を使用して認証される。</span><span class="sxs-lookup"><span data-stu-id="d1d44-117">The server is authenticated using the server's X.509 certificate.</span></span>

- <span data-ttu-id="d1d44-118">サーバーが <xref:System.ServiceModel.ServiceAuthorizationManager> を使用して、サービス内の特定メソッドへのアクセスを制御する。</span><span class="sxs-lookup"><span data-stu-id="d1d44-118">The server can use <xref:System.ServiceModel.ServiceAuthorizationManager> to control access to certain methods in the service.</span></span>

- <span data-ttu-id="d1d44-119"><xref:System.IdentityModel.Policy.IAuthorizationPolicy> の実装方法。</span><span class="sxs-lookup"><span data-stu-id="d1d44-119">How to implement <xref:System.IdentityModel.Policy.IAuthorizationPolicy>.</span></span>

<span data-ttu-id="d1d44-120">サービスは、そのサービスとの通信に使用する 2 つのエンドポイントを公開します。エンドポイントは構成ファイル App.config で定義します。各エンドポイントは、アドレス、バインディング、およびコントラクトがそれぞれ 1 つずつで構成されます。</span><span class="sxs-lookup"><span data-stu-id="d1d44-120">The service exposes two endpoints for communicating with the service, defined using the configuration file App.config. Each endpoint consists of an address, a binding, and a contract.</span></span> <span data-ttu-id="d1d44-121">1 つのバインディングの構成には、WS-Security とクライアントのユーザー名認証を使用する、標準の `wsHttpBinding` バインディングが使用されます。</span><span class="sxs-lookup"><span data-stu-id="d1d44-121">One binding is configured with a standard `wsHttpBinding` binding that uses WS-Security and client username authentication.</span></span> <span data-ttu-id="d1d44-122">もう 1 つのバインディングの構成には、WS-Security とクライアント証明書による認証を使用する、標準の `wsHttpBinding` バインディングが使用されます。</span><span class="sxs-lookup"><span data-stu-id="d1d44-122">The other binding is configured with a standard `wsHttpBinding` binding that uses WS-Security and client certificate authentication.</span></span> <span data-ttu-id="d1d44-123">[ \<動作 >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)は、ユーザーの資格情報をサービス認証に使用することを指定します。</span><span class="sxs-lookup"><span data-stu-id="d1d44-123">The [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) specifies that the user credentials are to be used for service authentication.</span></span> <span data-ttu-id="d1d44-124">サーバー証明書には、 [ \<serviceCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)の`findValue`属性`SubjectName`と同じ値が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1d44-124">The server certificate must contain the same value for the `SubjectName` property as the `findValue` attribute in the [\<serviceCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md).</span></span>

```xml
<system.serviceModel>
  <services>
    <service name="Microsoft.ServiceModel.Samples.CalculatorService"
             behaviorConfiguration="CalculatorServiceBehavior">
      <host>
        <baseAddresses>
          <!-- configure base address provided by host -->
          <add baseAddress ="http://localhost:8001/servicemodelsamples/service"/>
        </baseAddresses>
      </host>
      <!-- use base address provided by host, provide two endpoints -->
      <endpoint address="username"
                binding="wsHttpBinding"
                bindingConfiguration="Binding1"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />
      <endpoint address="certificate"
                binding="wsHttpBinding"
                bindingConfiguration="Binding2"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />
    </service>
  </services>

  <bindings>
    <wsHttpBinding>
      <!-- Username binding -->
      <binding name="Binding1">
        <security mode="Message">
    <message clientCredentialType="UserName" />
        </security>
      </binding>
      <!-- X509 certificate binding -->
      <binding name="Binding2">
        <security mode="Message">
          <message clientCredentialType="Certificate" />
        </security>
      </binding>
    </wsHttpBinding>
  </bindings>

  <behaviors>
    <serviceBehaviors>
      <behavior name="CalculatorServiceBehavior" >
        <serviceDebug includeExceptionDetailInFaults ="true" />
        <serviceCredentials>
          <!--
          The serviceCredentials behavior allows one to specify a custom validator for username/password combinations.
          -->
          <userNameAuthentication userNamePasswordValidationMode="Custom" customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.MyCustomUserNameValidator, service" />
          <!--
          The serviceCredentials behavior allows one to specify authentication constraints on client certificates.
          -->
          <clientCertificate>
            <!--
            Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate
            is in the user's Trusted People store, then it will be trusted without performing a
            validation of the certificate's issuer chain. This setting is used here for convenience so that the
            sample can be run without having to have certificates issued by a certification authority (CA).
            This setting is less secure than the default, ChainTrust. The security implications of this
            setting should be carefully considered before using PeerOrChainTrust in production code.
            -->
            <authentication certificateValidationMode="PeerOrChainTrust" />
          </clientCertificate>
          <!--
          The serviceCredentials behavior allows one to define a service certificate.
          A service certificate is used by a client to authenticate the service and provide message protection.
          This configuration references the "localhost" certificate installed during the setup instructions.
          -->
          <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />
        </serviceCredentials>
        <serviceAuthorization serviceAuthorizationManagerType="Microsoft.ServiceModel.Samples.MyServiceAuthorizationManager, service">
          <!--
          The serviceAuthorization behavior allows one to specify custom authorization policies.
          -->
          <authorizationPolicies>
            <add policyType="Microsoft.ServiceModel.Samples.CustomAuthorizationPolicy.MyAuthorizationPolicy, PolicyLibrary" />
          </authorizationPolicies>
        </serviceAuthorization>
      </behavior>
    </serviceBehaviors>
  </behaviors>

</system.serviceModel>
```

<span data-ttu-id="d1d44-125">各クライアント エンドポイント構成は、構成名、サービス エンドポイントの絶対アドレス、バインディング、およびコントラクトで構成されます。</span><span class="sxs-lookup"><span data-stu-id="d1d44-125">Each client endpoint configuration consists of a configuration name, an absolute address for the service endpoint, the binding, and the contract.</span></span> <span data-ttu-id="d1d44-126">クライアントバインディングは、 `clientCredentialType` [ \<セキュリティ >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md)で指定されている適切なセキュリティモードと、 [ \<メッセージ >](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md)で指定されているとおりに構成されます。</span><span class="sxs-lookup"><span data-stu-id="d1d44-126">The client binding is configured with the appropriate security mode as specified in this case in the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md) and `clientCredentialType` as specified in the [\<message>](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md).</span></span>

```xml
<system.serviceModel>

    <client>
      <!-- Username based endpoint -->
      <endpoint name="Username"
            address="http://localhost:8001/servicemodelsamples/service/username"
    binding="wsHttpBinding"
    bindingConfiguration="Binding1"
                behaviorConfiguration="ClientCertificateBehavior"
                contract="Microsoft.ServiceModel.Samples.ICalculator" >
      </endpoint>
      <!-- X509 certificate based endpoint -->
      <endpoint name="Certificate"
                        address="http://localhost:8001/servicemodelsamples/service/certificate"
                binding="wsHttpBinding"
            bindingConfiguration="Binding2"
                behaviorConfiguration="ClientCertificateBehavior"
                contract="Microsoft.ServiceModel.Samples.ICalculator">
      </endpoint>
    </client>

    <bindings>
      <wsHttpBinding>
        <!-- Username binding -->
      <binding name="Binding1">
        <security mode="Message">
          <message clientCredentialType="UserName" />
        </security>
      </binding>
        <!-- X509 certificate binding -->
        <binding name="Binding2">
          <security mode="Message">
            <message clientCredentialType="Certificate" />
          </security>
        </binding>
    </wsHttpBinding>
    </bindings>

    <behaviors>
      <behavior name="ClientCertificateBehavior">
        <clientCredentials>
          <serviceCertificate>
            <!--
            Setting the certificateValidationMode to PeerOrChainTrust
            means that if the certificate
            is in the user's Trusted People store, then it will be
            trusted without performing a
            validation of the certificate's issuer chain. This setting
            is used here for convenience so that the
            sample can be run without having to have certificates
            issued by a certification authority (CA).
            This setting is less secure than the default, ChainTrust.
            The security implications of this
            setting should be carefully considered before using
            PeerOrChainTrust in production code.
            -->
            <authentication certificateValidationMode = "PeerOrChainTrust" />
          </serviceCertificate>
        </clientCredentials>
      </behavior>
    </behaviors>

  </system.serviceModel>
```

<span data-ttu-id="d1d44-127">ユーザー名に基づくエンドポイントには、使用するユーザー名とパスワードがクライアント実装で設定されます。</span><span class="sxs-lookup"><span data-stu-id="d1d44-127">For the user name-based endpoint, the client implementation sets the user name and password to use.</span></span>

```csharp
// Create a client with Username endpoint configuration
CalculatorClient client1 = new CalculatorClient("Username");

client1.ClientCredentials.UserName.UserName = "test1";
client1.ClientCredentials.UserName.Password = "1tset";

try
{
    // Call the Add service operation.
    double value1 = 100.00D;
    double value2 = 15.99D;
    double result = client1.Add(value1, value2);
    Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);
    ...
}
catch (Exception e)
{
    Console.WriteLine("Call failed : {0}", e.Message);
}

client1.Close();
```

<span data-ttu-id="d1d44-128">証明書に基づくエンドポイントには、使用するクライアント証明書がクライアント実装で設定されます。</span><span class="sxs-lookup"><span data-stu-id="d1d44-128">For the certificate-based endpoint, the client implementation sets the client certificate to use.</span></span>

```csharp
// Create a client with Certificate endpoint configuration
CalculatorClient client2 = new CalculatorClient("Certificate");

client2.ClientCredentials.ClientCertificate.SetCertificate(StoreLocation.CurrentUser, StoreName.My, X509FindType.FindBySubjectName, "test1");

try
{
    // Call the Add service operation.
    double value1 = 100.00D;
    double value2 = 15.99D;
    double result = client2.Add(value1, value2);
    Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);
    ...
}
catch (Exception e)
{
    Console.WriteLine("Call failed : {0}", e.Message);
}

client2.Close();
```

<span data-ttu-id="d1d44-129">このサンプルでは、カスタム <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> を使用してユーザー名とパスワードを検証します。</span><span class="sxs-lookup"><span data-stu-id="d1d44-129">This sample uses a custom <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> to validate user names and passwords.</span></span> <span data-ttu-id="d1d44-130">サンプルは、`MyCustomUserNamePasswordValidator` から派生する <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> を実装しています。</span><span class="sxs-lookup"><span data-stu-id="d1d44-130">The sample implements `MyCustomUserNamePasswordValidator`, derived from <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>.</span></span> <span data-ttu-id="d1d44-131"><xref:System.IdentityModel.Selectors.UserNamePasswordValidator> の詳細については、ドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1d44-131">See the documentation about <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> for more information.</span></span> <span data-ttu-id="d1d44-132"><xref:System.IdentityModel.Selectors.UserNamePasswordValidator> との統合を示すため、カスタム検証のこのサンプルでは次のコード例に示すように、<xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> メソッドを実装して、ユーザー名がパスワードと一致するユーザー名とパスワードの組み合わせを許可します。</span><span class="sxs-lookup"><span data-stu-id="d1d44-132">For the purposes of demonstrating the integration with the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>, this custom validator sample implements the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> method to accept user name/password pairs where the user name matches the password as shown in the following code.</span></span>

```csharp
public class MyCustomUserNamePasswordValidator : UserNamePasswordValidator
{
  // This method validates users. It allows in two users,
  // test1 and test2 with passwords 1tset and 2tset respectively.
  // This code is for illustration purposes only and
  // MUST NOT be used in a production environment because it
  // is NOT secure.
  public override void Validate(string userName, string password)
  {
    if (null == userName || null == password)
    {
      throw new ArgumentNullException();
    }

    if (!(userName == "test1" && password == "1tset") && !(userName == "test2" && password == "2tset"))
    {
      throw new SecurityTokenException("Unknown Username or Password");
    }
  }
}
```

<span data-ttu-id="d1d44-133">サービス コードに検証を実装した場合、使用する検証インスタンスをサービス ホストに通知する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1d44-133">Once the validator is implemented in service code, the service host must be informed about the validator instance to use.</span></span> <span data-ttu-id="d1d44-134">これを行うには、次のコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="d1d44-134">This is done using the following code:</span></span>

```csharp
Servicehost.Credentials.UserNameAuthentication.UserNamePasswordValidationMode = UserNamePasswordValidationMode.Custom;
serviceHost.Credentials.UserNameAuthentication.CustomUserNamePasswordValidator = new MyCustomUserNamePasswordValidatorProvider();
```

<span data-ttu-id="d1d44-135">または、次の構成でも同じことを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="d1d44-135">Or you can do the same thing in configuration:</span></span>

```xml
<behavior ...>
    <serviceCredentials>
      <!--
      The serviceCredentials behavior allows one to specify a custom validator for username/password combinations.
      -->
      <userNameAuthentication userNamePasswordValidationMode="Custom" customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.MyCustomUserNameValidator, service" />
    ...
    </serviceCredentials>
</behavior>
```

<span data-ttu-id="d1d44-136">Windows Communication Foundation (WCF) は、アクセスチェックを実行するための豊富な要求ベースのモデルを提供します。</span><span class="sxs-lookup"><span data-stu-id="d1d44-136">Windows Communication Foundation (WCF) provides a rich claims-based model for performing access checks.</span></span> <span data-ttu-id="d1d44-137"><xref:System.ServiceModel.ServiceAuthorizationManager> オブジェクトを使用するとアクセス チェックが実行され、クライアントに関連付けられたクレームがサービス メソッドへのアクセスに必要な要件を満たすかどうかが判断されます。</span><span class="sxs-lookup"><span data-stu-id="d1d44-137">The <xref:System.ServiceModel.ServiceAuthorizationManager> object is used to perform the access check and determine whether the claims associated with the client satisfy the requirements necessary to access the service method.</span></span>

<span data-ttu-id="d1d44-138">このサンプルでは、このサンプルでは、 <xref:System.ServiceModel.ServiceAuthorizationManager> <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A>メソッドを実装するの実装を示しています。このメソッドは、値がで`http://example.com/claims/allowedoperation`ある操作のアクション URI である型の要求に基づいて、ユーザーがメソッドにアクセスできるようにします。を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="d1d44-138">For the purposes of demonstration, this sample shows an implementation of <xref:System.ServiceModel.ServiceAuthorizationManager> that implements the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> method to allow a user's access to methods based on claims of type `http://example.com/claims/allowedoperation` whose value is the Action URI of the operation that is allowed to be called.</span></span>

```csharp
public class MyServiceAuthorizationManager : ServiceAuthorizationManager
{
  protected override bool CheckAccessCore(OperationContext operationContext)
  {
    string action = operationContext.RequestContext.RequestMessage.Headers.Action;
    Console.WriteLine("action: {0}", action);
    foreach(ClaimSet cs in operationContext.ServiceSecurityContext.AuthorizationContext.ClaimSets)
    {
      if ( cs.Issuer == ClaimSet.System )
      {
        foreach (Claim c in cs.FindClaims("http://example.com/claims/allowedoperation", Rights.PossessProperty))
        {
          Console.WriteLine("resource: {0}", c.Resource.ToString());
          if (action == c.Resource.ToString())
            return true;
        }
      }
    }
    return false;
  }
}
```

<span data-ttu-id="d1d44-139">カスタム <xref:System.ServiceModel.ServiceAuthorizationManager> を実装した場合、使用する <xref:System.ServiceModel.ServiceAuthorizationManager> をサービス ホストに通知する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1d44-139">Once the custom <xref:System.ServiceModel.ServiceAuthorizationManager> is implemented, the service host must be informed about the <xref:System.ServiceModel.ServiceAuthorizationManager> to use.</span></span> <span data-ttu-id="d1d44-140">これを行うコードは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="d1d44-140">This is done as shown in the following code.</span></span>

```xml
<behavior ...>
    ...
    <serviceAuthorization serviceAuthorizationManagerType="Microsoft.ServiceModel.Samples.MyServiceAuthorizationManager, service">
        ...
    </serviceAuthorization>
</behavior>
```

<span data-ttu-id="d1d44-141">実装する主要な <xref:System.IdentityModel.Policy.IAuthorizationPolicy> メソッドは、<xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29> メソッドです。</span><span class="sxs-lookup"><span data-stu-id="d1d44-141">The primary <xref:System.IdentityModel.Policy.IAuthorizationPolicy> method to implement is the <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29> method.</span></span>

```csharp
public class MyAuthorizationPolicy : IAuthorizationPolicy
{
    string id;

    public MyAuthorizationPolicy()
    {
    id =  Guid.NewGuid().ToString();
    }

    public bool Evaluate(EvaluationContext evaluationContext,
                                            ref object state)
    {
        bool bRet = false;
        CustomAuthState customstate = null;

        if (state == null)
        {
            customstate = new CustomAuthState();
            state = customstate;
        }
        else
            customstate = (CustomAuthState)state;
        Console.WriteLine("In Evaluate");
        if (!customstate.ClaimsAdded)
        {
           IList<Claim> claims = new List<Claim>();

           foreach (ClaimSet cs in evaluationContext.ClaimSets)
              foreach (Claim c in cs.FindClaims(ClaimTypes.Name,
                                         Rights.PossessProperty))
                  foreach (string s in
                        GetAllowedOpList(c.Resource.ToString()))
                  {
                       claims.Add(new
               Claim("http://example.com/claims/allowedoperation",
                                    s, Rights.PossessProperty));
                            Console.WriteLine("Claim added {0}", s);
                      }
                   evaluationContext.AddClaimSet(this,
                           new DefaultClaimSet(this.Issuer,claims));
                   customstate.ClaimsAdded = true;
                   bRet = true;
                }
         else
         {
              bRet = true;
         }
         return bRet;
     }
...
}
```

<span data-ttu-id="d1d44-142">前のコードでは、<xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29> メソッドが、処理に影響を与える新しいクレームが追加されていないことをチェックして特定のクレームを追加する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="d1d44-142">The previous code shows how the <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29> method checks that no new claims have been added that affect the processing and adds specific claims.</span></span> <span data-ttu-id="d1d44-143">許可されるクレームは `GetAllowedOpList` メソッドから取得されます。このメソッドが実装されると、ユーザーによる実行が許可されている特定の操作リストが返されます。</span><span class="sxs-lookup"><span data-stu-id="d1d44-143">The claims that are allowed are obtained from the `GetAllowedOpList` method, which is implemented to return a specific list of operations that the user is allowed to perform.</span></span> <span data-ttu-id="d1d44-144">承認ポリシーは、特定の操作にアクセスするためのクレームを追加します。</span><span class="sxs-lookup"><span data-stu-id="d1d44-144">The authorization policy adds claims for accessing the particular operation.</span></span> <span data-ttu-id="d1d44-145">このポリシーは、アクセス チェックの決定を実行する <xref:System.ServiceModel.ServiceAuthorizationManager> によって後で使用されます。</span><span class="sxs-lookup"><span data-stu-id="d1d44-145">This is later used by the <xref:System.ServiceModel.ServiceAuthorizationManager> to perform access check decisions.</span></span>

<span data-ttu-id="d1d44-146">カスタム <xref:System.IdentityModel.Policy.IAuthorizationPolicy> を実装した場合、使用する承認ポリシーをサービス ホストに通知する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1d44-146">Once the custom <xref:System.IdentityModel.Policy.IAuthorizationPolicy> is implemented, the service host must be informed about the authorization policies to use.</span></span>

```xml
<serviceAuthorization ...>
       <authorizationPolicies>
            <add policyType='Microsoft.ServiceModel.Samples.CustomAuthorizationPolicy.MyAuthorizationPolicy, PolicyLibrary' />
       </authorizationPolicies>
</serviceAuthorization>
```

<span data-ttu-id="d1d44-147">このサンプルを実行すると、操作要求および応答がクライアントのコンソール ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="d1d44-147">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="d1d44-148">クライアントでは Add、Subtract、および Multiple メソッドは正常に呼び出されますが、Divide メソッドを呼び出そうとすると、"アクセスが拒否されました" のメッセージが発生します。</span><span class="sxs-lookup"><span data-stu-id="d1d44-148">The client successfully calls the Add, Subtract and Multiple methods and gets an "Access is denied" message when trying to call the Divide method.</span></span> <span data-ttu-id="d1d44-149">クライアントをシャットダウンするには、クライアント ウィンドウで Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="d1d44-149">Press ENTER in the client window to shut down the client.</span></span>

## <a name="setup-batch-file"></a><span data-ttu-id="d1d44-150">セットアップ バッチ ファイル</span><span class="sxs-lookup"><span data-stu-id="d1d44-150">Setup Batch File</span></span>

<span data-ttu-id="d1d44-151">このサンプルに用意されている Setup.bat バッチ ファイルを使用すると、適切な証明書を使用してサーバーを構成し、サーバー証明書ベースのセキュリティを必要とする自己ホスト型アプリケーションを実行できるようになります。</span><span class="sxs-lookup"><span data-stu-id="d1d44-151">The Setup.bat batch file included with this sample allows you to configure the server with relevant certificates to run a self-hosted application that requires server certificate-based security.</span></span>

<span data-ttu-id="d1d44-152">次に、バッチ ファイルのセクションのうち、該当する構成で実行するために変更が必要となる部分を示します。</span><span class="sxs-lookup"><span data-stu-id="d1d44-152">The following provides a brief overview of the different sections of the batch files so that they can be modified to run in the appropriate configuration:</span></span>

- <span data-ttu-id="d1d44-153">サーバー証明書の作成。</span><span class="sxs-lookup"><span data-stu-id="d1d44-153">Creating the server certificate.</span></span>

    <span data-ttu-id="d1d44-154">Setup.bat バッチ ファイルの次の行は、使用するサーバー証明書を作成します。</span><span class="sxs-lookup"><span data-stu-id="d1d44-154">The following lines from the Setup.bat batch file create the server certificate to be used.</span></span> <span data-ttu-id="d1d44-155">%SERVER_NAME% 変数はサーバー名を指定します。</span><span class="sxs-lookup"><span data-stu-id="d1d44-155">The %SERVER_NAME% variable specifies the server name.</span></span> <span data-ttu-id="d1d44-156">この変数を変更して、使用するサーバー名を指定します。</span><span class="sxs-lookup"><span data-stu-id="d1d44-156">Change this variable to specify your own server name.</span></span> <span data-ttu-id="d1d44-157">既定値は、localhost です。</span><span class="sxs-lookup"><span data-stu-id="d1d44-157">The default value is localhost.</span></span>

    ```bat
    echo ************
    echo Server cert setup starting
    echo %SERVER_NAME%
    echo ************
    echo making server cert
    echo ************
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe
    ```

- <span data-ttu-id="d1d44-158">サーバー証明書のクライアントの信頼された証明書ストアへのインストール。</span><span class="sxs-lookup"><span data-stu-id="d1d44-158">Installing the server certificate into client's trusted certificate store.</span></span>

    <span data-ttu-id="d1d44-159">Setup.bat バッチ ファイルの次の行は、サーバー証明書をクライアントの信頼されたユーザーのストアにコピーします。</span><span class="sxs-lookup"><span data-stu-id="d1d44-159">The following lines in the Setup.bat batch file copy the server certificate into the client trusted people store.</span></span> <span data-ttu-id="d1d44-160">この手順が必要なのは、Makecert.exe によって生成される証明書がクライアント システムにより暗黙には信頼されないからです。</span><span class="sxs-lookup"><span data-stu-id="d1d44-160">This step is required because certificates that are generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="d1d44-161">マイクロソフト発行の証明書など、クライアントの信頼されたルート証明書に基づいた証明書が既にある場合は、クライアント証明書ストアにサーバー証明書を配置するこの手順は不要です。</span><span class="sxs-lookup"><span data-stu-id="d1d44-161">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft issued certificate—this step of populating the client certificate store with the server certificate is not required.</span></span>

    ```console
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople
    ```

- <span data-ttu-id="d1d44-162">クライアント証明書の作成。</span><span class="sxs-lookup"><span data-stu-id="d1d44-162">Creating the client certificate.</span></span>

    <span data-ttu-id="d1d44-163">Setup.bat バッチ ファイルの次の行は、使用するクライアント証明書を作成します。</span><span class="sxs-lookup"><span data-stu-id="d1d44-163">The following lines from the Setup.bat batch file create the client certificate to be used.</span></span> <span data-ttu-id="d1d44-164">%USER_NAME% 変数はユーザー名を指定します。</span><span class="sxs-lookup"><span data-stu-id="d1d44-164">The %USER_NAME% variable specifies the server name.</span></span> <span data-ttu-id="d1d44-165">この値は "test1" に設定されます。`IAuthorizationPolicy` によってこの名前が検索されたためです。</span><span class="sxs-lookup"><span data-stu-id="d1d44-165">This value is set to "test1" because this is the name the `IAuthorizationPolicy` looks for.</span></span> <span data-ttu-id="d1d44-166">%USER_NAME% の値を変更した場合は、`IAuthorizationPolicy.Evaluate` メソッド内の対応する値を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1d44-166">If you change the value of %USER_NAME% you must change the corresponding value in the `IAuthorizationPolicy.Evaluate` method.</span></span>

    <span data-ttu-id="d1d44-167">証明書は、CurrentUser ストアの場所の My (Personal) ストアに保存されます。</span><span class="sxs-lookup"><span data-stu-id="d1d44-167">The certificate is stored in My (Personal) store under the CurrentUser store location.</span></span>

    ```bat
    echo ************
    echo making client cert
    echo ************
    makecert.exe -sr CurrentUser -ss MY -a sha1 -n CN=%CLIENT_NAME% -sky exchange -pe
    ```

- <span data-ttu-id="d1d44-168">クライアント証明書のサーバーの信頼された証明書ストアへのインストール。</span><span class="sxs-lookup"><span data-stu-id="d1d44-168">Installing the client certificate into server's trusted certificate store.</span></span>

    <span data-ttu-id="d1d44-169">Setup.bat バッチ ファイルの次の行は、クライアント証明書を信頼されたユーザーのストアにコピーします。</span><span class="sxs-lookup"><span data-stu-id="d1d44-169">The following lines in the Setup.bat batch file copy the client certificate into the trusted people store.</span></span> <span data-ttu-id="d1d44-170">この手順が必要なのは、Makecert.exe によって生成される証明書がサーバー システムにより暗黙には信頼されないからです。</span><span class="sxs-lookup"><span data-stu-id="d1d44-170">This step is required because certificates that are generated by Makecert.exe are not implicitly trusted by the server system.</span></span> <span data-ttu-id="d1d44-171">マイクロソフト発行の証明書など、信頼されたルート証明書に基づく証明書が既にある場合は、サーバー証明書ストアにクライアント証明書を配置するこの手順は不要です。</span><span class="sxs-lookup"><span data-stu-id="d1d44-171">If you already have a certificate that is rooted in a trusted root certificate—for example, a Microsoft issued certificate—this step of populating the server certificate store with the client certificate is not required.</span></span>

    ```console
    certmgr.exe -add -r CurrentUser -s My -c -n %CLIENT_NAME% -r LocalMachine -s TrustedPeople
    ```

### <a name="to-set-up-and-build-the-sample"></a><span data-ttu-id="d1d44-172">サンプルをセットアップしてビルドするには</span><span class="sxs-lookup"><span data-stu-id="d1d44-172">To set up and build the sample</span></span>

1. <span data-ttu-id="d1d44-173">ソリューションをビルドするには、「 [Windows Communication Foundation サンプルのビルド](../../../../docs/framework/wcf/samples/building-the-samples.md)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="d1d44-173">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>

2. <span data-ttu-id="d1d44-174">サンプルを単一コンピューター構成で実行するか、複数コンピューター構成で実行するかに応じて、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="d1d44-174">To run the sample in a single- or cross-computer configuration, use the following instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="d1d44-175">Svcutil.exe を使用してこのサンプルの構成を再生成した場合は、クライアント コードに一致するように、クライアント構成内のエンドポイント名を変更してください。</span><span class="sxs-lookup"><span data-stu-id="d1d44-175">If you use Svcutil.exe to regenerate the configuration for this sample, be sure to modify the endpoint name in the client configuration to match the client code.</span></span>

### <a name="to-run-the-sample-on-the-same-computer"></a><span data-ttu-id="d1d44-176">サンプルを同じコンピューターで実行するには</span><span class="sxs-lookup"><span data-stu-id="d1d44-176">To run the sample on the same computer</span></span>

1. <span data-ttu-id="d1d44-177">管理者特権で Visual Studio の開発者コマンドプロンプトを開き、サンプルのインストールフォルダーから*setup.exe*を実行します。</span><span class="sxs-lookup"><span data-stu-id="d1d44-177">Open Developer Command Prompt for Visual Studio with administrator privileges and run *Setup.bat* from the sample install folder.</span></span> <span data-ttu-id="d1d44-178">これにより、サンプルの実行に必要なすべての証明書がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="d1d44-178">This installs all the certificates required for running the sample.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d1d44-179">セットアップの .bat バッチファイルは、Visual Studio の開発者コマンドプロンプトから実行するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="d1d44-179">The Setup.bat batch file is designed to be run from Developer Command Prompt for Visual Studio.</span></span> <span data-ttu-id="d1d44-180">Visual Studio の開発者コマンドプロンプト内で設定された PATH 環境変数は、*セットアップの .bat*スクリプトで必要な実行可能ファイルが格納されているディレクトリを指します。</span><span class="sxs-lookup"><span data-stu-id="d1d44-180">The PATH environment variable set within Developer Command Prompt for Visual Studio points to the directory that contains executables required by the *Setup.bat* script.</span></span>

1. <span data-ttu-id="d1d44-181">Service.exe を起動 *service \bin* します。</span><span class="sxs-lookup"><span data-stu-id="d1d44-181">Launch Service.exe from *service\bin*.</span></span>

1. <span data-ttu-id="d1d44-182">Client.exe を起動します *\client\bin* します。</span><span class="sxs-lookup"><span data-stu-id="d1d44-182">Launch Client.exe from *\client\bin*.</span></span> <span data-ttu-id="d1d44-183">クライアント アクティビティがクライアントのコンソール アプリケーションに表示されます。</span><span class="sxs-lookup"><span data-stu-id="d1d44-183">Client activity is displayed on the client console application.</span></span>

<span data-ttu-id="d1d44-184">クライアントとサービスが通信できない場合は、「 [WCF サンプルのトラブルシューティングのヒント](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1d44-184">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>

### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="d1d44-185">サンプルを複数のコンピューターで実行するには</span><span class="sxs-lookup"><span data-stu-id="d1d44-185">To run the sample across computers</span></span>

1. <span data-ttu-id="d1d44-186">サービス コンピューターにディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="d1d44-186">Create a directory on the service computer.</span></span>

2. <span data-ttu-id="d1d44-187">サービスプログラムファイルを *\ service\bin*からサービスコンピューターのディレクトリにコピーします。</span><span class="sxs-lookup"><span data-stu-id="d1d44-187">Copy the service program files from *\service\bin* to the directory on the service computer.</span></span> <span data-ttu-id="d1d44-188">Setup.bat、Cleanup.bat、GetComputerName.vbs、ImportClientCert.bat の各ファイルもサービス コンピューターにコピーします。</span><span class="sxs-lookup"><span data-stu-id="d1d44-188">Also copy the Setup.bat, Cleanup.bat, GetComputerName.vbs and ImportClientCert.bat files to the service computer.</span></span>

3. <span data-ttu-id="d1d44-189">クライアント コンピューターにクライアント バイナリ用のディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="d1d44-189">Create a directory on the client computer for the client binaries.</span></span>

4. <span data-ttu-id="d1d44-190">クライアント プログラム ファイルを、クライアント コンピューターに作成したクライアント ディレクトリにコピーします。</span><span class="sxs-lookup"><span data-stu-id="d1d44-190">Copy the client program files to the client directory on the client computer.</span></span> <span data-ttu-id="d1d44-191">Setup.bat、Cleanup.bat、ImportServiceCert.bat の各ファイルもクライアントにコピーします。</span><span class="sxs-lookup"><span data-stu-id="d1d44-191">Also copy the Setup.bat, Cleanup.bat, and ImportServiceCert.bat files to the client.</span></span>

5. <span data-ttu-id="d1d44-192">サーバーで、管理者`setup.bat service`特権で開いた Visual Studio の開発者コマンドプロンプトでを実行します。</span><span class="sxs-lookup"><span data-stu-id="d1d44-192">On the server, run `setup.bat service` in Developer Command Prompt for Visual Studio opened with administrator privileges.</span></span>

    <span data-ttu-id="d1d44-193">引数を指定してを実行`setup.bat`すると、コンピューターの完全修飾ドメイン名を使用してサービス証明書が作成され、service *.cer*という名前のファイルにエクスポートされます。 `service`</span><span class="sxs-lookup"><span data-stu-id="d1d44-193">Running `setup.bat` with the `service` argument creates a service certificate with the fully qualified domain name of the computer, and exports the service certificate to a file named *Service.cer*.</span></span>

6. <span data-ttu-id="d1d44-194">ServiceCertificate*を編集し*て、新しい証明書名 ( `findValue` [> の属性) を反映します。これは、コンピューターの完全修飾ドメイン名と同じです。 \<](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="d1d44-194">Edit *Service.exe.config* to reflect the new certificate name (in the `findValue` attribute in the [\<serviceCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)) which is the same as the fully qualified domain name of the computer.</span></span> <span data-ttu-id="d1d44-195">また、 \<service >/\<baseaddresses > 要素の**computername**を localhost からサービスコンピューターの完全修飾名に変更します。</span><span class="sxs-lookup"><span data-stu-id="d1d44-195">Also change the **computername** in the \<service>/\<baseAddresses> element from localhost to the fully qualified name of your service computer.</span></span>

7. <span data-ttu-id="d1d44-196">サービスの *.cer*ファイルを、サービスディレクトリからクライアントコンピューターのクライアントディレクトリにコピーします。</span><span class="sxs-lookup"><span data-stu-id="d1d44-196">Copy the *Service.cer* file from the service directory to the client directory on the client computer.</span></span>

8. <span data-ttu-id="d1d44-197">クライアントで、管理者`setup.bat client`特権で開いた Visual Studio の開発者コマンドプロンプトでを実行します。</span><span class="sxs-lookup"><span data-stu-id="d1d44-197">On the client, run `setup.bat client` in Developer Command Prompt for Visual Studio opened with administrator privileges.</span></span>

    <span data-ttu-id="d1d44-198">引数を指定してを実行`setup.bat`すると、 **test1**という名前のクライアント証明書が作成され、クライアント証明書が*クライアント .cer*という名前のファイルにエクスポートされます。 `client`</span><span class="sxs-lookup"><span data-stu-id="d1d44-198">Running `setup.bat` with the `client` argument creates a client certificate named **test1** and exports the client certificate to a file named *Client.cer*.</span></span>

9. <span data-ttu-id="d1d44-199">クライアントコンピューターの*クライアントの .exe*ファイルで、エンドポイントのアドレス値をサービスの新しいアドレスに変更します。</span><span class="sxs-lookup"><span data-stu-id="d1d44-199">In the *Client.exe.config* file on the client computer, change the address value of the endpoint to match the new address of your service.</span></span> <span data-ttu-id="d1d44-200">これを行うには、 **localhost**をサーバーの完全修飾ドメイン名に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="d1d44-200">Do this by replacing **localhost** with the fully qualified domain name of the server.</span></span>

10. <span data-ttu-id="d1d44-201">Client.cer ファイルを、クライアント ディレクトリからサーバーのサービス ディレクトリにコピーします。</span><span class="sxs-lookup"><span data-stu-id="d1d44-201">Copy the Client.cer file from the client directory to the service directory on the server.</span></span>

11. <span data-ttu-id="d1d44-202">クライアントで、管理者特権で開かれた Visual Studio の開発者コマンドプロンプトで*importservicecert.bat*を実行します。</span><span class="sxs-lookup"><span data-stu-id="d1d44-202">On the client, run *ImportServiceCert.bat* in Developer Command Prompt for Visual Studio opened with administrator privileges.</span></span>

    <span data-ttu-id="d1d44-203">これにより、サービス証明書がサービス .cer ファイルから**CurrentUser-TrustedPeople**ストアにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="d1d44-203">This imports the service certificate from the Service.cer file into the **CurrentUser - TrustedPeople** store.</span></span>

12. <span data-ttu-id="d1d44-204">サーバーで、管理者特権で開かれた Visual Studio の開発者コマンドプロンプトで*importclientcert.bat*を実行します。</span><span class="sxs-lookup"><span data-stu-id="d1d44-204">On the server, run *ImportClientCert.bat* in Developer Command Prompt for Visual Studio opened with administrator privileges.</span></span>

    <span data-ttu-id="d1d44-205">これにより、クライアント証明書がクライアント .cer ファイルから**LocalMachine-TrustedPeople**ストアにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="d1d44-205">This imports the client certificate from the Client.cer file into the **LocalMachine - TrustedPeople** store.</span></span>

13. <span data-ttu-id="d1d44-206">サーバー コンピューターで、コマンド プロンプト ウィンドウから Service.exe を起動します。</span><span class="sxs-lookup"><span data-stu-id="d1d44-206">On the server computer, launch Service.exe from the command prompt window.</span></span>

14. <span data-ttu-id="d1d44-207">クライアント コンピューターで、コマンド プロンプト ウィンドウから Client.exe を起動します。</span><span class="sxs-lookup"><span data-stu-id="d1d44-207">On the client computer, launch Client.exe from a command prompt window.</span></span>

    <span data-ttu-id="d1d44-208">クライアントとサービスが通信できない場合は、「 [WCF サンプルのトラブルシューティングのヒント](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1d44-208">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>

### <a name="clean-up-after-the-sample"></a><span data-ttu-id="d1d44-209">サンプルの後にクリーンアップする</span><span class="sxs-lookup"><span data-stu-id="d1d44-209">Clean up after the sample</span></span>

<span data-ttu-id="d1d44-210">サンプルの実行後にクリーンアップするには、サンプルの実行が完了したら、samples フォルダーで*Cleanup*を実行します。</span><span class="sxs-lookup"><span data-stu-id="d1d44-210">To clean up after the sample, run *Cleanup.bat* in the samples folder when you have finished running the sample.</span></span> <span data-ttu-id="d1d44-211">これにより、証明書ストアからサーバー証明書とクライアント証明書が削除されます。</span><span class="sxs-lookup"><span data-stu-id="d1d44-211">This removes the server and client certificates from the certificate store.</span></span>

> [!NOTE]
> <span data-ttu-id="d1d44-212">このサンプルを複数のコンピューターで実行している場合、このスクリプトはサービス証明書をクライアントから削除しません。</span><span class="sxs-lookup"><span data-stu-id="d1d44-212">This script does not remove service certificates on a client when running this sample across computers.</span></span> <span data-ttu-id="d1d44-213">コンピューター間で証明書を使用する WCF サンプルを実行している場合は、CurrentUser-TrustedPeople ストアにインストールされているサービス証明書を必ずオフにしてください。</span><span class="sxs-lookup"><span data-stu-id="d1d44-213">If you have run WCF samples that use certificates across computers, be sure to clear the service certificates that have been installed in the CurrentUser - TrustedPeople store.</span></span> <span data-ttu-id="d1d44-214">これを行うには、次のコマンドを使用します。`certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>`たとえば、の`certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`ようになります。</span><span class="sxs-lookup"><span data-stu-id="d1d44-214">To do this, use the following command: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` For example: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span></span>
