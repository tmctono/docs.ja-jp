---
title: '方法 : Windows Communication Foundation セキュリティ イベントを監査する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [WCF], auditing events
ms.assetid: e71e9587-3336-46a2-9a9e-d72a1743ecec
ms.openlocfilehash: 62d26b24b5d46427c1871fccf48b063c45781beb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185125"
---
# <a name="how-to-audit-windows-communication-foundation-security-events"></a><span data-ttu-id="6a8d2-102">方法 : Windows Communication Foundation セキュリティ イベントを監査する</span><span class="sxs-lookup"><span data-stu-id="6a8d2-102">How to: Audit Windows Communication Foundation Security Events</span></span>
<span data-ttu-id="6a8d2-103">Windows 通信基盤 (WCF) では、Windows イベント ビューアーを使用して表示できる Windows イベント ログにセキュリティ イベントを記録できます。</span><span class="sxs-lookup"><span data-stu-id="6a8d2-103">Windows Communication Foundation (WCF) allows you to log security events to the Windows event log, which can be viewed using the Windows Event Viewer.</span></span> <span data-ttu-id="6a8d2-104">このトピックでは、セキュリティ イベントをログ出力するようにアプリケーションを設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6a8d2-104">This topic explains how to set up an application so that it logs security events.</span></span> <span data-ttu-id="6a8d2-105">WCF 監査の詳細については、「[監査](../../../../docs/framework/wcf/feature-details/auditing-security-events.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a8d2-105">For more information about WCF auditing, see [Auditing](../../../../docs/framework/wcf/feature-details/auditing-security-events.md).</span></span>  
  
### <a name="to-audit-security-events-in-code"></a><span data-ttu-id="6a8d2-106">セキュリティ イベントを監査するコードを記述するには</span><span class="sxs-lookup"><span data-stu-id="6a8d2-106">To audit security events in code</span></span>  
  
1. <span data-ttu-id="6a8d2-107">監査ログの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="6a8d2-107">Specify the audit log location.</span></span> <span data-ttu-id="6a8d2-108">それには、次のコードに示すように、<xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.AuditLogLocation%2A> クラスの <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> プロパティに <xref:System.ServiceModel.AuditLogLocation> 列挙体のいずれかの値を設定します。</span><span class="sxs-lookup"><span data-stu-id="6a8d2-108">To do this, set the <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.AuditLogLocation%2A> property of the <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> class to one of the <xref:System.ServiceModel.AuditLogLocation> enumeration values, as shown in the following code.</span></span>  
  
     [!code-csharp[AuditingSecurityEvents#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/auditingsecurityevents/cs/auditingsecurityevents.cs#2)]
     [!code-vb[AuditingSecurityEvents#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/auditingsecurityevents/vb/auditingsecurityevents.vb#2)]  
  
     <span data-ttu-id="6a8d2-109">列挙<xref:System.ServiceModel.AuditLogLocation>体には、 、 `Application` `Security`、 `Default`、または の 3 つの値があります。</span><span class="sxs-lookup"><span data-stu-id="6a8d2-109">The <xref:System.ServiceModel.AuditLogLocation> enumeration has three values: `Application`, `Security`, or `Default`.</span></span> <span data-ttu-id="6a8d2-110">これは、イベント ビューアーを開いたとき、セキュリティ ログとアプリケーション ログのどちらが表示されるかを表します。</span><span class="sxs-lookup"><span data-stu-id="6a8d2-110">The value specifies one of the logs visible in the Event Viewer, either the Security log or the Application log.</span></span> <span data-ttu-id="6a8d2-111">`Default` を指定した場合の動作は、アプリケーションが稼働するオペレーティング システムに依存します。</span><span class="sxs-lookup"><span data-stu-id="6a8d2-111">If you use the `Default` value, the actual log will depend on the operating system the application is running on.</span></span> <span data-ttu-id="6a8d2-112">ログの場所を指定せずに監査機能を有効にした場合、セキュリティ ログに書き込み可能なプラットフォームであれば `Security` ログに、そうでなければ `Application` ログに出力するようになります。</span><span class="sxs-lookup"><span data-stu-id="6a8d2-112">If auditing is enabled and the log location is not specified, the default is the `Security` log for platforms that support writing to the Security log; otherwise, it will write to the `Application` log.</span></span> <span data-ttu-id="6a8d2-113">既定では、セキュリティ ログへの書き込みがサポートされているのは Windows Server 2003 および Windows Vista だけです。</span><span class="sxs-lookup"><span data-stu-id="6a8d2-113">Only Windows Server 2003 and Windows Vista support writing to the Security log by default.</span></span>  
  
2. <span data-ttu-id="6a8d2-114">イベントの種類を監査対象として設定します。</span><span class="sxs-lookup"><span data-stu-id="6a8d2-114">Set up the types of events to audit.</span></span> <span data-ttu-id="6a8d2-115">サービス レベルのイベントとメッセージ レベルの承認イベントを同時に監査できます。</span><span class="sxs-lookup"><span data-stu-id="6a8d2-115">You can simultaneously audit service-level events or message-level authorization events.</span></span> <span data-ttu-id="6a8d2-116">それには、次のコードに示すように、<xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.ServiceAuthorizationAuditLevel%2A> プロパティまたは <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.MessageAuthenticationAuditLevel%2A> プロパティに <xref:System.ServiceModel.AuditLevel> 列挙体のいずれかの値を設定します。</span><span class="sxs-lookup"><span data-stu-id="6a8d2-116">To do this, set the <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.ServiceAuthorizationAuditLevel%2A> property or the <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.MessageAuthenticationAuditLevel%2A> property to one of the <xref:System.ServiceModel.AuditLevel> enumeration values, as shown in the following code.</span></span>  
  
     [!code-csharp[AuditingSecurityEvents#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/auditingsecurityevents/cs/auditingsecurityevents.cs#3)]
     [!code-vb[AuditingSecurityEvents#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/auditingsecurityevents/vb/auditingsecurityevents.vb#3)]  
  
3. <span data-ttu-id="6a8d2-117">ログ監査イベントに関して、単に無視してアプリケーションの処理を続行するか、それとも失敗を通知するかを設定します。</span><span class="sxs-lookup"><span data-stu-id="6a8d2-117">Specify whether to suppress or expose failures to the application regarding log audit events.</span></span> <span data-ttu-id="6a8d2-118">次のコードに示すように、<xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.SuppressAuditFailure%2A> プロパティに `true` または `false` を設定します。</span><span class="sxs-lookup"><span data-stu-id="6a8d2-118">Set the <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.SuppressAuditFailure%2A> property to either `true` or `false`, as shown in the following code.</span></span>  
  
     [!code-csharp[AuditingSecurityEvents#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/auditingsecurityevents/cs/auditingsecurityevents.cs#4)]
     [!code-vb[AuditingSecurityEvents#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/auditingsecurityevents/vb/auditingsecurityevents.vb#4)]  
  
     <span data-ttu-id="6a8d2-119">`SuppressAuditFailure` プロパティの既定値は `true` なので、監査に失敗してもアプリケーションには影響しません。</span><span class="sxs-lookup"><span data-stu-id="6a8d2-119">The default `SuppressAuditFailure` property is `true`, so that the failure to audit does not affect the application.</span></span> <span data-ttu-id="6a8d2-120">それ以外の場合は、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="6a8d2-120">Otherwise, an exception is thrown.</span></span> <span data-ttu-id="6a8d2-121">正常な監査に関するログは、Verbose レベルで出力されます。</span><span class="sxs-lookup"><span data-stu-id="6a8d2-121">For any successful audit, a verbose trace is written.</span></span> <span data-ttu-id="6a8d2-122">異常発生時には、Error レベルでトレースが出力されます。</span><span class="sxs-lookup"><span data-stu-id="6a8d2-122">For any failure to audit, the trace is written at the Error level.</span></span>  
  
4. <span data-ttu-id="6a8d2-123">既存の <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> を、<xref:System.ServiceModel.ServiceHost> の説明にある動作のコレクションから削除します。</span><span class="sxs-lookup"><span data-stu-id="6a8d2-123">Delete the existing <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> from the collection of behaviors found in the description of a <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="6a8d2-124">動作のコレクションは、<xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> プロパティからアクセスできます。また、<xref:System.ServiceModel.ServiceHostBase.Description%2A> プロパティからもアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="6a8d2-124">The behavior collection is accessed by the <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> property, which in turn is accessed from the <xref:System.ServiceModel.ServiceHostBase.Description%2A> property.</span></span> <span data-ttu-id="6a8d2-125">その後、次のコードに示すように、新しい <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> を同じコレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="6a8d2-125">Then add the new <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> to the same collection, as shown in the following code.</span></span>  
  
     [!code-csharp[AuditingSecurityEvents#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/auditingsecurityevents/cs/auditingsecurityevents.cs#5)]
     [!code-vb[AuditingSecurityEvents#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/auditingsecurityevents/vb/auditingsecurityevents.vb#5)]  
  
### <a name="to-set-up-auditing-in-configuration"></a><span data-ttu-id="6a8d2-126">構成ファイルで監査を設定するには</span><span class="sxs-lookup"><span data-stu-id="6a8d2-126">To set up auditing in configuration</span></span>  
  
1. <span data-ttu-id="6a8d2-127">構成で監査を設定するには、web.config ファイル[\<の](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)[\<動作>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)セクションに動作>要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="6a8d2-127">To set up auditing in configuration, add a [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) element to the [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) section of the web.config file.</span></span> <span data-ttu-id="6a8d2-128">次に、[\<](../../../../docs/framework/configure-apps/file-schema/wcf/servicesecurityaudit.md)次の例に示すように、要素>を追加し、さまざまな属性を設定します。</span><span class="sxs-lookup"><span data-stu-id="6a8d2-128">Then add a [\<serviceSecurityAudit>](../../../../docs/framework/configure-apps/file-schema/wcf/servicesecurityaudit.md) element and set the various attributes, as shown in the following example.</span></span>  
  
    ```xml  
    <behaviors>  
       <behavior name="myAuditBehavior">  
          <serviceSecurityAudit auditLogLocation="Application"  
                suppressAuditFailure="false"
                serviceAuthorizationAuditLevel="None"
                messageAuthenticationAuditLevel="SuccessOrFailure" />  
          </behavior>  
    </behaviors>  
    ```  
  
2. <span data-ttu-id="6a8d2-129">次の例に示すように、サービスに対して動作を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a8d2-129">You must specify the behavior for the service, as shown in the following example.</span></span>  
  
    ```xml  
    <services>  
        <service type="WCS.Samples.Service.Echo"
        behaviorConfiguration=" myAuditBehavior">  
           <endpoint address=""  
                    binding="wsHttpBinding"  
                    bindingConfiguration="CertificateDefault"
                    contract="WCS.Samples.Service.IEcho" />  
        </service>  
    </services>  
    ```  
  
## <a name="example"></a><span data-ttu-id="6a8d2-130">例</span><span class="sxs-lookup"><span data-stu-id="6a8d2-130">Example</span></span>  
 <span data-ttu-id="6a8d2-131"><xref:System.ServiceModel.ServiceHost> クラスのインスタンスを作成し、新しい <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> をその動作のコレクションに追加するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="6a8d2-131">The following code creates an instance of the <xref:System.ServiceModel.ServiceHost> class and adds a new <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> to its collection of behaviors.</span></span>  
  
 [!code-csharp[AuditingSecurityEvents#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/auditingsecurityevents/cs/auditingsecurityevents.cs#1)]
 [!code-vb[AuditingSecurityEvents#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/auditingsecurityevents/vb/auditingsecurityevents.vb#1)]  
  
## <a name="net-framework-security"></a><span data-ttu-id="6a8d2-132">.NET Framework のセキュリティ</span><span class="sxs-lookup"><span data-stu-id="6a8d2-132">.NET Framework Security</span></span>  
 <span data-ttu-id="6a8d2-133"><xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.SuppressAuditFailure%2A> プロパティを `true` に設定すると、セキュリティ監査を生成する失敗が抑制されます (`false` に設定した場合は、例外がスローされます)。</span><span class="sxs-lookup"><span data-stu-id="6a8d2-133">Setting the <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.SuppressAuditFailure%2A> property to `true`, suppresses any failure to generate security audits (if set to `false`, an exception is thrown).</span></span> <span data-ttu-id="6a8d2-134">ただし、次の [ローカル**セキュリティ設定]** プロパティを有効にすると、監査イベントの生成に失敗すると、Windows が直ちにシャットダウンします。</span><span class="sxs-lookup"><span data-stu-id="6a8d2-134">However, if you enable the following Windows **Local Security Setting** property, a failure to generate audit events will cause Windows to shut down immediately:</span></span>  
  
 <span data-ttu-id="6a8d2-135">**監査: セキュリティ監査のログを記録できない場合は直ちにシステムをシャットダウンする**</span><span class="sxs-lookup"><span data-stu-id="6a8d2-135">**Audit: Shut down system immediately if unable to log security audits**</span></span>  
  
 <span data-ttu-id="6a8d2-136">プロパティを設定するには、[ローカル**セキュリティ設定]** ダイアログ ボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="6a8d2-136">To set the property, open the **Local Security Settings** dialog box.</span></span> <span data-ttu-id="6a8d2-137">[**セキュリティの設定**] の [**ローカル ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6a8d2-137">Under **Security Settings**, click **Local Policies**.</span></span> <span data-ttu-id="6a8d2-138">次に、[**セキュリティ オプション]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6a8d2-138">Then click **Security Options**.</span></span>  
  
 <span data-ttu-id="6a8d2-139">プロパティが<xref:System.ServiceModel.AuditLogLocation>に<xref:System.ServiceModel.AuditLogLocation.Security>設定され、**オブジェクト アクセスの監査**がローカル セキュリティ**ポリシー**で設定されていない場合、監査イベントはセキュリティ ログに書き込まれません。</span><span class="sxs-lookup"><span data-stu-id="6a8d2-139">If the <xref:System.ServiceModel.AuditLogLocation> property is set to <xref:System.ServiceModel.AuditLogLocation.Security> and **Audit Object Access** is not set in the **Local Security Policy**, audit events will not be written to the Security log.</span></span> <span data-ttu-id="6a8d2-140">エラーが返らない場合でも、監査エントリはセキュリティ ログに書き込まれません。</span><span class="sxs-lookup"><span data-stu-id="6a8d2-140">Note that no failure is returned, but audit entries are not written to the Security log.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a8d2-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="6a8d2-141">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.AuditLogLocation%2A>
- <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>
- <xref:System.ServiceModel.AuditLogLocation>
- [<span data-ttu-id="6a8d2-142">監査</span><span class="sxs-lookup"><span data-stu-id="6a8d2-142">Auditing</span></span>](../../../../docs/framework/wcf/feature-details/auditing-security-events.md)
