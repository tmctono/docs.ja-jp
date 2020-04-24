---
title: <generatePublisherEvidence> 要素
ms.date: 03/30/2017
helpviewer_keywords:
- generatePublisherEvidence element
- <generatePublisherEvidence> element
ms.assetid: 7d208f50-e8d5-4a42-bc1a-1cf3590706a8
ms.openlocfilehash: c2ba4a7244b7849e28eac38fb34a2cdd0d1f1048
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2020
ms.locfileid: "81645355"
---
# <a name="generatepublisherevidence-element"></a><span data-ttu-id="f134c-102">\<generatePublisherEvidence> 要素</span><span class="sxs-lookup"><span data-stu-id="f134c-102">\<generatePublisherEvidence> Element</span></span>
<span data-ttu-id="f134c-103">ランタイムがコード アクセス<xref:System.Security.Policy.Publisher>セキュリティ (CAS) の証拠を作成するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="f134c-103">Specifies whether the runtime creates <xref:System.Security.Policy.Publisher> evidence for code access security (CAS).</span></span>  
  
<span data-ttu-id="f134c-104">[**\<構成>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f134c-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f134c-105">&nbsp;&nbsp;[**\<ランタイム>**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="f134c-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="f134c-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<>を生成する**</span><span class="sxs-lookup"><span data-stu-id="f134c-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<generatePublisherEvidence>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f134c-107">構文</span><span class="sxs-lookup"><span data-stu-id="f134c-107">Syntax</span></span>  
  
```xml  
<generatePublisherEvidence
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f134c-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="f134c-108">Attributes and Elements</span></span>  
 <span data-ttu-id="f134c-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="f134c-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f134c-110">属性</span><span class="sxs-lookup"><span data-stu-id="f134c-110">Attributes</span></span>  
  
|<span data-ttu-id="f134c-111">属性</span><span class="sxs-lookup"><span data-stu-id="f134c-111">Attribute</span></span>|<span data-ttu-id="f134c-112">説明</span><span class="sxs-lookup"><span data-stu-id="f134c-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="f134c-113">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="f134c-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="f134c-114">ランタイムが証拠を作成<xref:System.Security.Policy.Publisher>するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="f134c-114">Specifies whether the runtime creates <xref:System.Security.Policy.Publisher> evidence.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="f134c-115">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="f134c-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="f134c-116">値</span><span class="sxs-lookup"><span data-stu-id="f134c-116">Value</span></span>|<span data-ttu-id="f134c-117">説明</span><span class="sxs-lookup"><span data-stu-id="f134c-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="f134c-118">証拠を作成<xref:System.Security.Policy.Publisher>しません。</span><span class="sxs-lookup"><span data-stu-id="f134c-118">Does not create <xref:System.Security.Policy.Publisher> evidence.</span></span>|  
|`true`|<span data-ttu-id="f134c-119">証拠<xref:System.Security.Policy.Publisher>を作成します。</span><span class="sxs-lookup"><span data-stu-id="f134c-119">Creates <xref:System.Security.Policy.Publisher> evidence.</span></span> <span data-ttu-id="f134c-120">これは既定値です。</span><span class="sxs-lookup"><span data-stu-id="f134c-120">This is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f134c-121">子要素</span><span class="sxs-lookup"><span data-stu-id="f134c-121">Child Elements</span></span>  
 <span data-ttu-id="f134c-122">[なし] :</span><span class="sxs-lookup"><span data-stu-id="f134c-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f134c-123">親要素</span><span class="sxs-lookup"><span data-stu-id="f134c-123">Parent Elements</span></span>  
  
|<span data-ttu-id="f134c-124">要素</span><span class="sxs-lookup"><span data-stu-id="f134c-124">Element</span></span>|<span data-ttu-id="f134c-125">説明</span><span class="sxs-lookup"><span data-stu-id="f134c-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="f134c-126">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="f134c-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="f134c-127">ランタイム初期化オプションに関する情報を含んでいます。</span><span class="sxs-lookup"><span data-stu-id="f134c-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f134c-128">解説</span><span class="sxs-lookup"><span data-stu-id="f134c-128">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f134c-129">NET Framework 4 以降では、この要素はアセンブリの読み込み時間には影響しません。</span><span class="sxs-lookup"><span data-stu-id="f134c-129">In the .NET Framework 4 and later, this element has no effect on assembly load times.</span></span> <span data-ttu-id="f134c-130">詳細については、『セキュリティの[変更](https://docs.microsoft.com/previous-versions/dotnet/framework/security/security-changes)』の「セキュリティ ポリシーの簡略化」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f134c-130">For more information, see the "Security Policy Simplification" section in [Security Changes](https://docs.microsoft.com/previous-versions/dotnet/framework/security/security-changes).</span></span>  
  
 <span data-ttu-id="f134c-131">共通言語ランタイム (CLR) は、読み込み時に Authenticode<xref:System.Security.Policy.Publisher>署名を検証して、アセンブリの証拠を作成しようとします。</span><span class="sxs-lookup"><span data-stu-id="f134c-131">The common language runtime (CLR) tries to verify the Authenticode signature at load time to create <xref:System.Security.Policy.Publisher> evidence for the assembly.</span></span> <span data-ttu-id="f134c-132">ただし、既定では、ほとんどのアプリケーションは証拠を<xref:System.Security.Policy.Publisher>必要としません。</span><span class="sxs-lookup"><span data-stu-id="f134c-132">However, by default, most applications do not need <xref:System.Security.Policy.Publisher> evidence.</span></span> <span data-ttu-id="f134c-133">標準の CAS ポリシーは、<xref:System.Security.Policy.PublisherMembershipCondition>に依存しません。</span><span class="sxs-lookup"><span data-stu-id="f134c-133">Standard CAS policy does not rely on the <xref:System.Security.Policy.PublisherMembershipCondition>.</span></span> <span data-ttu-id="f134c-134">アプリケーションがカスタム CAS ポリシーを使用してコンピューターで実行される場合、または部分的に信頼された環境で要求を満たす場合を除き、発行者の<xref:System.Security.Permissions.PublisherIdentityPermission>署名の検証に伴う不要な起動コストを回避する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f134c-134">You should avoid the unnecessary startup cost associated with verifying the publisher signature unless your application executes on a computer with custom CAS policy, or is intending to satisfy demands for <xref:System.Security.Permissions.PublisherIdentityPermission> in a partial-trust environment.</span></span> <span data-ttu-id="f134c-135">(ID アクセス許可の要求は、常に完全信頼環境で成功します)。</span><span class="sxs-lookup"><span data-stu-id="f134c-135">(Demands for identity permissions always succeed in a full-trust environment.)</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f134c-136">サービスでは、スタートアップ の`<generatePublisherEvidence>`パフォーマンスを向上させるために、この要素を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f134c-136">We recommend that services use the `<generatePublisherEvidence>` element to improve startup performance.</span></span>  <span data-ttu-id="f134c-137">この要素を使用すると、タイムアウトやサービスの起動のキャンセルを引き起こす遅延を回避することもできます。</span><span class="sxs-lookup"><span data-stu-id="f134c-137">Using this element can also help avoid delays that can cause a time-out and the cancellation of the service startup.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="f134c-138">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="f134c-138">Configuration File</span></span>  
 <span data-ttu-id="f134c-139">この要素は、アプリケーション構成ファイルでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="f134c-139">This element can be used only in the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f134c-140">例</span><span class="sxs-lookup"><span data-stu-id="f134c-140">Example</span></span>  
 <span data-ttu-id="f134c-141">次の例は、アプリケーションの`<generatePublisherEvidence>`CAS 発行者ポリシーのチェックを無効にする要素を使用する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="f134c-141">The following example shows how to use the `<generatePublisherEvidence>` element to disable checking for CAS publisher policy for an application.</span></span>  
  
```xml  
<configuration>  
    <runtime>  
        <generatePublisherEvidence enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f134c-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="f134c-142">See also</span></span>

- [<span data-ttu-id="f134c-143">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="f134c-143">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="f134c-144">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="f134c-144">Configuration File Schema</span></span>](../index.md)
