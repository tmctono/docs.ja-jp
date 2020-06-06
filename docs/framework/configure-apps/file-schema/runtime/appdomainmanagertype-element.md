---
title: <appDomainManagerType> 要素
ms.date: 03/30/2017
helpviewer_keywords:
- appDomainManagerType element
- <appDomainManagerType> element
ms.assetid: ae8d5a7e-e7f7-47f7-98d9-455cc243a322
ms.openlocfilehash: 8eb6129b3fafaeb81a94d5a4078e41a16583a226
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154428"
---
# <a name="appdomainmanagertype-element"></a><span data-ttu-id="11c62-102">\<appDomainManagerType> 要素</span><span class="sxs-lookup"><span data-stu-id="11c62-102">\<appDomainManagerType> Element</span></span>
<span data-ttu-id="11c62-103">既定のアプリケーション ドメインのアプリケーション ドメイン マネージャーの役割を果たす種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="11c62-103">Specifies the type that serves as the application domain manager for the default application domain.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<appDomainManagerType>**  
  
## <a name="syntax"></a><span data-ttu-id="11c62-104">構文</span><span class="sxs-lookup"><span data-stu-id="11c62-104">Syntax</span></span>  
  
```xml  
<appDomainManagerAssembly
   value="type name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="11c62-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="11c62-105">Attributes and Elements</span></span>  
 <span data-ttu-id="11c62-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="11c62-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="11c62-107">属性</span><span class="sxs-lookup"><span data-stu-id="11c62-107">Attributes</span></span>  
  
|<span data-ttu-id="11c62-108">属性</span><span class="sxs-lookup"><span data-stu-id="11c62-108">Attribute</span></span>|<span data-ttu-id="11c62-109">説明</span><span class="sxs-lookup"><span data-stu-id="11c62-109">Description</span></span>|  
|---------------|-----------------|  
|`value`|<span data-ttu-id="11c62-110">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="11c62-110">Required attribute.</span></span> <span data-ttu-id="11c62-111">プロセス内の既定のアプリケーションドメインのアプリケーションドメインマネージャーとして機能する、名前空間を含む型の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="11c62-111">Specifies the name of the type, including the namespace, that serves as the application domain manager for the default application domain in the process.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="11c62-112">子要素</span><span class="sxs-lookup"><span data-stu-id="11c62-112">Child Elements</span></span>  
 <span data-ttu-id="11c62-113">なし。</span><span class="sxs-lookup"><span data-stu-id="11c62-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="11c62-114">親要素</span><span class="sxs-lookup"><span data-stu-id="11c62-114">Parent Elements</span></span>  
  
|<span data-ttu-id="11c62-115">要素</span><span class="sxs-lookup"><span data-stu-id="11c62-115">Element</span></span>|<span data-ttu-id="11c62-116">Description</span><span class="sxs-lookup"><span data-stu-id="11c62-116">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="11c62-117">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="11c62-117">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="11c62-118">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="11c62-118">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="11c62-119">解説</span><span class="sxs-lookup"><span data-stu-id="11c62-119">Remarks</span></span>  
 <span data-ttu-id="11c62-120">アプリケーションドメインマネージャーの種類を指定するには、この要素と要素の両方を指定する必要があり [\<appDomainManagerAssembly>](appdomainmanagerassembly-element.md) ます。</span><span class="sxs-lookup"><span data-stu-id="11c62-120">To specify the type of the application domain manager, you must specify both this element and the [\<appDomainManagerAssembly>](appdomainmanagerassembly-element.md) element.</span></span> <span data-ttu-id="11c62-121">これらの要素のいずれかが指定されていない場合、もう一方は無視されます。</span><span class="sxs-lookup"><span data-stu-id="11c62-121">If either of these elements is not specified, the other is ignored.</span></span>  
  
 <span data-ttu-id="11c62-122">既定のアプリケーションドメインが読み込まれると、指定した <xref:System.TypeLoadException> 型が要素によって指定されたアセンブリに存在しない場合にがスローされ、 [\<appDomainManagerAssembly>](appdomainmanagerassembly-element.md) プロセスを開始できなくなります。</span><span class="sxs-lookup"><span data-stu-id="11c62-122">When the default application domain is loaded, <xref:System.TypeLoadException> is thrown if the specified type does not exist in the assembly that is specified by the [\<appDomainManagerAssembly>](appdomainmanagerassembly-element.md) element; and the process fails to start.</span></span>  
  
 <span data-ttu-id="11c62-123">既定のアプリケーションドメインに対してアプリケーションドメインマネージャーの種類を指定すると、既定のアプリケーションドメインから作成された他のアプリケーションドメインは、アプリケーションドメインマネージャーの種類を継承します。</span><span class="sxs-lookup"><span data-stu-id="11c62-123">When you specify the application domain manager type for the default application domain, other application domains created from the default application domain inherit the application domain manager type.</span></span> <span data-ttu-id="11c62-124">プロパティとプロパティを使用して、 <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> 新しいアプリケーションドメインに別のアプリケーションドメインマネージャーの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="11c62-124">Use the <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> and <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> properties to specify a different application domain manager type for a new application domain.</span></span>  
  
 <span data-ttu-id="11c62-125">アプリケーションドメインマネージャーの種類を指定するには、アプリケーションが完全に信頼されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="11c62-125">Specifying the application domain manager type requires the application to have full trust.</span></span> <span data-ttu-id="11c62-126">(たとえば、デスクトップで実行されているアプリケーションには完全な信頼があります)。アプリケーションが完全に信頼されていない場合は、 <xref:System.TypeLoadException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="11c62-126">(For example, an application running on the desktop has full trust.) If the application does not have full trust, a <xref:System.TypeLoadException> is thrown.</span></span>  
  
 <span data-ttu-id="11c62-127">型と名前空間の形式は、プロパティで使用される形式と同じです <xref:System.Type.FullName%2A?displayProperty=nameWithType> 。</span><span class="sxs-lookup"><span data-stu-id="11c62-127">The format of the type and namespace is the same format that is used for the <xref:System.Type.FullName%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="11c62-128">この構成要素は、.NET Framework 4 以降でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="11c62-128">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="11c62-129">例</span><span class="sxs-lookup"><span data-stu-id="11c62-129">Example</span></span>  
 <span data-ttu-id="11c62-130">次の例は、プロセスの既定のアプリケーションドメインのアプリケーションドメインマネージャーがアセンブリ内の型であることを指定する方法を示してい `MyMgr` `AdMgrExample` ます。</span><span class="sxs-lookup"><span data-stu-id="11c62-130">The following example shows how to specify that the application domain manager for the default application domain of a process is the `MyMgr` type in the `AdMgrExample` assembly.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainManagerType value="MyMgr" />  
      <appDomainManagerAssembly
         value="AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="11c62-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="11c62-131">See also</span></span>

- <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>
- <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>
- [<span data-ttu-id="11c62-132">\<appDomainManagerAssembly>Element</span><span class="sxs-lookup"><span data-stu-id="11c62-132">\<appDomainManagerAssembly> Element</span></span>](appdomainmanagerassembly-element.md)
- [<span data-ttu-id="11c62-133">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="11c62-133">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="11c62-134">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="11c62-134">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="11c62-135">SetAppDomainManagerType メソッド</span><span class="sxs-lookup"><span data-stu-id="11c62-135">SetAppDomainManagerType Method</span></span>](../../../unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)
