---
title: PooledStream. NetworkStream プロパティ (System.Net)
ms.date: 10/21/2019
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.PooledStream.NetworkStream
- System.Net.PooledStream.get_NetworkStream
- System.Net.PooledStream.set_NetworkStream
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: 541b8c94b30675c1286b48a2291c3bd3e4aeea0b
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2019
ms.locfileid: "72847230"
---
# <a name="pooledstreamnetworkstream-property"></a><span data-ttu-id="8039f-102">PooledStream. NetworkStream プロパティ</span><span class="sxs-lookup"><span data-stu-id="8039f-102">PooledStream.NetworkStream Property</span></span>

<span data-ttu-id="8039f-103">`PooledStream` ソケットのネットワークストリームを取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="8039f-103">Gets or sets the network stream for the `PooledStream` socket.</span></span>

## <a name="syntax"></a><span data-ttu-id="8039f-104">構文</span><span class="sxs-lookup"><span data-stu-id="8039f-104">Syntax</span></span>

```csharp
internal NetworkStream NetworkStream { get; set; }
```

## <a name="property-value"></a><span data-ttu-id="8039f-105">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="8039f-105">Property value</span></span>

<xref:System.Net.Sockets.NetworkStream>  
<span data-ttu-id="8039f-106">`PooledStream` ソケットのネットワークストリーム。</span><span class="sxs-lookup"><span data-stu-id="8039f-106">The network stream for the `PooledStream` socket.</span></span>

## <a name="remarks"></a><span data-ttu-id="8039f-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="8039f-107">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="8039f-108">`PooledStream.NetworkStream` プロパティは内部であり、コードで直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="8039f-108">The `PooledStream.NetworkStream` property is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="8039f-109">Microsoft では、どのような状況でも、実稼働アプリケーションでのこのプロパティの使用はサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="8039f-109">Microsoft does not support the use of this property in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="8039f-110">［要件］</span><span class="sxs-lookup"><span data-stu-id="8039f-110">Requirements</span></span>

<span data-ttu-id="8039f-111">**名前空間:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="8039f-111">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="8039f-112">**アセンブリ:** システム (.dll 内)</span><span class="sxs-lookup"><span data-stu-id="8039f-112">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="8039f-113">**.NET Framework のバージョン:** 2.0 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="8039f-113">**.NET Framework versions:** Available since 2.0.</span></span>
