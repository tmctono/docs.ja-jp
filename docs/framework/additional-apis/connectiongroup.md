---
title: ConnectionGroup クラス
ms.date: 05/01/2017
topic_type:
- apiref
api_name:
- System.Net.ConnectionGroup
api_location:
- System.dll
api_type:
- Assembly
ms.assetid: 25c08217-fdeb-44b9-9cd6-1b4955d6e602
ms.openlocfilehash: 9620eb25837a5cf6dd592f4222e0fa5a13751278
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "77214929"
---
# <a name="connectiongroup-class"></a><span data-ttu-id="05c3b-102">ConnectionGroup クラス</span><span class="sxs-lookup"><span data-stu-id="05c3b-102">ConnectionGroup Class</span></span>

<span data-ttu-id="05c3b-103">`ConnectionGroup` クラスは、<xref:System.Net.ServicePoint> コンテキスト内の接続の一覧をグループ化し、ネットワークリソース (プロキシや個別のクライアントなど) のコンテキストを維持するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="05c3b-103">The `ConnectionGroup` class groups a list of connections within the <xref:System.Net.ServicePoint> context and is used to maintain context for network resources (for example, proxies and separate clients).</span></span>

## <a name="syntax"></a><span data-ttu-id="05c3b-104">構文</span><span class="sxs-lookup"><span data-stu-id="05c3b-104">Syntax</span></span>
  
```csharp  
internal class ConnectionGroup
```

> [!WARNING]
> <span data-ttu-id="05c3b-105">`ConnectionGroup` クラスは内部であり、コードで直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="05c3b-105">The `ConnectionGroup` class is internal and is not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="05c3b-106">Microsoft では、どのような状況でも、実稼働アプリケーションでのこのクラスの使用はサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="05c3b-106">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="05c3b-107">要件</span><span class="sxs-lookup"><span data-stu-id="05c3b-107">Requirements</span></span>

<span data-ttu-id="05c3b-108">**名前空間:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="05c3b-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="05c3b-109">**アセンブリ:** システム (.dll 内)</span><span class="sxs-lookup"><span data-stu-id="05c3b-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="05c3b-110">**.NET Framework のバージョン:** 2.0 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="05c3b-110">**.NET Framework versions:** Available since 2.0.</span></span>
