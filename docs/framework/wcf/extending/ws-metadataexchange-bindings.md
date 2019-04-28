---
title: WS-MetadataExchange のバインディング
ms.date: 03/30/2017
ms.assetid: 10f8de5d-b81d-4ea7-b37e-7f2c00c39714
ms.openlocfilehash: 03e6e6d5ee7e69b397acd0f51b8037f02c1804ec
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61795476"
---
# <a name="ws-metadataexchange-bindings"></a><span data-ttu-id="79190-102">WS-MetadataExchange のバインディング</span><span class="sxs-lookup"><span data-stu-id="79190-102">WS-MetadataExchange Bindings</span></span>
<span data-ttu-id="79190-103">ここでは、既定のメタデータ交換バインディングを各種のトランスポート用に構築する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="79190-103">This topic describes how the default metadata exchange bindings are constructed for various transports.</span></span>  
  
## <a name="the-default-bindings"></a><span data-ttu-id="79190-104">既定のバインディング</span><span class="sxs-lookup"><span data-stu-id="79190-104">The Default Bindings</span></span>  
  
|<span data-ttu-id="79190-105">既定のバインディング名</span><span class="sxs-lookup"><span data-stu-id="79190-105">Default Binding Name</span></span>|<span data-ttu-id="79190-106">バインディングを構築する方法</span><span class="sxs-lookup"><span data-stu-id="79190-106">How the binding is constructed</span></span>|  
|--------------------------|------------------------------------|  
|<span data-ttu-id="79190-107">mexHttpBinding</span><span class="sxs-lookup"><span data-stu-id="79190-107">mexHttpBinding</span></span>|<span data-ttu-id="79190-108">トランスポート レベルのセキュリティが無効な <xref:System.ServiceModel.WSHttpBinding>。</span><span class="sxs-lookup"><span data-stu-id="79190-108">A <xref:System.ServiceModel.WSHttpBinding> with transport-level security disabled.</span></span>|  
|<span data-ttu-id="79190-109">mexHttpsBinding</span><span class="sxs-lookup"><span data-stu-id="79190-109">mexHttpsBinding</span></span>|<span data-ttu-id="79190-110">トランスポート レベルのセキュリティをサポートする <xref:System.ServiceModel.WSHttpBinding>。</span><span class="sxs-lookup"><span data-stu-id="79190-110">A <xref:System.ServiceModel.WSHttpBinding> that supports transport-level security.</span></span>|  
|<span data-ttu-id="79190-111">mexNamedPipeBinding</span><span class="sxs-lookup"><span data-stu-id="79190-111">mexNamedPipeBinding</span></span>|<span data-ttu-id="79190-112"><xref:System.ServiceModel.Channels.CustomBinding> で既定値を使用する <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>。</span><span class="sxs-lookup"><span data-stu-id="79190-112">A  <xref:System.ServiceModel.Channels.CustomBinding> with a <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement> using the default values.</span></span>|  
|<span data-ttu-id="79190-113">mexTcpBinding</span><span class="sxs-lookup"><span data-stu-id="79190-113">mexTcpBinding</span></span>|<span data-ttu-id="79190-114"><xref:System.ServiceModel.Channels.CustomBinding> で既定値を使用する <xref:System.ServiceModel.Channels.TcpTransportBindingElement>。</span><span class="sxs-lookup"><span data-stu-id="79190-114">A <xref:System.ServiceModel.Channels.CustomBinding> with a <xref:System.ServiceModel.Channels.TcpTransportBindingElement> using default values.</span></span>|
