---
title: サービス操作へのアクセスの承認
ms.date: 03/30/2017
helpviewer_keywords:
- service behaviors, authorizing access sample
- Authorizing Access To Service Operations Sample [Windows Communication Foundation]
- authorization, Windows Communication Foundation sample
ms.assetid: ddcfdaa5-8b2e-4e13-bd85-887209dc6328
ms.openlocfilehash: a0ea82c876b3bd8c2a3218f84399fbb69e1d0080
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69932506"
---
# <a name="authorizing-access-to-service-operations"></a><span data-ttu-id="32fbb-102">サービス操作へのアクセスの承認</span><span class="sxs-lookup"><span data-stu-id="32fbb-102">Authorizing Access to Service Operations</span></span>
<span data-ttu-id="32fbb-103">このサンプルでは、 [ \<serviceauthorization >](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md)を使用して、 <xref:System.Security.Permissions.PrincipalPermissionAttribute>サービス操作へのアクセスを承認するために属性を使用できるようにする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="32fbb-103">This sample demonstrates how to use the [\<serviceAuthorization>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) to enable use of the <xref:System.Security.Permissions.PrincipalPermissionAttribute> attribute to authorize access to service operations.</span></span> <span data-ttu-id="32fbb-104">このサンプルは、[はじめに](../../../../docs/framework/wcf/samples/getting-started-sample.md)のサンプルに基づいています。</span><span class="sxs-lookup"><span data-stu-id="32fbb-104">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) sample.</span></span> <span data-ttu-id="32fbb-105">サービスとクライアントは、 [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)を使用して構成されます。</span><span class="sxs-lookup"><span data-stu-id="32fbb-105">The service and client are configured using the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span></span> <span data-ttu-id="32fbb-106">`Message` `Windows`セキュリティ>`clientCredentialType` [の属性がに設定され、がに設定されています。 \<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) `mode`</span><span class="sxs-lookup"><span data-stu-id="32fbb-106">The `mode` attribute of the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) has been set to `Message` and `clientCredentialType` has been set to `Windows`.</span></span> <span data-ttu-id="32fbb-107"><xref:System.Security.Permissions.PrincipalPermissionAttribute> は各サービス メソッドに適用され、各操作へのアクセスを制限するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="32fbb-107">The <xref:System.Security.Permissions.PrincipalPermissionAttribute> is applied to each service method and used to restrict access to each operation.</span></span> <span data-ttu-id="32fbb-108">呼び出し元は、各操作にアクセスできる Windows 管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="32fbb-108">The caller must be a Windows administrator to access each operation.</span></span>  
  
 <span data-ttu-id="32fbb-109">この例では、クライアントはコンソール アプリケーション (.exe) であり、サービスはインターネット インフォメーション サービス (IIS) によってホストされます。</span><span class="sxs-lookup"><span data-stu-id="32fbb-109">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="32fbb-110">このサンプルのセットアップ手順とビルド手順については、このトピックの最後を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32fbb-110">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="32fbb-111">サービス構成ファイルでは、 [ \<serviceauthorization >](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md)を使用し`principalPermissionMode`て属性を設定します。</span><span class="sxs-lookup"><span data-stu-id="32fbb-111">The service configuration file uses the [\<serviceAuthorization>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) to set the `principalPermissionMode` attribute:</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
    <behavior>   
      <!-- The serviceAuthorization behavior sets the  
           principalPermissionMode to UseWindowsGroups.  
           This puts a WindowsPrincipal on the current thread when a   
           service is invoked. -->  
      <serviceAuthorization principalPermissionMode="UseWindowsGroups" />  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 <span data-ttu-id="32fbb-112">`principalPermissionMode` を `UseWindowsGroups` に設定すると、Windows グループ名に基づいて <xref:System.Security.Permissions.PrincipalPermissionAttribute> を使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="32fbb-112">Setting the `principalPermissionMode` to `UseWindowsGroups` enables the use of <xref:System.Security.Permissions.PrincipalPermissionAttribute> based on Windows group names.</span></span>  
  
 <span data-ttu-id="32fbb-113">呼び出し元が Windows 管理者グループのメンバーであることを要求するため、<xref:System.Security.Permissions.PrincipalPermissionAttribute> が各操作に適用されます。次のサンプル コードを参照してください。</span><span class="sxs-lookup"><span data-stu-id="32fbb-113">The <xref:System.Security.Permissions.PrincipalPermissionAttribute> is applied to each operation to require the caller to be part of the Windows administrators group, as shown in the following sample code.</span></span>  
  
```csharp
[PrincipalPermission(SecurityAction.Demand,   
                             Role = "Builtin\\Administrators")]  
public double Add(double n1, double n2)  
{  
    double result = n1 + n2;  
    return result;  
}  
```  
  
 <span data-ttu-id="32fbb-114">このサンプルを実行すると、操作要求および応答がクライアントのコンソール ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="32fbb-114">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="32fbb-115">クライアントが管理者グループのメンバーであるアカウントで実行される場合、クライアントは各操作と正常に通信できます。それ以外のアカウントで実行される場合、アクセスは拒否されます。</span><span class="sxs-lookup"><span data-stu-id="32fbb-115">The client successfully communicates with each operation if it is running under an account that is part of the Administrators group; otherwise, access is denied.</span></span> <span data-ttu-id="32fbb-116">承認エラーを試すには、管理グループのメンバーではないアカウントでクライアントを実行します。</span><span class="sxs-lookup"><span data-stu-id="32fbb-116">To experiment with authorization failure, run the client under an account that is not part of the Administrators group.</span></span> <span data-ttu-id="32fbb-117">クライアントをシャットダウンするには、コンソール ウィンドウで Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="32fbb-117">Press ENTER in the console window to shut down the client.</span></span>  
  
 <span data-ttu-id="32fbb-118"><xref:System.ServiceModel.Dispatcher.IErrorHandler> を実装すると、サービスに承認エラーを通知することができます。</span><span class="sxs-lookup"><span data-stu-id="32fbb-118">A service can be notified of authorization failures by implementing an <xref:System.ServiceModel.Dispatcher.IErrorHandler>.</span></span> <span data-ttu-id="32fbb-119">の実装`IErrorHandler`の詳細については[、「エラー処理およびレポートに対する制御の拡張](../../../../docs/framework/wcf/samples/extending-control-over-error-handling-and-reporting.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32fbb-119">See [Extending Control Over Error Handling and Reporting](../../../../docs/framework/wcf/samples/extending-control-over-error-handling-and-reporting.md) for information about implementing `IErrorHandler`.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="32fbb-120">サンプルをセットアップ、ビルド、および実行するには</span><span class="sxs-lookup"><span data-stu-id="32fbb-120">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="32fbb-121">[Windows Communication Foundation サンプルの1回限りのセットアップ手順](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)を実行したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="32fbb-121">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="32fbb-122">ソリューションの C# 版または Visual Basic .NET 版をビルドするには、「 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="32fbb-122">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="32fbb-123">サンプルを単一コンピューター構成または複数コンピューター構成で実行するには、「 [Windows Communication Foundation サンプルの実行](../../../../docs/framework/wcf/samples/running-the-samples.md)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="32fbb-123">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
