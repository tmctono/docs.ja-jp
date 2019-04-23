---
title: <generatePublisherEvidence> 要素
ms.date: 03/30/2017
helpviewer_keywords:
- generatePublisherEvidence element
- <generatePublisherEvidence> element
ms.assetid: 7d208f50-e8d5-4a42-bc1a-1cf3590706a8
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 09a12f062b2fe3ad6e5ac90f0d268bbbeab44876
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59198921"
---
# <a name="generatepublisherevidence-element"></a><span data-ttu-id="c5c6c-102">\<generatePublisherEvidence > 要素</span><span class="sxs-lookup"><span data-stu-id="c5c6c-102">\<generatePublisherEvidence> Element</span></span>
<span data-ttu-id="c5c6c-103">ランタイムを作成するかどうかを指定します。<xref:System.Security.Policy.Publisher>コード アクセス セキュリティ (CAS) のための証拠。</span><span class="sxs-lookup"><span data-stu-id="c5c6c-103">Specifies whether the runtime creates <xref:System.Security.Policy.Publisher> evidence for code access security (CAS).</span></span>  
  
 <span data-ttu-id="c5c6c-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="c5c6c-104">\<configuration></span></span>  
<span data-ttu-id="c5c6c-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="c5c6c-105">\<runtime></span></span>  
<span data-ttu-id="c5c6c-106">\<generatePublisherEvidence></span><span class="sxs-lookup"><span data-stu-id="c5c6c-106">\<generatePublisherEvidence></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5c6c-107">構文</span><span class="sxs-lookup"><span data-stu-id="c5c6c-107">Syntax</span></span>  
  
```xml  
<generatePublisherEvidence    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c5c6c-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="c5c6c-108">Attributes and Elements</span></span>  
 <span data-ttu-id="c5c6c-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="c5c6c-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c5c6c-110">属性</span><span class="sxs-lookup"><span data-stu-id="c5c6c-110">Attributes</span></span>  
  
|<span data-ttu-id="c5c6c-111">属性</span><span class="sxs-lookup"><span data-stu-id="c5c6c-111">Attribute</span></span>|<span data-ttu-id="c5c6c-112">説明</span><span class="sxs-lookup"><span data-stu-id="c5c6c-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="c5c6c-113">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="c5c6c-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="c5c6c-114">ランタイムを作成するかどうかを指定します。<xref:System.Security.Policy.Publisher>証拠。</span><span class="sxs-lookup"><span data-stu-id="c5c6c-114">Specifies whether the runtime creates <xref:System.Security.Policy.Publisher> evidence.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="c5c6c-115">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="c5c6c-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="c5c6c-116">値</span><span class="sxs-lookup"><span data-stu-id="c5c6c-116">Value</span></span>|<span data-ttu-id="c5c6c-117">説明</span><span class="sxs-lookup"><span data-stu-id="c5c6c-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="c5c6c-118">作成されません<xref:System.Security.Policy.Publisher>証拠。</span><span class="sxs-lookup"><span data-stu-id="c5c6c-118">Does not create <xref:System.Security.Policy.Publisher> evidence.</span></span>|  
|`true`|<span data-ttu-id="c5c6c-119">作成<xref:System.Security.Policy.Publisher>証拠。</span><span class="sxs-lookup"><span data-stu-id="c5c6c-119">Creates <xref:System.Security.Policy.Publisher> evidence.</span></span> <span data-ttu-id="c5c6c-120">既定値です。</span><span class="sxs-lookup"><span data-stu-id="c5c6c-120">This is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c5c6c-121">子要素</span><span class="sxs-lookup"><span data-stu-id="c5c6c-121">Child Elements</span></span>  
 <span data-ttu-id="c5c6c-122">なし。</span><span class="sxs-lookup"><span data-stu-id="c5c6c-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c5c6c-123">親要素</span><span class="sxs-lookup"><span data-stu-id="c5c6c-123">Parent Elements</span></span>  
  
|<span data-ttu-id="c5c6c-124">要素</span><span class="sxs-lookup"><span data-stu-id="c5c6c-124">Element</span></span>|<span data-ttu-id="c5c6c-125">説明</span><span class="sxs-lookup"><span data-stu-id="c5c6c-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="c5c6c-126">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="c5c6c-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="c5c6c-127">ランタイム初期化オプションに関する情報を含んでいます。</span><span class="sxs-lookup"><span data-stu-id="c5c6c-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c5c6c-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="c5c6c-128">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c5c6c-129">[!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)]なり、後でこの要素にはアセンブリの読み込み時間に効力はありません。</span><span class="sxs-lookup"><span data-stu-id="c5c6c-129">In the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] and later, this element has no effect on assembly load times.</span></span> <span data-ttu-id="c5c6c-130">詳細については、「セキュリティ ポリシーの簡略化」のセクションを参照してください。[セキュリティ変更](../../../../../docs/framework/security/security-changes.md)します。</span><span class="sxs-lookup"><span data-stu-id="c5c6c-130">For more information, see the "Security Policy Simplification" section in [Security Changes](../../../../../docs/framework/security/security-changes.md).</span></span>  
  
 <span data-ttu-id="c5c6c-131">共通言語ランタイム (CLR) を作成する読み込み時に Authenticode 署名を検証しようとする<xref:System.Security.Policy.Publisher>アセンブリの証拠。</span><span class="sxs-lookup"><span data-stu-id="c5c6c-131">The common language runtime (CLR) tries to verify the Authenticode signature at load time to create <xref:System.Security.Policy.Publisher> evidence for the assembly.</span></span> <span data-ttu-id="c5c6c-132">ただし、既定では、ほとんどのアプリケーションは必要ありません<xref:System.Security.Policy.Publisher>証拠。</span><span class="sxs-lookup"><span data-stu-id="c5c6c-132">However, by default, most applications do not need <xref:System.Security.Policy.Publisher> evidence.</span></span> <span data-ttu-id="c5c6c-133">標準の CAS ポリシーに依存せず、<xref:System.Security.Policy.PublisherMembershipCondition>します。</span><span class="sxs-lookup"><span data-stu-id="c5c6c-133">Standard CAS policy does not rely on the <xref:System.Security.Policy.PublisherMembershipCondition>.</span></span> <span data-ttu-id="c5c6c-134">アプリケーションがカスタムの CAS ポリシーを使用しているコンピューター上で実行しますかのニーズを満たすにしない限り、発行元の署名の検証に関連付けられている不要なスタートアップ コストを回避する必要があります<xref:System.Security.Permissions.PublisherIdentityPermission>部分信頼環境でします。</span><span class="sxs-lookup"><span data-stu-id="c5c6c-134">You should avoid the unnecessary startup cost associated with verifying the publisher signature unless your application executes on a computer with custom CAS policy, or is intending to satisfy demands for <xref:System.Security.Permissions.PublisherIdentityPermission> in a partial-trust environment.</span></span> <span data-ttu-id="c5c6c-135">(Id アクセス許可の要求は常には、完全に信頼された環境で失敗した)。</span><span class="sxs-lookup"><span data-stu-id="c5c6c-135">(Demands for identity permissions always succeed in a full-trust environment.)</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c5c6c-136">使用するサービスをお勧め、`<generatePublisherEvidence>`起動時のパフォーマンスを向上させるために要素。</span><span class="sxs-lookup"><span data-stu-id="c5c6c-136">We recommend that services use the `<generatePublisherEvidence>` element to improve startup performance.</span></span>  <span data-ttu-id="c5c6c-137">この要素を使用しても、タイムアウトと、サービスのスタートアップのキャンセルを引き起こす可能性のある遅延を避けるためとことができます。</span><span class="sxs-lookup"><span data-stu-id="c5c6c-137">Using this element can also help avoid delays that can cause a time-out and the cancellation of the service startup.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="c5c6c-138">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="c5c6c-138">Configuration File</span></span>  
 <span data-ttu-id="c5c6c-139">この要素は、アプリケーション構成ファイルでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="c5c6c-139">This element can be used only in the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c5c6c-140">例</span><span class="sxs-lookup"><span data-stu-id="c5c6c-140">Example</span></span>  
 <span data-ttu-id="c5c6c-141">次の例は、使用する方法を示します、`<generatePublisherEvidence>`チェック アプリケーションの CA の発行元ポリシーを無効にする要素。</span><span class="sxs-lookup"><span data-stu-id="c5c6c-141">The following example shows how to use the `<generatePublisherEvidence>` element to disable checking for CAS publisher policy for an application.</span></span>  
  
```xml  
<configuration>  
    <runtime>  
        <generatePublisherEvidence enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c5c6c-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="c5c6c-142">See also</span></span>

- [<span data-ttu-id="c5c6c-143">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="c5c6c-143">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="c5c6c-144">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="c5c6c-144">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
