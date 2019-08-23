---
title: <behaviorExtensions>
ms.date: 03/30/2017
ms.assetid: 59f2791a-c78f-40d7-aa80-0d9cd10135d9
ms.openlocfilehash: bcf1f1dcdba50c3e7fba8eb170132d0cf47c4271
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919813"
---
# <a name="behaviorextensions"></a><span data-ttu-id="98618-101">\<動作拡張機能 ></span><span class="sxs-lookup"><span data-stu-id="98618-101">\<behaviorExtensions></span></span>
<span data-ttu-id="98618-102">動作の拡張により、ユーザーはユーザー定義の動作要素を作成できます。</span><span class="sxs-lookup"><span data-stu-id="98618-102">Behavior extensions enable the user to create user-defined behavior elements.</span></span> <span data-ttu-id="98618-103">これらの要素は、標準の Windows Communication Foundation (WCF) 動作要素と共に使用できます。</span><span class="sxs-lookup"><span data-stu-id="98618-103">These elements can be used alongside the standard Windows Communication Foundation (WCF) behavior elements.</span></span> <span data-ttu-id="98618-104">`behaviorExtensions` セクションでは、構成で使用できるように要素を定義します。</span><span class="sxs-lookup"><span data-stu-id="98618-104">The `behaviorExtensions` section defines the element such that it can be used in configuration.</span></span> <span data-ttu-id="98618-105">次の例は、一般的な動作拡張を示します。</span><span class="sxs-lookup"><span data-stu-id="98618-105">Here is an example of a typical behavior extension.</span></span>  
  
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
  
 <span data-ttu-id="98618-106">構成機能を要素に追加するには、構成要素を記述して登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="98618-106">To add configuration abilities to the element, you need to write and register a configuration element.</span></span> <span data-ttu-id="98618-107">詳細については、<xref:System.Configuration> を参照してください。</span><span class="sxs-lookup"><span data-stu-id="98618-107">For more information on this, see the <xref:System.Configuration> documentation.</span></span>  
  
 <span data-ttu-id="98618-108">要素とその構成の型を定義したら、次の例に示すように拡張を使用できます。</span><span class="sxs-lookup"><span data-stu-id="98618-108">After the element and its configuration type are defined, the extension can be used, as shown in the following example.</span></span>  
  
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
  
## <a name="security"></a><span data-ttu-id="98618-109">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="98618-109">Security</span></span>  
 <span data-ttu-id="98618-110">`machine.config` ファイルと `app.config` ファイルに型を登録する場合は、完全修飾アセンブリ名の使用を強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="98618-110">It is strongly recommended that you use fully qualified assembly names when registering types in the `machine.config` and `app.config` files.</span></span> <span data-ttu-id="98618-111">型が一意に定義されていない場合、CLR 型ローダーは次の場所を指定された順序で検索します。</span><span class="sxs-lookup"><span data-stu-id="98618-111">If the type is not uniquely defined, the CLR type loader searches for it in the following locations in the specified order:</span></span>  
  
 <span data-ttu-id="98618-112">型のアセンブリが判明している場合、ローダーは構成ファイルのリダイレクトの場所、GAC、構成情報を使用する現在のアセンブリ、およびアプリケーションの基本ディレクトリを検索します。</span><span class="sxs-lookup"><span data-stu-id="98618-112">If the assembly of the type is known, the loader searches the configuration file's redirect locations, GAC, the current assembly using configuration information, and the application base directory.</span></span> <span data-ttu-id="98618-113">アセンブリが判明していない場合、ローダーは現在のアセンブリ、mscorlib、および `TypeResolve` イベント ハンドラーによって返される場所を検索します。</span><span class="sxs-lookup"><span data-stu-id="98618-113">If the assembly is unknown, the loader searches the current assembly, mscorlib, and the location returned by the `TypeResolve` event handler.</span></span> <span data-ttu-id="98618-114">この CLR 検索順序は、Type Forwarding 機構や AppDomain.TypeResolve イベントなどのフックを使用して変更できます。</span><span class="sxs-lookup"><span data-stu-id="98618-114">This CLR search order can be modified with hooks such as the Type Forwarding mechanism and the AppDomain.TypeResolve event.</span></span>  
  
 <span data-ttu-id="98618-115">攻撃者が CLR 検索順序を悪用して、未承認のコードを実行する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="98618-115">An attacker can exploit the CLR search order and execute unauthorized code.</span></span> <span data-ttu-id="98618-116">(厳密な) 完全修飾名を使用すると、型が一意に識別され、システムのセキュリティがさらに強化されます。</span><span class="sxs-lookup"><span data-stu-id="98618-116">Using fully qualified (strong) names uniquely identifies a type and further increases security of your system.</span></span>  
  
 <span data-ttu-id="98618-117">詳細については、「[ランタイムがアセンブリを検索する方法](https://go.microsoft.com/fwlink/?LinkId=95336)」と<xref:System.AppDomain.TypeResolve>「」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="98618-117">For more information, see [How the Runtime Locates Assemblies](https://go.microsoft.com/fwlink/?LinkId=95336) and <xref:System.AppDomain.TypeResolve>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98618-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="98618-118">See also</span></span>

- <xref:System.ServiceModel.Configuration.BehaviorExtensionElement>
- [<span data-ttu-id="98618-119">動作を使用したランタイムの構成と拡張</span><span class="sxs-lookup"><span data-stu-id="98618-119">Configuring and Extending the Runtime with Behaviors</span></span>](../../../wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
