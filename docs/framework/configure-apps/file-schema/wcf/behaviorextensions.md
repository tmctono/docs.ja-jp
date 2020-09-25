---
title: <behaviorExtensions>
ms.date: 03/30/2017
ms.assetid: 59f2791a-c78f-40d7-aa80-0d9cd10135d9
ms.openlocfilehash: 27bf9e380df1586b42cbe96a628a794364fae743
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204971"
---
# \<behaviorExtensions>

<span data-ttu-id="fd904-101">動作の拡張により、ユーザーはユーザー定義の動作要素を作成できます。</span><span class="sxs-lookup"><span data-stu-id="fd904-101">Behavior extensions enable the user to create user-defined behavior elements.</span></span> <span data-ttu-id="fd904-102">これらの要素は、標準の Windows Communication Foundation (WCF) 動作要素と共に使用できます。</span><span class="sxs-lookup"><span data-stu-id="fd904-102">These elements can be used alongside the standard Windows Communication Foundation (WCF) behavior elements.</span></span> <span data-ttu-id="fd904-103">`behaviorExtensions` セクションでは、構成で使用できるように要素を定義します。</span><span class="sxs-lookup"><span data-stu-id="fd904-103">The `behaviorExtensions` section defines the element such that it can be used in configuration.</span></span> <span data-ttu-id="fd904-104">次の例は、一般的な動作拡張を示します。</span><span class="sxs-lookup"><span data-stu-id="fd904-104">Here is an example of a typical behavior extension.</span></span>  
  
```xml  
<system.serviceModel>
  <extensions>
    <behaviorExtensions>
      <add name="myBehavior"
           type="Microsoft.ServiceModel.Samples.MyBehaviorSection, MyBehavior,
                 Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />
    </behaviorExtensions>
  </extensions>
</system.serviceModel>
```  
  
 <span data-ttu-id="fd904-105">構成機能を要素に追加するには、構成要素を記述して登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd904-105">To add configuration abilities to the element, you need to write and register a configuration element.</span></span> <span data-ttu-id="fd904-106">詳細については、<xref:System.Configuration> を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd904-106">For more information on this, see the <xref:System.Configuration> documentation.</span></span>  
  
 <span data-ttu-id="fd904-107">要素とその構成の型を定義したら、次の例に示すように拡張を使用できます。</span><span class="sxs-lookup"><span data-stu-id="fd904-107">After the element and its configuration type are defined, the extension can be used, as shown in the following example.</span></span>  
  
```xml  
<behaviors>
  <behavior configurationName="testChannelBehavior">
    <myBehavior />
    <channelSecurity cacheCookies="false"
                     detectReplays="false"
                     maxCachedNonces="9"
                     maxClockSkew="00:00:03"
                     maxCookieCachingTime="00:07:24"
                     replayWindow="00:07:22.2190000" />
  </behavior>
</behaviors>
```  
  
## <a name="security"></a><span data-ttu-id="fd904-108">Security</span><span class="sxs-lookup"><span data-stu-id="fd904-108">Security</span></span>  

 <span data-ttu-id="fd904-109">`machine.config` ファイルと `app.config` ファイルに型を登録する場合は、完全修飾アセンブリ名の使用を強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="fd904-109">It is strongly recommended that you use fully qualified assembly names when registering types in the `machine.config` and `app.config` files.</span></span> <span data-ttu-id="fd904-110">型が一意に定義されていない場合、CLR 型ローダーは次の場所を指定された順序で検索します。</span><span class="sxs-lookup"><span data-stu-id="fd904-110">If the type is not uniquely defined, the CLR type loader searches for it in the following locations in the specified order:</span></span>  
  
 <span data-ttu-id="fd904-111">型のアセンブリが判明している場合、ローダーは構成ファイルのリダイレクトの場所、GAC、構成情報を使用する現在のアセンブリ、およびアプリケーションの基本ディレクトリを検索します。</span><span class="sxs-lookup"><span data-stu-id="fd904-111">If the assembly of the type is known, the loader searches the configuration file's redirect locations, GAC, the current assembly using configuration information, and the application base directory.</span></span> <span data-ttu-id="fd904-112">アセンブリが判明していない場合、ローダーは現在のアセンブリ、mscorlib、および `TypeResolve` イベント ハンドラーによって返される場所を検索します。</span><span class="sxs-lookup"><span data-stu-id="fd904-112">If the assembly is unknown, the loader searches the current assembly, mscorlib, and the location returned by the `TypeResolve` event handler.</span></span> <span data-ttu-id="fd904-113">この CLR 検索順序は、Type Forwarding 機構や AppDomain.TypeResolve イベントなどのフックを使用して変更できます。</span><span class="sxs-lookup"><span data-stu-id="fd904-113">This CLR search order can be modified with hooks such as the Type Forwarding mechanism and the AppDomain.TypeResolve event.</span></span>  
  
 <span data-ttu-id="fd904-114">攻撃者が CLR 検索順序を悪用して、未承認のコードを実行する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fd904-114">An attacker can exploit the CLR search order and execute unauthorized code.</span></span> <span data-ttu-id="fd904-115">完全修飾名 (厳密な名前) を使用することで型が一意に識別され、システムのセキュリティが強化されます。</span><span class="sxs-lookup"><span data-stu-id="fd904-115">Using fully qualified (strong) names uniquely identifies a type and further increases security of your system.</span></span>  
  
 <span data-ttu-id="fd904-116">詳細については、「 [ランタイムがアセンブリを検索する方法](../../../deployment/how-the-runtime-locates-assemblies.md) 」と「」を参照してください <xref:System.AppDomain.TypeResolve> 。</span><span class="sxs-lookup"><span data-stu-id="fd904-116">For more information, see [How the Runtime Locates Assemblies](../../../deployment/how-the-runtime-locates-assemblies.md) and <xref:System.AppDomain.TypeResolve>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd904-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="fd904-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.BehaviorExtensionElement>
- [<span data-ttu-id="fd904-118">動作を使用したランタイムの構成と拡張</span><span class="sxs-lookup"><span data-stu-id="fd904-118">Configuring and Extending the Runtime with Behaviors</span></span>](../../../wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
