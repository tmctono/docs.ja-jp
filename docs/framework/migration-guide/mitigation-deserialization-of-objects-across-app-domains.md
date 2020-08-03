---
title: '軽減策: アプリ ドメイン全体でのオブジェクトの逆シリアル化'
description: アプリ ドメイン全体で論理呼び出しコンテキストのオブジェクトを逆シリアル化しようとすると例外がスローされる問題を診断し、軽減する方法について説明します。
ms.date: 03/30/2017
ms.assetid: 30c2d66c-04a8-41a5-ad31-646b937f61b5
ms.openlocfilehash: 20ea0f2f0b49000b7d1993adb583a803d9f5be6c
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475243"
---
# <a name="mitigation-deserialization-of-objects-across-app-domains"></a><span data-ttu-id="27917-103">軽減策:アプリ ドメイン全体でのオブジェクトの逆シリアル化</span><span class="sxs-lookup"><span data-stu-id="27917-103">Mitigation: Deserialization of Objects Across App Domains</span></span>
<span data-ttu-id="27917-104">場合によっては、アプリが異なるアプリケーション ベースを持つ複数のアプリ ドメインを使用すると、アプリ ドメイン間で論理呼び出しコンテキストのオブジェクトを逆シリアル化しようとして、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="27917-104">In some cases, when an app uses two or more app domains with different application bases, the attempt to deserialize objects in the logical call context across app domains throws an exception.</span></span>  
  
## <a name="diagnosing-the-issue"></a><span data-ttu-id="27917-105">問題の診断</span><span class="sxs-lookup"><span data-stu-id="27917-105">Diagnosing the issue</span></span>  
 <span data-ttu-id="27917-106">問題は、次の条件の順序で発生します。</span><span class="sxs-lookup"><span data-stu-id="27917-106">The issue arises under the following sequence of conditions:</span></span>  
  
1. <span data-ttu-id="27917-107">アプリケーションが異なるアプリケーション ベースを持つ複数のアプリ ドメインを使用します。</span><span class="sxs-lookup"><span data-stu-id="27917-107">An app uses two or more app domains with different application bases.</span></span>  
  
2. <span data-ttu-id="27917-108">一部の型は、<xref:System.Runtime.Remoting.Messaging.LogicalCallContext> や <xref:System.Runtime.Remoting.Messaging.LogicalCallContext.SetData%2A?displayProperty=nameWithType> などのメソッドを呼び出して <xref:System.Runtime.Remoting.Messaging.CallContext.LogicalSetData%2A?displayProperty=nameWithType> に明示的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="27917-108">Some types are explicitly added to the <xref:System.Runtime.Remoting.Messaging.LogicalCallContext> by calling a method such as <xref:System.Runtime.Remoting.Messaging.LogicalCallContext.SetData%2A?displayProperty=nameWithType> or <xref:System.Runtime.Remoting.Messaging.CallContext.LogicalSetData%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="27917-109">これらの型は、シリアル化可能としてマークされず、グローバル アセンブリ キャッシュに格納されません。</span><span class="sxs-lookup"><span data-stu-id="27917-109">These types are not marked as serializable and are not stored in the global assembly cache.</span></span>  
  
3. <span data-ttu-id="27917-110">後で、既定以外のアプリ ドメインで実行されているコードは、構成ファイルから値を読み取るか、XML を使用してオブジェクトを逆シリアル化しようとします。</span><span class="sxs-lookup"><span data-stu-id="27917-110">Later, code running in the non-default app domain tries to read a value from a configuration file or use XML to deserialize an object.</span></span>  
  
4. <span data-ttu-id="27917-111">構成ファイルから読み取るか、オブジェクトを逆シリアル化するために、<xref:System.Xml.XmlReader> オブジェクトは構成システムにアクセスしようとします。</span><span class="sxs-lookup"><span data-stu-id="27917-111">In order to read from a configuration file or deserialize the object, an <xref:System.Xml.XmlReader> object tries to access the configuration system.</span></span>  
  
5. <span data-ttu-id="27917-112">構成システムがまだ初期化されていないときは、初期化を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="27917-112">If the configuration system has not already been initialized, it must complete its initialization.</span></span> <span data-ttu-id="27917-113">これは特に、ランタイムが次のように構成システムの固定のパスを作成する必要があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="27917-113">This means, among other things, that the runtime has to create a stable path for a configuration system, which it does as follows:</span></span>  
  
    1. <span data-ttu-id="27917-114">これは既定以外のアプリ ドメインの証拠を検索します。</span><span class="sxs-lookup"><span data-stu-id="27917-114">It looks for evidence for the non-default app domain.</span></span>  
  
    2. <span data-ttu-id="27917-115">既定のアプリ ドメインに基づいて既定以外のアプリ ドメインの証拠を計算しようとします。</span><span class="sxs-lookup"><span data-stu-id="27917-115">It tries to calculate the evidence for the non-default app domain based on the default app domain.</span></span>  
  
    3. <span data-ttu-id="27917-116">既定のアプリ ドメインの証拠を取得するための呼び出しは、既定以外のアプリ ドメインから既定のアプリ ドメインへのアプリ ドメイン間の呼び出しをトリガーします。</span><span class="sxs-lookup"><span data-stu-id="27917-116">The call to get evidence for the default app domain triggers a cross-app domain call from the non-default app domain to the default app domain.</span></span>  
  
    4. <span data-ttu-id="27917-117">.NET Framework のアプリ ドメイン間コントラクトの一部として、論理呼び出しコンテキストの内容も、アプリ ドメインの境界を越えてマーシャリングされる必要があります。</span><span class="sxs-lookup"><span data-stu-id="27917-117">As part of the cross-app domain contract in the .NET Framework, the contents of the logical call context also have to be marshaled across app domain boundaries.</span></span>  
  
6. <span data-ttu-id="27917-118">論理呼び出しコンテキストに含まれる型が既定のアプリ ドメインで解決できないため、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="27917-118">Because the types that are in the logical call context cannot be resolved in the default app domain, an exception is thrown.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="27917-119">軽減策</span><span class="sxs-lookup"><span data-stu-id="27917-119">Mitigation</span></span>  
 <span data-ttu-id="27917-120">この問題を回避するには、次を実行します</span><span class="sxs-lookup"><span data-stu-id="27917-120">To work around this issue, do the following</span></span>  
  
1. <span data-ttu-id="27917-121">例外がスローされたときにコール スタックで `get_Evidence` の呼び出しを検索します。</span><span class="sxs-lookup"><span data-stu-id="27917-121">Look for the call to `get_Evidence` in the call stack when the exception is thrown.</span></span> <span data-ttu-id="27917-122">この例外は、<xref:System.IO.FileNotFoundException> や <xref:System.Runtime.Serialization.SerializationException> などの例外の大きなサブセットであることもあります。</span><span class="sxs-lookup"><span data-stu-id="27917-122">The exception can be any of a large subset of exceptions, including <xref:System.IO.FileNotFoundException> and <xref:System.Runtime.Serialization.SerializationException>.</span></span>  
  
2. <span data-ttu-id="27917-123">オブジェクトが論理呼び出しコンテキストに追加されないアプリ内の場所を特定して、次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="27917-123">Identify the place in the app where no objects are added to the logical call context and add the following code:</span></span>  
  
    ```csharp
    System.Configuration.ConfigurationManager.GetSection("system.xml/xmlReader");  
    ```
  
## <a name="see-also"></a><span data-ttu-id="27917-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="27917-124">See also</span></span>

- [<span data-ttu-id="27917-125">アプリケーションの互換性</span><span class="sxs-lookup"><span data-stu-id="27917-125">Application compatibility</span></span>](application-compatibility.md)
