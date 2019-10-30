---
title: <generatePublisherEvidence> 要素
ms.date: 03/30/2017
helpviewer_keywords:
- generatePublisherEvidence element
- <generatePublisherEvidence> element
ms.assetid: 7d208f50-e8d5-4a42-bc1a-1cf3590706a8
ms.openlocfilehash: b04ef53d6e9c3d954b0925ea8634b3d220b36af7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73116572"
---
# <a name="generatepublisherevidence-element"></a><span data-ttu-id="65cd4-102">\<generatePublisherEvidence > 要素</span><span class="sxs-lookup"><span data-stu-id="65cd4-102">\<generatePublisherEvidence> Element</span></span>
<span data-ttu-id="65cd4-103">ランタイムがコードアクセスセキュリティ (CAS) の <xref:System.Security.Policy.Publisher> 証拠を作成するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="65cd4-103">Specifies whether the runtime creates <xref:System.Security.Policy.Publisher> evidence for code access security (CAS).</span></span>  
  
<span data-ttu-id="65cd4-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="65cd4-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="65cd4-105">&nbsp;&nbsp;[ **\<runtime>** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="65cd4-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="65cd4-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<generatePublisherEvidence >**</span><span class="sxs-lookup"><span data-stu-id="65cd4-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<generatePublisherEvidence>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65cd4-107">構文</span><span class="sxs-lookup"><span data-stu-id="65cd4-107">Syntax</span></span>  
  
```xml  
<generatePublisherEvidence    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="65cd4-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="65cd4-108">Attributes and Elements</span></span>  
 <span data-ttu-id="65cd4-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="65cd4-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="65cd4-110">属性</span><span class="sxs-lookup"><span data-stu-id="65cd4-110">Attributes</span></span>  
  
|<span data-ttu-id="65cd4-111">属性</span><span class="sxs-lookup"><span data-stu-id="65cd4-111">Attribute</span></span>|<span data-ttu-id="65cd4-112">説明</span><span class="sxs-lookup"><span data-stu-id="65cd4-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="65cd4-113">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="65cd4-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="65cd4-114">ランタイムが <xref:System.Security.Policy.Publisher> 証拠を作成するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="65cd4-114">Specifies whether the runtime creates <xref:System.Security.Policy.Publisher> evidence.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="65cd4-115">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="65cd4-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="65cd4-116">[値]</span><span class="sxs-lookup"><span data-stu-id="65cd4-116">Value</span></span>|<span data-ttu-id="65cd4-117">説明</span><span class="sxs-lookup"><span data-stu-id="65cd4-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="65cd4-118"><xref:System.Security.Policy.Publisher> 証拠を作成しません。</span><span class="sxs-lookup"><span data-stu-id="65cd4-118">Does not create <xref:System.Security.Policy.Publisher> evidence.</span></span>|  
|`true`|<span data-ttu-id="65cd4-119"><xref:System.Security.Policy.Publisher> 証拠を作成します。</span><span class="sxs-lookup"><span data-stu-id="65cd4-119">Creates <xref:System.Security.Policy.Publisher> evidence.</span></span> <span data-ttu-id="65cd4-120">既定値です。</span><span class="sxs-lookup"><span data-stu-id="65cd4-120">This is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="65cd4-121">子要素</span><span class="sxs-lookup"><span data-stu-id="65cd4-121">Child Elements</span></span>  
 <span data-ttu-id="65cd4-122">なし。</span><span class="sxs-lookup"><span data-stu-id="65cd4-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="65cd4-123">親要素</span><span class="sxs-lookup"><span data-stu-id="65cd4-123">Parent Elements</span></span>  
  
|<span data-ttu-id="65cd4-124">要素</span><span class="sxs-lookup"><span data-stu-id="65cd4-124">Element</span></span>|<span data-ttu-id="65cd4-125">説明</span><span class="sxs-lookup"><span data-stu-id="65cd4-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="65cd4-126">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="65cd4-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="65cd4-127">ランタイム初期化オプションに関する情報を含んでいます。</span><span class="sxs-lookup"><span data-stu-id="65cd4-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="65cd4-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="65cd4-128">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="65cd4-129">.NET Framework 4 以降では、この要素はアセンブリの読み込み時間に影響しません。</span><span class="sxs-lookup"><span data-stu-id="65cd4-129">In the .NET Framework 4 and later, this element has no effect on assembly load times.</span></span> <span data-ttu-id="65cd4-130">詳細については、「セキュリティの[変更](../../../security/security-changes.md)」の「セキュリティポリシーの簡略化」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65cd4-130">For more information, see the "Security Policy Simplification" section in [Security Changes](../../../security/security-changes.md).</span></span>  
  
 <span data-ttu-id="65cd4-131">共通言語ランタイム (CLR) は、読み込み時に Authenticode 署名を検証して、アセンブリの <xref:System.Security.Policy.Publisher> 証拠を作成しようとします。</span><span class="sxs-lookup"><span data-stu-id="65cd4-131">The common language runtime (CLR) tries to verify the Authenticode signature at load time to create <xref:System.Security.Policy.Publisher> evidence for the assembly.</span></span> <span data-ttu-id="65cd4-132">ただし、既定では、ほとんどのアプリケーションは <xref:System.Security.Policy.Publisher> 証拠を必要としません。</span><span class="sxs-lookup"><span data-stu-id="65cd4-132">However, by default, most applications do not need <xref:System.Security.Policy.Publisher> evidence.</span></span> <span data-ttu-id="65cd4-133">Standard CAS ポリシーは、<xref:System.Security.Policy.PublisherMembershipCondition>に依存しません。</span><span class="sxs-lookup"><span data-stu-id="65cd4-133">Standard CAS policy does not rely on the <xref:System.Security.Policy.PublisherMembershipCondition>.</span></span> <span data-ttu-id="65cd4-134">カスタム CAS ポリシーを使用しているコンピューターでアプリケーションを実行する場合や、部分信頼環境で <xref:System.Security.Permissions.PublisherIdentityPermission> の要求を満たす場合を除き、発行元の署名の検証に関連する不要な起動コストを回避する必要があります。</span><span class="sxs-lookup"><span data-stu-id="65cd4-134">You should avoid the unnecessary startup cost associated with verifying the publisher signature unless your application executes on a computer with custom CAS policy, or is intending to satisfy demands for <xref:System.Security.Permissions.PublisherIdentityPermission> in a partial-trust environment.</span></span> <span data-ttu-id="65cd4-135">(Id 権限の要求は、完全に信頼された環境では常に成功します)。</span><span class="sxs-lookup"><span data-stu-id="65cd4-135">(Demands for identity permissions always succeed in a full-trust environment.)</span></span>  
  
> [!NOTE]
> <span data-ttu-id="65cd4-136">サービスでは、起動時のパフォーマンスを向上させるために `<generatePublisherEvidence>` 要素を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="65cd4-136">We recommend that services use the `<generatePublisherEvidence>` element to improve startup performance.</span></span>  <span data-ttu-id="65cd4-137">また、この要素を使用すると、タイムアウトを発生させたり、サービスの開始をキャンセルしたりする可能性がある遅延を回避することもできます。</span><span class="sxs-lookup"><span data-stu-id="65cd4-137">Using this element can also help avoid delays that can cause a time-out and the cancellation of the service startup.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="65cd4-138">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="65cd4-138">Configuration File</span></span>  
 <span data-ttu-id="65cd4-139">この要素は、アプリケーション構成ファイルでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="65cd4-139">This element can be used only in the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="65cd4-140">例</span><span class="sxs-lookup"><span data-stu-id="65cd4-140">Example</span></span>  
 <span data-ttu-id="65cd4-141">次の例は、`<generatePublisherEvidence>` 要素を使用して、アプリケーションの CAS 発行者ポリシーのチェックを無効にする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="65cd4-141">The following example shows how to use the `<generatePublisherEvidence>` element to disable checking for CAS publisher policy for an application.</span></span>  
  
```xml  
<configuration>  
    <runtime>  
        <generatePublisherEvidence enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="65cd4-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="65cd4-142">See also</span></span>

- [<span data-ttu-id="65cd4-143">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="65cd4-143">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="65cd4-144">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="65cd4-144">Configuration File Schema</span></span>](../index.md)
