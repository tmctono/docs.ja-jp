---
title: COM アプリケーションとの統合の概要
ms.date: 03/30/2017
helpviewer_keywords:
- COM [WCF], integration overview
ms.assetid: 02c5697f-6e2e-47d6-b715-f3a28aebfbd5
ms.openlocfilehash: 2be428f0ae83596a4398fc9830af40d05f6ab191
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64638652"
---
# <a name="integrating-with-com-applications-overview"></a><span data-ttu-id="e0161-102">COM アプリケーションとの統合の概要</span><span class="sxs-lookup"><span data-stu-id="e0161-102">Integrating with COM Applications Overview</span></span>
<span data-ttu-id="e0161-103">Windows Communication Foundation (WCF) は、マネージ コードを開発者には、接続型アプリケーションを作成するための豊富な環境を提供します。</span><span class="sxs-lookup"><span data-stu-id="e0161-103">Windows Communication Foundation (WCF) provides the managed code developer with a rich environment for creating connected applications.</span></span> <span data-ttu-id="e0161-104">ただし、アンマネージ COM ベースのコードにかなりの投資がある、移行したくない場合は、まだ統合できます WCF Web サービスの既存のコードに直接 WCF サービス モニカーを使用しています。</span><span class="sxs-lookup"><span data-stu-id="e0161-104">However, if you have a substantial investment in unmanaged COM-based code and do not want to migrate, you can still integrate WCF Web services directly into your existing code by using the WCF service moniker.</span></span> <span data-ttu-id="e0161-105">サービス モニカーは Office VBA、Visual Basic 6.0、または Visual C++ 6.0 などの幅広い COM ベースの開発環境で使用可能です。</span><span class="sxs-lookup"><span data-stu-id="e0161-105">The service moniker can be used from a wide range of COM-based development environments, such as Office VBA, Visual Basic 6.0, or Visual C++ 6.0.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e0161-106">サービス モニカーでは、WCF の通信チャネルを使用して、すべての通信。</span><span class="sxs-lookup"><span data-stu-id="e0161-106">The service moniker uses a WCF communication channel for all communication.</span></span> <span data-ttu-id="e0161-107">このチャネルのセキュリティ メカニズムと識別メカニズムは、標準の COM および DCOM プロキシで使用されるものとは異なります。</span><span class="sxs-lookup"><span data-stu-id="e0161-107">The security and identity mechanisms for that channel differ from those used in standard COM and DCOM proxies.</span></span> <span data-ttu-id="e0161-108">さらに、サービス モニカーは WCF 通信チャネルは、既定のタイムアウト期間を使用するためには、1 分間のすべての呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="e0161-108">In addition, because the service moniker uses a WCF communication channel the default timeout period is one minute for all calls.</span></span>  
  
 <span data-ttu-id="e0161-109">サービス モニカーを併用、 `GetObject` WCF Web サービスを呼び出すための厳密に型指定された、COM に固有の方法で、アンマネージ開発者を提供する関数。</span><span class="sxs-lookup"><span data-stu-id="e0161-109">The service moniker is used with the `GetObject` function to provide the unmanaged developer with a strongly-typed, COM-specific approach for calling WCF Web services.</span></span> <span data-ttu-id="e0161-110">これは、ローカル、WCF Web サービスのコントラクトおよび使用するバインディングの定義を COM から参照できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0161-110">This requires a local, COM-visible definition of the WCF Web service contract and the binding that is to be used.</span></span> <span data-ttu-id="e0161-111">他の WCF クライアントのようにこのチャネルの構築は、最初のメソッド呼び出し時に COM プログラマに対して透過的に実行が、サービス モニカーは、サービスに型指定されたチャネルを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0161-111">Like other WCF clients, the service moniker must construct a typed channel to the service, though this channel construction occurs transparently to the COM programmer on the first method call.</span></span>  
  
 <span data-ttu-id="e0161-112">他の WCF クライアント、モニカーを使用する場合、共通のアプリケーションは、アドレス、バインド、およびサービスと通信するコントラクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="e0161-112">In common with other WCF clients, when using the moniker, applications specify the address, binding and contract to communicate with a service.</span></span> <span data-ttu-id="e0161-113">コントラクトは、次のいずれかの方法で指定できます。</span><span class="sxs-lookup"><span data-stu-id="e0161-113">The contract can be specified in one of the following ways:</span></span>  
  
- <span data-ttu-id="e0161-114">型指定のあるコントラクト - クライアント コンピューターで COM から参照できる型として登録されます。</span><span class="sxs-lookup"><span data-stu-id="e0161-114">Typed contract – the contract is registered as a COM visible type on the client machine.</span></span>  
  
- <span data-ttu-id="e0161-115">WSDL コントラクト - WSDL ドキュメントという形で供給されます。</span><span class="sxs-lookup"><span data-stu-id="e0161-115">WSDL contract – the contract is supplied in the form of a WSDL document.</span></span>  
  
- <span data-ttu-id="e0161-116">MEX コントラクト - 実行時に Metadata Exchange (MEX) エンドポイントから取得されます。</span><span class="sxs-lookup"><span data-stu-id="e0161-116">MEX contract – the contract is retrieved at runtime from a Metadata Exchange (MEX) endpoint.</span></span>  
  
## <a name="parameters-supported-by-the-service-moniker"></a><span data-ttu-id="e0161-117">サービス モニカーでサポートされるパラメーター</span><span class="sxs-lookup"><span data-stu-id="e0161-117">Parameters Supported by the Service Moniker</span></span>  
 <span data-ttu-id="e0161-118">サービス モニカーでサポートされるパラメーターを次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="e0161-118">The following table shows the parameters that are supported by the service moniker.</span></span>  
  
|<span data-ttu-id="e0161-119">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e0161-119">Parameter</span></span>|<span data-ttu-id="e0161-120">説明</span><span class="sxs-lookup"><span data-stu-id="e0161-120">Description</span></span>|  
|---------------|-----------------|  
|`address`|<span data-ttu-id="e0161-121">サービスの URL 位置。</span><span class="sxs-lookup"><span data-stu-id="e0161-121">URL location of the service.</span></span>|  
|`binding`|<span data-ttu-id="e0161-122">アプリケーション構成のバインディング セクションの名前。</span><span class="sxs-lookup"><span data-stu-id="e0161-122">Binding section name from the application configuration.</span></span>|  
|`bindingConfiguration`|<span data-ttu-id="e0161-123">名前付きバインディング セクション内の名前付きバインディング インスタンス。</span><span class="sxs-lookup"><span data-stu-id="e0161-123">Named binding instance from within the named binding section.</span></span>|  
|`contract`|<span data-ttu-id="e0161-124">サービス コントラクトまたは (MEX の) コントラクト名を表すインターフェイス識別子 (IID)。</span><span class="sxs-lookup"><span data-stu-id="e0161-124">Interface identifier (IID) that represents the service contract or the contract name (from MEX).</span></span>|  
|`wsdl`|<span data-ttu-id="e0161-125">代替形式のコントラクト定義を提供する WSDL ドキュメント。</span><span class="sxs-lookup"><span data-stu-id="e0161-125">WSDL document that provides an alternative form of contract definition.</span></span>|  
|`spnIdentity`|<span data-ttu-id="e0161-126">サービスとの通信に使用するサーバー プリンシパル名 (SPN) ID。</span><span class="sxs-lookup"><span data-stu-id="e0161-126">Server principal name (SPN) identity to be used to communicate with the service.</span></span>|  
|`upnIdentity`|<span data-ttu-id="e0161-127">サービスとの通信に使用するユーザー プリンシパル名 (UPN) ID。</span><span class="sxs-lookup"><span data-stu-id="e0161-127">User principal name (UPN) identity to be used to communicate with the service.</span></span>|  
|`dnsIdentity`|<span data-ttu-id="e0161-128">サービスとの通信に使用する DNS ID。</span><span class="sxs-lookup"><span data-stu-id="e0161-128">DNS identity to be used to communicate with the service.</span></span>|  
|`mexAddress`|<span data-ttu-id="e0161-129">サービスの Metadata Exchange (MEX) エンドポイントの URL 位置。</span><span class="sxs-lookup"><span data-stu-id="e0161-129">URL location of the Metadata Exchange (MEX) endpoint of the service.</span></span>|  
|`mexBinding`|<span data-ttu-id="e0161-130">MEX エンドポイントと接続するための、アプリケーション構成のバインディング セクションの名前。</span><span class="sxs-lookup"><span data-stu-id="e0161-130">Binding section name from the application configuration to connect with the MEX endpoint.</span></span>|  
|`mexBindingConfiguration`|<span data-ttu-id="e0161-131">MEX エンドポイントと接続する名前付きバインディング セクション内の名前付きバインディング インスタンス。</span><span class="sxs-lookup"><span data-stu-id="e0161-131">Named binding instance from within the named binding section to connect with the MEX endpoint.</span></span>|  
|`bindingNamespace`|<span data-ttu-id="e0161-132">取得する MEX のバインディング セクション名の名前空間。</span><span class="sxs-lookup"><span data-stu-id="e0161-132">Namespace of the binding section name from the retrieved MEX.</span></span>|  
|`contractNamespace`|<span data-ttu-id="e0161-133">取得する MEX のコントラクトの名前空間。</span><span class="sxs-lookup"><span data-stu-id="e0161-133">Namespace of the contract from the retrieved MEX.</span></span>|  
|`mexSpnIdentity`|<span data-ttu-id="e0161-134">MEX エンドポイントとの通信に使用するサーバー プリンシパル名 (SPN) ID。</span><span class="sxs-lookup"><span data-stu-id="e0161-134">Server principal name (SPN) identity to be used to communicate with the MEX endpoint.</span></span>|  
|`mexUpnIdentity`|<span data-ttu-id="e0161-135">MEX エンドポイントとの通信に使用するユーザー プリンシパル名 (UPN) ID。</span><span class="sxs-lookup"><span data-stu-id="e0161-135">User principal name (UPN) identity to be used to communicate with the MEX endpoint.</span></span>|  
|`mexDnsIdentity`|<span data-ttu-id="e0161-136">MEX エンドポイントとの通信に使用する DNS ID。</span><span class="sxs-lookup"><span data-stu-id="e0161-136">DNS identity to be used to communicate with the MEX endpoint.</span></span>|  
|`serializer`|<span data-ttu-id="e0161-137">"XML" シリアライザーと "datacontract" シリアライザーのいずれを使用するかを指定します。</span><span class="sxs-lookup"><span data-stu-id="e0161-137">Specify the use of either the "xml" or "datacontract" serializer.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="e0161-138">完全な COM ベースのクライアントと共に使用している場合でもサービス モニカーには、クライアント コンピューターにインストールするには、WCF とサポートの .NET Framework 2.0 が必要です。</span><span class="sxs-lookup"><span data-stu-id="e0161-138">Even when used with entirely COM-based clients, the service moniker requires WCF and the supporting .NET Framework 2.0 to be installed on the client computer.</span></span> <span data-ttu-id="e0161-139">また、サービス モニカーを使用するクライアント アプリケーションには、適切なバージョンの .NET Framework ランタイムが読み込まれていることが重要です。</span><span class="sxs-lookup"><span data-stu-id="e0161-139">It is also critical that client applications that use the service moniker load the appropriate version of the .NET Framework runtime.</span></span> <span data-ttu-id="e0161-140">Office アプリケーション内でモニカーを使用する場合、構成ファイルに、正しいフレームワーク バージョンが読み込まれていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0161-140">When using the moniker within Office applications, a configuration file may be required to ensure that the correct framework version is loaded.</span></span> <span data-ttu-id="e0161-141">たとえば Excel の場合、Excel.exe ファイルと同じディレクトリにある Excel.exe.config というファイルに、次のテキストが記述されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0161-141">For example, with Excel, the following text should be placed in a file called Excel.exe.config in the same directory as the Excel.exe file:</span></span>  
>   
>  `<?xml version="1.0" encoding="utf-8"?>`  
>   
>  <span data-ttu-id="e0161-142">`<configuration xmlns=` `http://schemas.microsoft.com/.NetConfiguration/v2.0` `>`</span><span class="sxs-lookup"><span data-stu-id="e0161-142">`<configuration xmlns=` `http://schemas.microsoft.com/.NetConfiguration/v2.0` `>`</span></span>  
>   
>  `<startup>`  
>   
>  `<requiredRuntime version="v2.0.50727" />`  
>   
>  `</startup>`  
>   
>  `</configuration>`  
  
## <a name="see-also"></a><span data-ttu-id="e0161-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="e0161-143">See also</span></span>

- [<span data-ttu-id="e0161-144">方法: 登録し、サービス モニカーの構成</span><span class="sxs-lookup"><span data-stu-id="e0161-144">How to: Register and Configure a Service Moniker</span></span>](../../../../docs/framework/wcf/feature-details/how-to-register-and-configure-a-service-moniker.md)
