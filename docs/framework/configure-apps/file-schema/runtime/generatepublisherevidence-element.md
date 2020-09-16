---
title: <generatePublisherEvidence> 要素
ms.date: 03/30/2017
helpviewer_keywords:
- generatePublisherEvidence element
- <generatePublisherEvidence> element
ms.assetid: 7d208f50-e8d5-4a42-bc1a-1cf3590706a8
ms.openlocfilehash: 11592b055641c0fa2d2b968547dcc5aa40c94600
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90541785"
---
# <a name="generatepublisherevidence-element"></a><span data-ttu-id="4b02c-102">\<generatePublisherEvidence> 要素</span><span class="sxs-lookup"><span data-stu-id="4b02c-102">\<generatePublisherEvidence> Element</span></span>
<span data-ttu-id="4b02c-103">ランタイムが <xref:System.Security.Policy.Publisher> コードアクセスセキュリティ (CAS) の証拠を作成するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="4b02c-103">Specifies whether the runtime creates <xref:System.Security.Policy.Publisher> evidence for code access security (CAS).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<generatePublisherEvidence>**  
  
## <a name="syntax"></a><span data-ttu-id="4b02c-104">構文</span><span class="sxs-lookup"><span data-stu-id="4b02c-104">Syntax</span></span>  
  
```xml  
<generatePublisherEvidence
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4b02c-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="4b02c-105">Attributes and Elements</span></span>  
 <span data-ttu-id="4b02c-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="4b02c-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4b02c-107">属性</span><span class="sxs-lookup"><span data-stu-id="4b02c-107">Attributes</span></span>  
  
|<span data-ttu-id="4b02c-108">属性</span><span class="sxs-lookup"><span data-stu-id="4b02c-108">Attribute</span></span>|<span data-ttu-id="4b02c-109">説明</span><span class="sxs-lookup"><span data-stu-id="4b02c-109">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="4b02c-110">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="4b02c-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="4b02c-111">ランタイムが証拠を作成するかどうかを指定し <xref:System.Security.Policy.Publisher> ます。</span><span class="sxs-lookup"><span data-stu-id="4b02c-111">Specifies whether the runtime creates <xref:System.Security.Policy.Publisher> evidence.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="4b02c-112">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="4b02c-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="4b02c-113">[値]</span><span class="sxs-lookup"><span data-stu-id="4b02c-113">Value</span></span>|<span data-ttu-id="4b02c-114">説明</span><span class="sxs-lookup"><span data-stu-id="4b02c-114">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="4b02c-115">は <xref:System.Security.Policy.Publisher> 証拠を作成しません。</span><span class="sxs-lookup"><span data-stu-id="4b02c-115">Does not create <xref:System.Security.Policy.Publisher> evidence.</span></span>|  
|`true`|<span data-ttu-id="4b02c-116"><xref:System.Security.Policy.Publisher>証拠を作成します。</span><span class="sxs-lookup"><span data-stu-id="4b02c-116">Creates <xref:System.Security.Policy.Publisher> evidence.</span></span> <span data-ttu-id="4b02c-117">これは既定値です。</span><span class="sxs-lookup"><span data-stu-id="4b02c-117">This is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4b02c-118">子要素</span><span class="sxs-lookup"><span data-stu-id="4b02c-118">Child Elements</span></span>  
 <span data-ttu-id="4b02c-119">なし。</span><span class="sxs-lookup"><span data-stu-id="4b02c-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4b02c-120">親要素</span><span class="sxs-lookup"><span data-stu-id="4b02c-120">Parent Elements</span></span>  
  
|<span data-ttu-id="4b02c-121">要素</span><span class="sxs-lookup"><span data-stu-id="4b02c-121">Element</span></span>|<span data-ttu-id="4b02c-122">説明</span><span class="sxs-lookup"><span data-stu-id="4b02c-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="4b02c-123">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="4b02c-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="4b02c-124">ランタイム初期化オプションに関する情報を含んでいます。</span><span class="sxs-lookup"><span data-stu-id="4b02c-124">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4b02c-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="4b02c-125">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4b02c-126">.NET Framework 4 以降では、この要素はアセンブリの読み込み時間に影響しません。</span><span class="sxs-lookup"><span data-stu-id="4b02c-126">In the .NET Framework 4 and later, this element has no effect on assembly load times.</span></span> <span data-ttu-id="4b02c-127">詳細については、「セキュリティの [変更](/previous-versions/dotnet/framework/security/security-changes)」の「セキュリティポリシーの簡略化」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b02c-127">For more information, see the "Security Policy Simplification" section in [Security Changes](/previous-versions/dotnet/framework/security/security-changes).</span></span>  
  
 <span data-ttu-id="4b02c-128">共通言語ランタイム (CLR) は、読み込み時に Authenticode 署名を検証して、アセンブリの証拠を作成しようとし <xref:System.Security.Policy.Publisher> ます。</span><span class="sxs-lookup"><span data-stu-id="4b02c-128">The common language runtime (CLR) tries to verify the Authenticode signature at load time to create <xref:System.Security.Policy.Publisher> evidence for the assembly.</span></span> <span data-ttu-id="4b02c-129">ただし、既定では、ほとんどのアプリケーションは証拠を必要としません <xref:System.Security.Policy.Publisher> 。</span><span class="sxs-lookup"><span data-stu-id="4b02c-129">However, by default, most applications do not need <xref:System.Security.Policy.Publisher> evidence.</span></span> <span data-ttu-id="4b02c-130">標準の CAS ポリシーは、に依存 <xref:System.Security.Policy.PublisherMembershipCondition> しません。</span><span class="sxs-lookup"><span data-stu-id="4b02c-130">Standard CAS policy does not rely on the <xref:System.Security.Policy.PublisherMembershipCondition>.</span></span> <span data-ttu-id="4b02c-131">カスタム CAS ポリシーを使用しているコンピューターでアプリケーションを実行する場合や、部分信頼環境での要求を満たす場合を除き、発行元の署名の検証に関連する不要な起動コストを回避する必要があり <xref:System.Security.Permissions.PublisherIdentityPermission> ます。</span><span class="sxs-lookup"><span data-stu-id="4b02c-131">You should avoid the unnecessary startup cost associated with verifying the publisher signature unless your application executes on a computer with custom CAS policy, or is intending to satisfy demands for <xref:System.Security.Permissions.PublisherIdentityPermission> in a partial-trust environment.</span></span> <span data-ttu-id="4b02c-132">(Id 権限の要求は、完全に信頼された環境では常に成功します)。</span><span class="sxs-lookup"><span data-stu-id="4b02c-132">(Demands for identity permissions always succeed in a full-trust environment.)</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4b02c-133">サービスでは、要素を使用して起動時のパフォーマンスを向上させることをお勧めし `<generatePublisherEvidence>` ます。</span><span class="sxs-lookup"><span data-stu-id="4b02c-133">We recommend that services use the `<generatePublisherEvidence>` element to improve startup performance.</span></span>  <span data-ttu-id="4b02c-134">また、この要素を使用すると、タイムアウトを発生させたり、サービスの開始をキャンセルしたりする可能性がある遅延を回避することもできます。</span><span class="sxs-lookup"><span data-stu-id="4b02c-134">Using this element can also help avoid delays that can cause a time-out and the cancellation of the service startup.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="4b02c-135">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="4b02c-135">Configuration File</span></span>  
 <span data-ttu-id="4b02c-136">この要素は、アプリケーション構成ファイルでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="4b02c-136">This element can be used only in the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4b02c-137">例</span><span class="sxs-lookup"><span data-stu-id="4b02c-137">Example</span></span>  
 <span data-ttu-id="4b02c-138">次の例は、要素を使用して、 `<generatePublisherEvidence>` アプリケーションの CAS 発行者ポリシーのチェックを無効にする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="4b02c-138">The following example shows how to use the `<generatePublisherEvidence>` element to disable checking for CAS publisher policy for an application.</span></span>  
  
```xml  
<configuration>  
    <runtime>  
        <generatePublisherEvidence enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4b02c-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="4b02c-139">See also</span></span>

- [<span data-ttu-id="4b02c-140">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="4b02c-140">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="4b02c-141">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="4b02c-141">Configuration File Schema</span></span>](../index.md)
