---
title: <serviceSecurityAudit>
ms.date: 03/30/2017
ms.assetid: ba517369-a034-4f8e-a2c4-66517716062b
ms.openlocfilehash: 10888f26053014ffb1fec49d1dfe87c7fd09ab54
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399575"
---
# \<serviceSecurityAudit>
<span data-ttu-id="53814-101">サービス操作中にセキュリティ イベントの監査を有効にする設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="53814-101">Specifies settings that enable auditing of security events during service operations.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceSecurityAudit>**  
  
## <a name="syntax"></a><span data-ttu-id="53814-102">構文</span><span class="sxs-lookup"><span data-stu-id="53814-102">Syntax</span></span>  
  
```xml  
<serviceSecurityAudit auditLogLocation="Default/Application/Security"
                      messageAuthenticationAuditLevel="None/Success/Failure/SuccessOrFailure"
                      serviceAuthorizationAuditLevel="None/Success/Failure/SuccessOrFailure"
                      suppressAuditFailure="Boolean" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="53814-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="53814-103">Attributes and Elements</span></span>  
 <span data-ttu-id="53814-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="53814-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="53814-105">属性</span><span class="sxs-lookup"><span data-stu-id="53814-105">Attributes</span></span>  
  
|<span data-ttu-id="53814-106">属性</span><span class="sxs-lookup"><span data-stu-id="53814-106">Attribute</span></span>|<span data-ttu-id="53814-107">説明</span><span class="sxs-lookup"><span data-stu-id="53814-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="53814-108">auditLogLocation</span><span class="sxs-lookup"><span data-stu-id="53814-108">auditLogLocation</span></span>|<span data-ttu-id="53814-109">監査ログの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="53814-109">Specifies the location of the audit log.</span></span> <span data-ttu-id="53814-110">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="53814-110">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="53814-111">-既定: セキュリティイベントは、windows XP の場合はアプリケーションログに、windows Server 2003 および Windows Vista の場合はイベントログに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="53814-111">-   Default: Security events are written to the application log on Windows XP, and to the Event Log on Windows Server 2003 and Windows Vista.</span></span><br /><span data-ttu-id="53814-112">-Application: 監査イベントは、アプリケーションイベントログに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="53814-112">-   Application: Audit events are written to the Application Event Log.</span></span><br /><span data-ttu-id="53814-113">-Security: 監査イベントは、セキュリティイベントログに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="53814-113">-   Security: Audit events are written to the Security Event Log.</span></span><br /><br /> <span data-ttu-id="53814-114">既定値は Default です。</span><span class="sxs-lookup"><span data-stu-id="53814-114">The default value is Default.</span></span> <span data-ttu-id="53814-115">詳細については、「<xref:System.ServiceModel.AuditLogLocation>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="53814-115">For more information, see <xref:System.ServiceModel.AuditLogLocation>.</span></span>|  
|<span data-ttu-id="53814-116">suppressAuditFailure</span><span class="sxs-lookup"><span data-stu-id="53814-116">suppressAuditFailure</span></span>|<span data-ttu-id="53814-117">監査ログへの書き込みエラーを非表示にする動作を指定します。</span><span class="sxs-lookup"><span data-stu-id="53814-117">A Boolean value that specifies the behavior for suppressing failures of writing to the audit log.</span></span><br /><br /> <span data-ttu-id="53814-118">アプリケーションには、監査ログへの書き込みエラーを通知する必要があります。</span><span class="sxs-lookup"><span data-stu-id="53814-118">Applications should be notified for failures of writing to the audit log.</span></span> <span data-ttu-id="53814-119">アプリケーションが監査エラーを処理するように設計されていない場合は、この属性を使用して、監査ログへの書き込みでのエラーが表示されないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="53814-119">If your application is not designed to handle audit failures, you should use this attribute to suppress failures in writing to the audit log.</span></span><br /><br /> <span data-ttu-id="53814-120">この属性が `true` の場合、監査イベントの書き込み試行の結果発生する例外 (ただし、OutOfMemoryException、StackOverFlowException、ThreadAbortException、および ArgumentException を除く) はシステムによって処理され、アプリケーションには伝達されません。</span><span class="sxs-lookup"><span data-stu-id="53814-120">If this attribute is `true`, exceptions other than OutOfMemoryException, StackOverFlowException, ThreadAbortException, and ArgumentException that result from attempts to write audit events are handled by the system, and are not propagated to the application.</span></span> <span data-ttu-id="53814-121">この属性が `false` の場合、監査イベントの書き込み試行の結果発生する例外は、すべてアプリケーションまで渡されます。</span><span class="sxs-lookup"><span data-stu-id="53814-121">If this attribute is `false`, all exceptions that result from attempts to write audit events are passed up to the application.</span></span><br /><br /> <span data-ttu-id="53814-122">既定値は、`true` です。</span><span class="sxs-lookup"><span data-stu-id="53814-122">The default is `true`.</span></span>|  
|<span data-ttu-id="53814-123">serviceAuthorizationAuditLevel</span><span class="sxs-lookup"><span data-stu-id="53814-123">serviceAuthorizationAuditLevel</span></span>|<span data-ttu-id="53814-124">監査ログに記録される承認イベントの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="53814-124">Specifies the types of authorization events that are recorded in the audit log.</span></span> <span data-ttu-id="53814-125">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="53814-125">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="53814-126">-None: サービス承認イベントの監査は実行されません。</span><span class="sxs-lookup"><span data-stu-id="53814-126">-   None: No auditing of service authorization events is performed.</span></span><br /><span data-ttu-id="53814-127">-Success: 成功したサービス承認イベントだけが監査されます。</span><span class="sxs-lookup"><span data-stu-id="53814-127">-   Success: Only successful service authorization events are audited.</span></span><br /><span data-ttu-id="53814-128">-Failure: 失敗したサービス承認イベントだけが監査されます。</span><span class="sxs-lookup"><span data-stu-id="53814-128">-   Failure: Only failure service authorization events are audited.</span></span><br /><span data-ttu-id="53814-129">-SuccessOrFailure: 成功と失敗の両方のサービス承認イベントが監査されます。</span><span class="sxs-lookup"><span data-stu-id="53814-129">-   SuccessOrFailure: Both success and failure service authorization events are audited.</span></span><br /><br /> <span data-ttu-id="53814-130">既定値は None です。</span><span class="sxs-lookup"><span data-stu-id="53814-130">The default value is None.</span></span> <span data-ttu-id="53814-131">詳細については、「<xref:System.ServiceModel.AuditLevel>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="53814-131">For more information, see <xref:System.ServiceModel.AuditLevel>.</span></span>|  
|<span data-ttu-id="53814-132">messageAuthenticationAuditLevel</span><span class="sxs-lookup"><span data-stu-id="53814-132">messageAuthenticationAuditLevel</span></span>|<span data-ttu-id="53814-133">ログに記録されるメッセージ認証監査イベントの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="53814-133">Specifies the type of message authentication audit events logged.</span></span> <span data-ttu-id="53814-134">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="53814-134">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="53814-135">-None: 監査イベントは生成されません。</span><span class="sxs-lookup"><span data-stu-id="53814-135">-   None: No audit events are generated.</span></span><br /><span data-ttu-id="53814-136">-Success: 成功したセキュリティ (メッセージ署名の検証、暗号、トークンの検証を含む完全な検証) イベントのみが記録されます。</span><span class="sxs-lookup"><span data-stu-id="53814-136">-   Success: Only successful security (full validation including message signature validation, cipher, and token validation) events are logged.</span></span><br /><span data-ttu-id="53814-137">-Failure: エラーイベントのみがログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="53814-137">-   Failure: Only failure events are logged.</span></span><br /><span data-ttu-id="53814-138">-SuccessOrFailure: 成功イベントと失敗イベントの両方がログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="53814-138">-   SuccessOrFailure: Both success and failure events are logged.</span></span><br /><br /> <span data-ttu-id="53814-139">既定値は None です。</span><span class="sxs-lookup"><span data-stu-id="53814-139">The default value is None.</span></span> <span data-ttu-id="53814-140">詳細については、「<xref:System.ServiceModel.AuditLevel>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="53814-140">For more information, see <xref:System.ServiceModel.AuditLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="53814-141">子要素</span><span class="sxs-lookup"><span data-stu-id="53814-141">Child Elements</span></span>  
 <span data-ttu-id="53814-142">なし。</span><span class="sxs-lookup"><span data-stu-id="53814-142">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="53814-143">親要素</span><span class="sxs-lookup"><span data-stu-id="53814-143">Parent Elements</span></span>  
  
|<span data-ttu-id="53814-144">要素</span><span class="sxs-lookup"><span data-stu-id="53814-144">Element</span></span>|<span data-ttu-id="53814-145">Description</span><span class="sxs-lookup"><span data-stu-id="53814-145">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="53814-146">動作の要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="53814-146">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="53814-147">解説</span><span class="sxs-lookup"><span data-stu-id="53814-147">Remarks</span></span>  
 <span data-ttu-id="53814-148">この構成要素は、Windows Communication Foundation (WCF) 認証イベントを監査するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="53814-148">This configuration element is used to audit Windows Communication Foundation (WCF) authentication events.</span></span> <span data-ttu-id="53814-149">監査を有効にすると、成功した認証、失敗した認証、またはその両方を監査できます。</span><span class="sxs-lookup"><span data-stu-id="53814-149">When auditing is enabled, either successful or failed authentication attempts (or both) can be audited.</span></span> <span data-ttu-id="53814-150">イベントは、3 種類のイベント ログ (アプリケーション ログ、セキュリティ ログ、およびオペレーティング システムのバージョンに対する既定のログ) のいずれかに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="53814-150">The events are written to one of three event logs: application, security, or the default log for the operating system version.</span></span> <span data-ttu-id="53814-151">イベント ログはすべて、Windows イベント ビューアーを使用して表示できます。</span><span class="sxs-lookup"><span data-stu-id="53814-151">The event logs can all be viewed using the Windows Event viewer.</span></span>  
  
 <span data-ttu-id="53814-152">この構成要素の使用例については、「[サービス監査の動作](../../../wcf/samples/service-auditing-behavior.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="53814-152">For a detailed example of using this configuration element, see [Service Auditing Behavior](../../../wcf/samples/service-auditing-behavior.md).</span></span>  
  
 <span data-ttu-id="53814-153">監査イベントは既定で、Windows XP の場合はアプリケーション ログに、Windows Server 2003 と Windows Vista の場合はセキュリティ ログに表示されます。</span><span class="sxs-lookup"><span data-stu-id="53814-153">By default, on Windows XP the audit events can be seen in the Application Log; while on Windows Server 2003 and Windows Vista, the audit events can be seen in the Security Log.</span></span> <span data-ttu-id="53814-154">監査イベントの場所は、`auditLogLocation` 属性を "Application" または "Security" に設定することによって指定できます。</span><span class="sxs-lookup"><span data-stu-id="53814-154">The location of audit events can be specified by setting the `auditLogLocation` attribute to 'Application' or 'Security'.</span></span> <span data-ttu-id="53814-155">詳細については、「[方法: セキュリティイベントを監査](../../../wcf/feature-details/how-to-audit-wcf-security-events.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="53814-155">For more information, see [How to: Audit Security Events](../../../wcf/feature-details/how-to-audit-wcf-security-events.md).</span></span> <span data-ttu-id="53814-156">イベントがセキュリティログに書き込まれた場合は、LocalSecurityPolicy-> Enable オブジェクトアクセスを "Success" と "Failure" に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="53814-156">If the events are written in the Security Log, the LocalSecurityPolicy-> Enable Object Access should be set for "Success" and "Failure".</span></span>  
  
 <span data-ttu-id="53814-157">イベント ログを調べる場合、監査イベントのソースは "ServiceModel Audit 3.0.0.0" です。</span><span class="sxs-lookup"><span data-stu-id="53814-157">When looking at the event log, the source of the audit events is "ServiceModel Audit 3.0.0.0".</span></span> <span data-ttu-id="53814-158">メッセージ認証監査レコードには "MessageAuthentication" のカテゴリ、サービス承認監査レコードには "ServiceAuthorization" のカテゴリが設定されます。</span><span class="sxs-lookup"><span data-stu-id="53814-158">Message authentication audit records have a category of "MessageAuthentication" while service authorization audit records have a category of 'ServiceAuthorization'.</span></span>  
  
 <span data-ttu-id="53814-159">メッセージ認証監査イベントは、メッセージの改ざんや期限切れの有無、クライアントによるサービス認証の成否などに適用されます。</span><span class="sxs-lookup"><span data-stu-id="53814-159">Message authentication audit events cover whether the message was tampered with, whether the message has expired and whether the client can authenticate to the service.</span></span> <span data-ttu-id="53814-160">このイベントでは、認証の成功または失敗に関する情報とクライアント ID、およびメッセージ送信先のエンドポイントとそのメッセージに関連付けられたアクションに関する情報が提供されます。</span><span class="sxs-lookup"><span data-stu-id="53814-160">They provide information about whether the authentication succeeded or failed along with the identity of the client and the endpoint the message was sent to along with the action associated with the message.</span></span>  
  
 <span data-ttu-id="53814-161">サービス承認監査イベントは、サービス承認マネージャーによって決定される承認に適用されます。</span><span class="sxs-lookup"><span data-stu-id="53814-161">Service authorization audit events cover the authorization decision made by a service authorization manager.</span></span> <span data-ttu-id="53814-162">これらの情報は、承認が成功したか失敗したか、クライアントの id、メッセージが送信されたエンドポイント、メッセージに関連付けられたアクション、受信メッセージから生成された承認コンテキストの識別子、およびアクセス決定を行った承認マネージャーの種類に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="53814-162">They provide information about whether authorization succeeded or failed along with the identity of the client, the endpoint the message was sent to, the action associated with the message, the identifier of the authorization context that was generated from the incoming message and the type of the authorization manager that made the access decision.</span></span>  
  
## <a name="example"></a><span data-ttu-id="53814-163">例</span><span class="sxs-lookup"><span data-stu-id="53814-163">Example</span></span>  
  
```xml  
<system.serviceModel>
  <behaviors>
    <serviceBehaviors>
      <behavior name="NewBehavior">
        <serviceSecurityAudit auditLogLocation="Application"
                              suppressAuditFailure="true"
                              serviceAuthorizationAuditLevel="Success"
                              messageAuthenticationAuditLevel="Success" />
      </behavior>
    </serviceBehaviors>
  </behaviors>
</system.serviceModel>
```  
  
## <a name="see-also"></a><span data-ttu-id="53814-164">関連項目</span><span class="sxs-lookup"><span data-stu-id="53814-164">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceSecurityAuditElement>
- <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>
- [<span data-ttu-id="53814-165">セキュリティ動作</span><span class="sxs-lookup"><span data-stu-id="53814-165">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="53814-166">監査</span><span class="sxs-lookup"><span data-stu-id="53814-166">Auditing</span></span>](../../../wcf/feature-details/auditing-security-events.md)
- [<span data-ttu-id="53814-167">方法: セキュリティ イベントを監査する</span><span class="sxs-lookup"><span data-stu-id="53814-167">How to: Audit Security Events</span></span>](../../../wcf/feature-details/how-to-audit-wcf-security-events.md)
- [<span data-ttu-id="53814-168">サービス監査動作</span><span class="sxs-lookup"><span data-stu-id="53814-168">Service Auditing Behavior</span></span>](../../../wcf/samples/service-auditing-behavior.md)
