---
title: <generatePublisherEvidence> 要素
ms.date: 03/30/2017
helpviewer_keywords:
- generatePublisherEvidence element
- <generatePublisherEvidence> element
ms.assetid: 7d208f50-e8d5-4a42-bc1a-1cf3590706a8
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1a0861436ca727d63cdae58e3222826bf6414610
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2019
ms.locfileid: "66489441"
---
# <a name="generatepublisherevidence-element"></a><span data-ttu-id="1bd4b-102">\<generatePublisherEvidence > 要素</span><span class="sxs-lookup"><span data-stu-id="1bd4b-102">\<generatePublisherEvidence> Element</span></span>
<span data-ttu-id="1bd4b-103">ランタイムを作成するかどうかを指定します。<xref:System.Security.Policy.Publisher>コード アクセス セキュリティ (CAS) のための証拠。</span><span class="sxs-lookup"><span data-stu-id="1bd4b-103">Specifies whether the runtime creates <xref:System.Security.Policy.Publisher> evidence for code access security (CAS).</span></span>  
  
 <span data-ttu-id="1bd4b-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="1bd4b-104">\<configuration></span></span>  
<span data-ttu-id="1bd4b-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="1bd4b-105">\<runtime></span></span>  
<span data-ttu-id="1bd4b-106">\<generatePublisherEvidence></span><span class="sxs-lookup"><span data-stu-id="1bd4b-106">\<generatePublisherEvidence></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1bd4b-107">構文</span><span class="sxs-lookup"><span data-stu-id="1bd4b-107">Syntax</span></span>  
  
```xml  
<generatePublisherEvidence    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1bd4b-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="1bd4b-108">Attributes and Elements</span></span>  
 <span data-ttu-id="1bd4b-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="1bd4b-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1bd4b-110">属性</span><span class="sxs-lookup"><span data-stu-id="1bd4b-110">Attributes</span></span>  
  
|<span data-ttu-id="1bd4b-111">属性</span><span class="sxs-lookup"><span data-stu-id="1bd4b-111">Attribute</span></span>|<span data-ttu-id="1bd4b-112">説明</span><span class="sxs-lookup"><span data-stu-id="1bd4b-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="1bd4b-113">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="1bd4b-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="1bd4b-114">ランタイムを作成するかどうかを指定します。<xref:System.Security.Policy.Publisher>証拠。</span><span class="sxs-lookup"><span data-stu-id="1bd4b-114">Specifies whether the runtime creates <xref:System.Security.Policy.Publisher> evidence.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="1bd4b-115">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="1bd4b-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="1bd4b-116">値</span><span class="sxs-lookup"><span data-stu-id="1bd4b-116">Value</span></span>|<span data-ttu-id="1bd4b-117">説明</span><span class="sxs-lookup"><span data-stu-id="1bd4b-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="1bd4b-118">作成されません<xref:System.Security.Policy.Publisher>証拠。</span><span class="sxs-lookup"><span data-stu-id="1bd4b-118">Does not create <xref:System.Security.Policy.Publisher> evidence.</span></span>|  
|`true`|<span data-ttu-id="1bd4b-119">作成<xref:System.Security.Policy.Publisher>証拠。</span><span class="sxs-lookup"><span data-stu-id="1bd4b-119">Creates <xref:System.Security.Policy.Publisher> evidence.</span></span> <span data-ttu-id="1bd4b-120">既定値です。</span><span class="sxs-lookup"><span data-stu-id="1bd4b-120">This is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1bd4b-121">子要素</span><span class="sxs-lookup"><span data-stu-id="1bd4b-121">Child Elements</span></span>  
 <span data-ttu-id="1bd4b-122">なし。</span><span class="sxs-lookup"><span data-stu-id="1bd4b-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1bd4b-123">親要素</span><span class="sxs-lookup"><span data-stu-id="1bd4b-123">Parent Elements</span></span>  
  
|<span data-ttu-id="1bd4b-124">要素</span><span class="sxs-lookup"><span data-stu-id="1bd4b-124">Element</span></span>|<span data-ttu-id="1bd4b-125">説明</span><span class="sxs-lookup"><span data-stu-id="1bd4b-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="1bd4b-126">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="1bd4b-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="1bd4b-127">ランタイム初期化オプションに関する情報を含んでいます。</span><span class="sxs-lookup"><span data-stu-id="1bd4b-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1bd4b-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="1bd4b-128">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1bd4b-129">.NET Framework 4 以降では、この要素はアセンブリの読み込み時間に影響を与えません。</span><span class="sxs-lookup"><span data-stu-id="1bd4b-129">In the .NET Framework 4 and later, this element has no effect on assembly load times.</span></span> <span data-ttu-id="1bd4b-130">詳細については、「セキュリティ ポリシーの簡略化」のセクションを参照してください。[セキュリティ変更](../../../../../docs/framework/security/security-changes.md)します。</span><span class="sxs-lookup"><span data-stu-id="1bd4b-130">For more information, see the "Security Policy Simplification" section in [Security Changes](../../../../../docs/framework/security/security-changes.md).</span></span>  
  
 <span data-ttu-id="1bd4b-131">共通言語ランタイム (CLR) を作成する読み込み時に Authenticode 署名を検証しようとする<xref:System.Security.Policy.Publisher>アセンブリの証拠。</span><span class="sxs-lookup"><span data-stu-id="1bd4b-131">The common language runtime (CLR) tries to verify the Authenticode signature at load time to create <xref:System.Security.Policy.Publisher> evidence for the assembly.</span></span> <span data-ttu-id="1bd4b-132">ただし、既定では、ほとんどのアプリケーションは必要ありません<xref:System.Security.Policy.Publisher>証拠。</span><span class="sxs-lookup"><span data-stu-id="1bd4b-132">However, by default, most applications do not need <xref:System.Security.Policy.Publisher> evidence.</span></span> <span data-ttu-id="1bd4b-133">標準の CAS ポリシーに依存せず、<xref:System.Security.Policy.PublisherMembershipCondition>します。</span><span class="sxs-lookup"><span data-stu-id="1bd4b-133">Standard CAS policy does not rely on the <xref:System.Security.Policy.PublisherMembershipCondition>.</span></span> <span data-ttu-id="1bd4b-134">アプリケーションがカスタムの CAS ポリシーを使用しているコンピューター上で実行しますかのニーズを満たすにしない限り、発行元の署名の検証に関連付けられている不要なスタートアップ コストを回避する必要があります<xref:System.Security.Permissions.PublisherIdentityPermission>部分信頼環境でします。</span><span class="sxs-lookup"><span data-stu-id="1bd4b-134">You should avoid the unnecessary startup cost associated with verifying the publisher signature unless your application executes on a computer with custom CAS policy, or is intending to satisfy demands for <xref:System.Security.Permissions.PublisherIdentityPermission> in a partial-trust environment.</span></span> <span data-ttu-id="1bd4b-135">(Id アクセス許可の要求は常には、完全に信頼された環境で失敗した)。</span><span class="sxs-lookup"><span data-stu-id="1bd4b-135">(Demands for identity permissions always succeed in a full-trust environment.)</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1bd4b-136">使用するサービスをお勧め、`<generatePublisherEvidence>`起動時のパフォーマンスを向上させるために要素。</span><span class="sxs-lookup"><span data-stu-id="1bd4b-136">We recommend that services use the `<generatePublisherEvidence>` element to improve startup performance.</span></span>  <span data-ttu-id="1bd4b-137">この要素を使用しても、タイムアウトと、サービスのスタートアップのキャンセルを引き起こす可能性のある遅延を避けるためとことができます。</span><span class="sxs-lookup"><span data-stu-id="1bd4b-137">Using this element can also help avoid delays that can cause a time-out and the cancellation of the service startup.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="1bd4b-138">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="1bd4b-138">Configuration File</span></span>  
 <span data-ttu-id="1bd4b-139">この要素は、アプリケーション構成ファイルでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="1bd4b-139">This element can be used only in the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1bd4b-140">例</span><span class="sxs-lookup"><span data-stu-id="1bd4b-140">Example</span></span>  
 <span data-ttu-id="1bd4b-141">次の例は、使用する方法を示します、`<generatePublisherEvidence>`チェック アプリケーションの CA の発行元ポリシーを無効にする要素。</span><span class="sxs-lookup"><span data-stu-id="1bd4b-141">The following example shows how to use the `<generatePublisherEvidence>` element to disable checking for CAS publisher policy for an application.</span></span>  
  
```xml  
<configuration>  
    <runtime>  
        <generatePublisherEvidence enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1bd4b-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="1bd4b-142">See also</span></span>

- [<span data-ttu-id="1bd4b-143">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="1bd4b-143">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="1bd4b-144">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="1bd4b-144">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
