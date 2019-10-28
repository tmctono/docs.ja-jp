---
title: ASP.NET での System.Transactions の使用
ms.date: 03/30/2017
ms.assetid: 1982c300-7ea6-4242-95ed-dc28ccfacac9
ms.openlocfilehash: 6f88a4b06a9a83cf920601b7abe887d8b5fa7839
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72774150"
---
# <a name="using-systemtransactions-in-aspnet"></a><span data-ttu-id="0db69-102">ASP.NET での System.Transactions の使用</span><span class="sxs-lookup"><span data-stu-id="0db69-102">Using System.Transactions in ASP.NET</span></span>
<span data-ttu-id="0db69-103">ここでは、ASP.NET アプリケーション内で <xref:System.Transactions> を正しく使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0db69-103">This topic describes how you can successfully use <xref:System.Transactions> inside an ASP.NET application.</span></span>

## <a name="enable-distributedtransactionpermission-in-aspnet"></a><span data-ttu-id="0db69-104">ASP.NET での DistributedTransactionPermission の有効化</span><span class="sxs-lookup"><span data-stu-id="0db69-104">Enable DistributedTransactionPermission in ASP.NET</span></span>
 <span data-ttu-id="0db69-105"><xref:System.Transactions> は、部分的に信頼された呼び出し側をサポートしており、 **AllowPartiallyTrustedCallers** 属性 (APTCA) を使用してマークされます。</span><span class="sxs-lookup"><span data-stu-id="0db69-105"><xref:System.Transactions> supports partially trusted callers and is marked with the **AllowPartiallyTrustedCallers** attribute (APTCA).</span></span> <span data-ttu-id="0db69-106"><xref:System.Transactions> の信頼レベルは、<xref:System.Transactions> 公開しているリソースの種類 (システムメモリ、共有プロセス全体のリソース、システム全体のリソース、その他のリソースなど) に基づいて定義され、それらにアクセスするために必要な信頼レベルに基づいて定義されます。参考.</span><span class="sxs-lookup"><span data-stu-id="0db69-106">The trust levels for <xref:System.Transactions> are defined based on the types of resources (for example, system memory, shared process-wide resources, system-wide resources, and other resources) that <xref:System.Transactions> exposes and the level of trust that should be required to access those resources.</span></span> <span data-ttu-id="0db69-107">部分的に信頼された環境では、 <xref:System.Transactions.DistributedTransactionPermission>が付与されていない限り、完全に信頼されていないアセンブリは、アプリケーション ドメイン内でのみトランザクションを使用できます (この場合、保護されている唯一のリソースはシステム メモリです)。</span><span class="sxs-lookup"><span data-stu-id="0db69-107">In a partial-trust environment, a non-full trust assembly can only use transactions within the Application Domain (in this case, the only resource being protected is system memory), unless it is granted the <xref:System.Transactions.DistributedTransactionPermission>.</span></span>

 <span data-ttu-id="0db69-108">Microsoft 分散トランザクション コーディネーター (MSDTC) で管理されるようトランザクション管理がエスカレートされるたびに、<xref:System.Transactions.DistributedTransactionPermission> が要求されます。</span><span class="sxs-lookup"><span data-stu-id="0db69-108"><xref:System.Transactions.DistributedTransactionPermission> is demanded whenever transaction management is escalated to be managed by the Microsoft Distributed Transaction Coordinator (MSDTC).</span></span> <span data-ttu-id="0db69-109">この種のシナリオでは、プロセス全体のリソースと特にグローバルなリソースを使用します。グローバルなリソースは、MSDTC ログで予約されたスペースです。</span><span class="sxs-lookup"><span data-stu-id="0db69-109">This kind of scenario utilizes process-wide resources and particularly a global resource, which is the reserved space in the MSDTC log.</span></span> <span data-ttu-id="0db69-110">この使用方法の例として、データベース、または供給するサービスの一部としてデータベースを使用するアプリケーションへの Web フロントエンドがあります。</span><span class="sxs-lookup"><span data-stu-id="0db69-110">An example of this usage is a Web front-end to a database or an application that uses a database as part of the services it provides.</span></span>

 <span data-ttu-id="0db69-111">ASP.NET は、独自の信頼レベル セットを持ち、ポリシー ファイルを介して特定のアクセス許可セットをこれらの信頼レベルに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="0db69-111">ASP.NET has its own set of trust levels and associates a specific set of permissions with these trust levels through policy files.</span></span> <span data-ttu-id="0db69-112">詳細については、「 [ASP.NET Trust Levels And Policy Files](https://docs.microsoft.com/previous-versions/aspnet/wyts434y(v=vs.100))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0db69-112">For more information, see [ASP.NET Trust Levels and Policy Files](https://docs.microsoft.com/previous-versions/aspnet/wyts434y(v=vs.100)).</span></span> <span data-ttu-id="0db69-113">Windows SDK を最初にインストールしたときに、既定の ASP.NET ポリシーファイルは、<xref:System.Transactions.DistributedTransactionPermission>に関連付けられていません。</span><span class="sxs-lookup"><span data-stu-id="0db69-113">When you initially install the Windows SDK, none of the default ASP.NET policy files are associated with the <xref:System.Transactions.DistributedTransactionPermission>.</span></span> <span data-ttu-id="0db69-114">そのため、ASP.NET アプリケーションのトランザクションが MSDTC によって管理されるようエスカレートされると、<xref:System.Security.SecurityException><xref:System.Transactions.DistributedTransactionPermission>を要求した時点で、 によりエスカレーションが失敗します。</span><span class="sxs-lookup"><span data-stu-id="0db69-114">As such, when your transaction in an ASP.NET application is escalated to be managed by the MSDTC, the escalation fails with a <xref:System.Security.SecurityException> upon demanding the <xref:System.Transactions.DistributedTransactionPermission>.</span></span> <span data-ttu-id="0db69-115">部分的に信頼された ASP.NET の環境でトランザクションのエスカレーションを有効にするには、<xref:System.Transactions.DistributedTransactionPermission><xref:System.Data.SqlClient.SqlClientPermission>と同じ既定の信頼レベルで、 を付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0db69-115">To enable transaction escalation in an ASP.NET partial trust environment, you should grant the <xref:System.Transactions.DistributedTransactionPermission> in the same default trust levels as those of <xref:System.Data.SqlClient.SqlClientPermission>.</span></span> <span data-ttu-id="0db69-116">これをサポートする独自のカスタム信頼レベルとポリシー ファイルを構成するか、既定のポリシー ファイルである **Web_hightrust.config** および **Web_mediumtrust.config**を変更できます。</span><span class="sxs-lookup"><span data-stu-id="0db69-116">You can either configure your own custom trust level and policy file to support this, or you can modify the default policy files, which are **Web_hightrust.config** and **Web_mediumtrust.config**.</span></span>

 <span data-ttu-id="0db69-117">ポリシーファイルを変更するには、 **DistributedTransactionPermission**の**Securityclass**要素を**Policylevel**要素の下の**securityclass**要素に追加し、対応する**IPermission**要素をに追加します。ASP.NET **vstecasp**を使用します。</span><span class="sxs-lookup"><span data-stu-id="0db69-117">To modify the policy files, add a **SecurityClass** element for **DistributedTransactionPermission** to the **SecurityClasses** element under the **PolicyLevel** element and add a corresponding **IPermission** element under the ASP.NET **NamedPermissionSet** for System.Transactions.</span></span> <span data-ttu-id="0db69-118">次の構成ファイルに、この例を示します。</span><span class="sxs-lookup"><span data-stu-id="0db69-118">The following configuration file demonstrates this.</span></span>

```xml
<SecurityClasses>
   <SecurityClass Name="DistributedTransactionPermission" Description="System.Transactions.DistributedTransactionPermission, System.Transactions, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"/>
...
</SecurityClasses>

<PermissionSet
  class="NamedPermissionSet"
  version="1"
  Name="ASP.Net">
     <IPermission
        class="System.Transactions.DistributedTransactionPermission, System.Transactions, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"
        version="1"
        Unrestricted="true"
     />
...
</PermissionSet>
```

 <span data-ttu-id="0db69-119">ASP.NET セキュリティポリシーの詳細については、「 [Ws-securitypolicy 要素 (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/zhs35b56(v=vs.100))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0db69-119">For more information about ASP.NET security policy, see [securityPolicy Element (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/zhs35b56(v=vs.100)).</span></span>

## <a name="dynamic-compilation"></a><span data-ttu-id="0db69-120">動的コンパイル</span><span class="sxs-lookup"><span data-stu-id="0db69-120">Dynamic Compilation</span></span>
 <span data-ttu-id="0db69-121">アクセス時に動的にコンパイルされる ASP.NET アプリケーションで <xref:System.Transactions> をインポートして使用する場合、構成ファイルに <xref:System.Transactions> アセンブリへの参照を配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0db69-121">If you want to import and use <xref:System.Transactions> in an ASP.NET application that is dynamically compiled on access, you should place a reference to the <xref:System.Transactions> assembly in the configuration file.</span></span> <span data-ttu-id="0db69-122">具体的には、既定のルートの **Web.config**/**compilation** / **assemblies** セクションに、この参照を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0db69-122">Specifically, the reference should be added under the **compilation**/**assemblies** section of the default root **Web.config** configuration file, or a specific Web application's configuration file.</span></span> <span data-ttu-id="0db69-123">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="0db69-123">The following example demonstrates this.</span></span>

```xml
<configuration>
   <system.web>
      <compilation>
         <assemblies>
      <add assembly="System.Transactions, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />
         </assemblies>
      </compilation>
   </system.web>
</configuration>
```

 <span data-ttu-id="0db69-124">詳細については、「[コンパイルのためのアセンブリの追加要素 (ASP.NET 設定スキーマ)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/37e2zyhb(v=vs.100))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0db69-124">For more information, see [add Element for assemblies for compilation (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/37e2zyhb(v=vs.100)).</span></span>

## <a name="see-also"></a><span data-ttu-id="0db69-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="0db69-125">See also</span></span>

- <span data-ttu-id="0db69-126">[ASP.NET の信頼レベルとポリシーファイル](https://docs.microsoft.com/previous-versions/aspnet/wyts434y(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="0db69-126">[ASP.NET Trust Levels and Policy Files](https://docs.microsoft.com/previous-versions/aspnet/wyts434y(v=vs.100))</span></span>
- <span data-ttu-id="0db69-127">[Ws-securitypolicy 要素 (ASP.NET Settings スキーマ)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/zhs35b56(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="0db69-127">[securityPolicy Element (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/zhs35b56(v=vs.100))</span></span>
- [<span data-ttu-id="0db69-128">トランザクション管理のエスカレーション</span><span class="sxs-lookup"><span data-stu-id="0db69-128">Transaction Management Escalation</span></span>](transaction-management-escalation.md)
