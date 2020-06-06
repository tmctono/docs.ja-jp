---
title: <remove>のの <listeners> 要素<source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/remove
helpviewer_keywords:
- remove element for <listeners> for <source>
- <remove> element for <listeners> for <source>
ms.assetid: 3ff6b578-273d-407f-b07f-8251f1f9f5d0
ms.openlocfilehash: 657e6db2af9b99b3bbf03afc6aab02c58a830f2d
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153336"
---
# <a name="remove-element-for-listeners-for-source"></a><span data-ttu-id="cd776-102">\<remove>のの \<listeners> 要素\<source></span><span class="sxs-lookup"><span data-stu-id="cd776-102">\<remove> Element for \<listeners> for \<source></span></span>
<span data-ttu-id="cd776-103">トレース ソースの `Listeners` コレクションからリスナーを削除します。</span><span class="sxs-lookup"><span data-stu-id="cd776-103">Removes a listener from the `Listeners` collection for a trace source.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**

## <a name="syntax"></a><span data-ttu-id="cd776-104">構文</span><span class="sxs-lookup"><span data-stu-id="cd776-104">Syntax</span></span>  
  
```xml  
<remove name="listenerName" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cd776-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="cd776-105">Attributes and Elements</span></span>  
 <span data-ttu-id="cd776-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="cd776-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cd776-107">属性</span><span class="sxs-lookup"><span data-stu-id="cd776-107">Attributes</span></span>  
  
|<span data-ttu-id="cd776-108">属性</span><span class="sxs-lookup"><span data-stu-id="cd776-108">Attribute</span></span>|<span data-ttu-id="cd776-109">説明</span><span class="sxs-lookup"><span data-stu-id="cd776-109">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="cd776-110">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="cd776-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="cd776-111">コレクションから削除するリスナーの名前 `Listeners` 。</span><span class="sxs-lookup"><span data-stu-id="cd776-111">The name of the listener to remove from the `Listeners` collection.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cd776-112">子要素</span><span class="sxs-lookup"><span data-stu-id="cd776-112">Child Elements</span></span>  
 <span data-ttu-id="cd776-113">なし。</span><span class="sxs-lookup"><span data-stu-id="cd776-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cd776-114">親要素</span><span class="sxs-lookup"><span data-stu-id="cd776-114">Parent Elements</span></span>  
  
|<span data-ttu-id="cd776-115">要素</span><span class="sxs-lookup"><span data-stu-id="cd776-115">Element</span></span>|<span data-ttu-id="cd776-116">Description</span><span class="sxs-lookup"><span data-stu-id="cd776-116">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="cd776-117">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="cd776-117">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="cd776-118">メッセージを収集、格納、およびルーティングするトレース リスナーとトレース スイッチを設定するレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="cd776-118">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="cd776-119">トレース メッセージを開始するトレース ソースを保持します。</span><span class="sxs-lookup"><span data-stu-id="cd776-119">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="cd776-120">トレース メッセージを開始するトレース ソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="cd776-120">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="cd776-121">メッセージを収集、格納、およびルーティングするリスナーを指定します。</span><span class="sxs-lookup"><span data-stu-id="cd776-121">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cd776-122">解説</span><span class="sxs-lookup"><span data-stu-id="cd776-122">Remarks</span></span>  
 <span data-ttu-id="cd776-123">要素は、 `<remove>` 指定されたリスナーを `Listeners` トレースソースのコレクションから削除します。</span><span class="sxs-lookup"><span data-stu-id="cd776-123">The `<remove>` element removes a specified listener from the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="cd776-124">`Listeners` <xref:System.Diagnostics.TraceListenerCollection.Remove%2A> インスタンスのプロパティに対してメソッドを呼び出すことによって、プログラムによってトレースソースのコレクションから要素を削除でき <xref:System.Diagnostics.TraceSource.Listeners%2A> <xref:System.Diagnostics.TraceSource> ます。</span><span class="sxs-lookup"><span data-stu-id="cd776-124">You can remove an element from the `Listeners` collection for a trace source programmatically by calling the <xref:System.Diagnostics.TraceListenerCollection.Remove%2A> method on the <xref:System.Diagnostics.TraceSource.Listeners%2A> property of the <xref:System.Diagnostics.TraceSource> instance.</span></span>  
  
 <span data-ttu-id="cd776-125">この要素は、コンピューターの構成ファイル (machine.config) とアプリケーション構成ファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="cd776-125">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cd776-126">例</span><span class="sxs-lookup"><span data-stu-id="cd776-126">Example</span></span>  
 <span data-ttu-id="cd776-127">次の例では、要素を使用し `<remove>` て、 `<add>` リスナーを `console` `Listeners` トレースソースのコレクションに追加する前に、要素を使用する方法を示し `TraceSourceApp` ます。</span><span class="sxs-lookup"><span data-stu-id="cd776-127">The following example shows how to use the `<remove>` element before using the `<add>` element to add the listener `console` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="TraceSourceApp" switchName="sourceSwitch"
         switchType="System.Diagnostics.SourceSwitch" >  
         <listeners>  
           <remove name="Default"/>  
           <add name="console"
             type="System.Diagnostics.ConsoleTraceListener" />  
         </listeners>  
      </source>  
    </sources>  
  </system.diagnostics>  
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="cd776-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="cd776-128">See also</span></span>

- <xref:System.Diagnostics.TraceSource.Listeners%2A>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="cd776-129">トレースおよびデバッグ設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="cd776-129">Trace and Debug Settings Schema</span></span>](index.md)
- [\<clear>](clear-element-for-listeners-for-source.md)
- [<span data-ttu-id="cd776-130">トレース リスナー</span><span class="sxs-lookup"><span data-stu-id="cd776-130">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
