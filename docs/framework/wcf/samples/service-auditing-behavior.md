---
title: サービス監査動作
ms.date: 03/30/2017
ms.assetid: 59bf0cda-e496-4418-a3a1-2f0f6e85f8ce
ms.openlocfilehash: 6d5f254f4f94adfaeaf5632ddd696891af177e93
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964546"
---
# <a name="service-auditing-behavior"></a><span data-ttu-id="0848e-102">サービス監査動作</span><span class="sxs-lookup"><span data-stu-id="0848e-102">Service Auditing Behavior</span></span>
<span data-ttu-id="0848e-103">このサンプルでは、<xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> を使用して、サービス操作中にセキュリティ イベントの監査を有効にする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="0848e-103">This sample demonstrates how to use the <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> to enable auditing of security events during service operations.</span></span> <span data-ttu-id="0848e-104">このサンプルは、[はじめに](../../../../docs/framework/wcf/samples/getting-started-sample.md)に基づいています。</span><span class="sxs-lookup"><span data-stu-id="0848e-104">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span> <span data-ttu-id="0848e-105">サービスとクライアントは、 [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)を使用して構成されています。</span><span class="sxs-lookup"><span data-stu-id="0848e-105">The service and client have been configured using the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span></span> <span data-ttu-id="0848e-106">`Message` `Windows`セキュリティ>`clientCredentialType` [の属性がに設定され、がに設定されています。 \<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) `mode`</span><span class="sxs-lookup"><span data-stu-id="0848e-106">The `mode` attribute of the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) has been set to `Message` and `clientCredentialType` has been set to `Windows`.</span></span> <span data-ttu-id="0848e-107">この例では、クライアントはコンソール アプリケーション (.exe) であり、サービスはインターネット インフォメーション サービス (IIS) によってホストされます。</span><span class="sxs-lookup"><span data-stu-id="0848e-107">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0848e-108">このサンプルのセットアップ手順とビルド手順については、このトピックの最後を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0848e-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="0848e-109">サービス構成ファイルは、次のように `serviceSecurityAudit` 要素を使用して監査を構成します。</span><span class="sxs-lookup"><span data-stu-id="0848e-109">The service configuration file uses the `serviceSecurityAudit` element to configure auditing.</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="CalculatorServiceBehavior">  
      ...  
<!-- serviceSecurityAudit allows specification of audit location   
     and whether to audit success, failure or both. This service   
     logs success and failure of messageAuthentication   
     to the default location -->  
     <serviceSecurityAudit auditLogLocation ="Default" messageAuthenticationAuditLevel = "SuccessOrFailure" />  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 <span data-ttu-id="0848e-110">このサンプルを実行すると、操作要求および応答がクライアントのコンソール ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="0848e-110">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="0848e-111">クライアントをシャットダウンするには、コンソール ウィンドウで Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="0848e-111">Press ENTER in the console window to shut down the client.</span></span>  
  
 <span data-ttu-id="0848e-112">結果として得られる監査ログは、イベント ビューアーを実行して表示できます。</span><span class="sxs-lookup"><span data-stu-id="0848e-112">The resulting audit logs can be seen by running the Event Viewer.</span></span> <span data-ttu-id="0848e-113">監査イベントは既定で、Windows XP の場合はアプリケーション ログに、Windows Server 2003 と Windows Vista の場合はセキュリティ ログに表示されます。</span><span class="sxs-lookup"><span data-stu-id="0848e-113">By default, on Windows XP the audit events can be seen in the Application Log while on Windows Server 2003 and Windows Vista, the audit events can be seen in the Security Log.</span></span> <span data-ttu-id="0848e-114">Windows Server 2008 と Windows 7 では、監査イベントをアプリケーション ログとサービス ログに表示できます。</span><span class="sxs-lookup"><span data-stu-id="0848e-114">On Windows Server 2008 and Windows 7, the audit events can be seen in the Applications and Services logs.</span></span> <span data-ttu-id="0848e-115">監査イベントの場所は、 `auditLogLocation`属性を "Application" または "Security" に設定することによって指定できます。</span><span class="sxs-lookup"><span data-stu-id="0848e-115">The location of audit events can be specified by setting the `auditLogLocation` attribute to "Application" or "Security".</span></span> <span data-ttu-id="0848e-116">詳細については、「[方法 :セキュリティイベント](../../../../docs/framework/wcf/feature-details/how-to-audit-wcf-security-events.md)を監査します。</span><span class="sxs-lookup"><span data-stu-id="0848e-116">For more information, see [How to: Audit Security Events](../../../../docs/framework/wcf/feature-details/how-to-audit-wcf-security-events.md).</span></span> <span data-ttu-id="0848e-117">イベントがセキュリティログに書き込まれる場合は、LocalSecurityPolicy-> Enable オブジェクトアクセスを "Success" と "Failure" に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0848e-117">If the events are written in the Security Log the LocalSecurityPolicy-> Enable Object Access should be set for "Success" and "Failure".</span></span>  
  
 <span data-ttu-id="0848e-118">イベント ログを調べる場合、監査イベントのソースは "ServiceModel Audit 3.0.0.0" です。</span><span class="sxs-lookup"><span data-stu-id="0848e-118">When looking at the event log, the source of the audit events is "ServiceModel Audit 3.0.0.0".</span></span> <span data-ttu-id="0848e-119">メッセージ認証監査レコードには "MessageAuthentication" のカテゴリがありますが、サービス承認監査レコードには "ServiceAuthorization" のカテゴリがあります。</span><span class="sxs-lookup"><span data-stu-id="0848e-119">Message authentication audit records have a category of "MessageAuthentication" while service authorization audit records have a category of "ServiceAuthorization".</span></span>  
  
 <span data-ttu-id="0848e-120">メッセージ認証監査イベントは、メッセージの改ざんや期限切れの有無、クライアントによるサービス認証の成否などに適用されます。</span><span class="sxs-lookup"><span data-stu-id="0848e-120">Message authentication audit events cover whether the message was tampered with, whether the message has expired, and whether the client can authenticate to the service.</span></span> <span data-ttu-id="0848e-121">このイベントでは、認証の成功または失敗に関する情報とクライアント ID、およびメッセージ送信先のエンドポイントとそのメッセージに関連付けられたアクションに関する情報が提供されます。</span><span class="sxs-lookup"><span data-stu-id="0848e-121">They provide information about whether the authentication succeeded or failed along with the identity of the client, and the endpoint the message was sent to along with the action associated with the message.</span></span>  
  
 <span data-ttu-id="0848e-122">サービス承認監査イベントは、サービス承認マネージャーによって決定される承認に適用されます。</span><span class="sxs-lookup"><span data-stu-id="0848e-122">Service authorization audit events cover the authorization decision made by a service authorization manager.</span></span> <span data-ttu-id="0848e-123">このイベントでは、承認の成功または失敗に関する情報とクライアント ID、メッセージ送信先のエンドポイント、そのメッセージに関連付けられたアクション、受信メッセージから生成された承認コンテキストの ID、およびアクセス決定を行った承認マネージャーの種類に関する情報が提供されます。</span><span class="sxs-lookup"><span data-stu-id="0848e-123">They provide information about whether authorization succeeded or failed along with the identity of the client, the endpoint the message was sent to, the action associated with the message, the identifier of the authorization context that was generated from the incoming message, and the type of the authorization manager that made the access decision.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="0848e-124">サンプルをセットアップ、ビルド、および実行するには</span><span class="sxs-lookup"><span data-stu-id="0848e-124">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="0848e-125">[Windows Communication Foundation サンプルの1回限りのセットアップ手順](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)を実行したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="0848e-125">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="0848e-126">ソリューションの C# 版または Visual Basic .NET 版をビルドするには、「 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="0848e-126">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="0848e-127">サンプルを単一コンピューター構成または複数コンピューター構成で実行するには、「 [Windows Communication Foundation サンプルの実行](../../../../docs/framework/wcf/samples/running-the-samples.md)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="0848e-127">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0848e-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="0848e-128">See also</span></span>

- [<span data-ttu-id="0848e-129">監査</span><span class="sxs-lookup"><span data-stu-id="0848e-129">Auditing</span></span>](../../../../docs/framework/wcf/feature-details/auditing-security-events.md)
- [<span data-ttu-id="0848e-130">方法: セキュリティイベントの監査</span><span class="sxs-lookup"><span data-stu-id="0848e-130">How to: Audit Security Events</span></span>](../../../../docs/framework/wcf/feature-details/how-to-audit-wcf-security-events.md)
