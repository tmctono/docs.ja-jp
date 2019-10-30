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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5a9041ab75836b4239d492987e94c9104133e9bf
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120036"
---
# <a name="connectiongroup-class"></a><span data-ttu-id="ebcd9-102">ConnectionGroup クラス</span><span class="sxs-lookup"><span data-stu-id="ebcd9-102">ConnectionGroup Class</span></span>

<span data-ttu-id="ebcd9-103">`ConnectionGroup` クラスは、<xref:System.Net.ServicePoint> コンテキスト内の接続の一覧をグループ化し、ネットワークリソース (プロキシや個別のクライアントなど) のコンテキストを維持するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="ebcd9-103">The `ConnectionGroup` class groups a list of connections within the <xref:System.Net.ServicePoint> context and is used to maintain context for network resources (for example, proxies and separate clients).</span></span>

## <a name="syntax"></a><span data-ttu-id="ebcd9-104">構文</span><span class="sxs-lookup"><span data-stu-id="ebcd9-104">Syntax</span></span>
  
```csharp  
internal class ConnectionGroup
```

> [!WARNING]
> <span data-ttu-id="ebcd9-105">`ConnectionGroup` クラスは内部であり、コードで直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="ebcd9-105">The `ConnectionGroup` class is internal and is not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="ebcd9-106">Microsoft では、どのような状況でも、実稼働アプリケーションでのこのクラスの使用はサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="ebcd9-106">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="ebcd9-107">［要件］</span><span class="sxs-lookup"><span data-stu-id="ebcd9-107">Requirements</span></span>

<span data-ttu-id="ebcd9-108">**名前空間:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="ebcd9-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="ebcd9-109">**アセンブリ:** システム (.dll 内)</span><span class="sxs-lookup"><span data-stu-id="ebcd9-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="ebcd9-110">**.NET Framework のバージョン:** 2.0 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="ebcd9-110">**.NET Framework versions:** Available since 2.0.</span></span>
