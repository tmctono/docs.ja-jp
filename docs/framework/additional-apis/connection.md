---
title: Connection クラス (System.Net)
description: .NET の Connection クラスについて説明します。 このクラスは、サーバーの応答、キューの要求、およびパイプライン要求を解析します。 System.NET 名前空間にあります。
ms.date: 05/01/2017
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.Connection
api_location:
- System.dll
api_type:
- Assembly
ms.assetid: 6f0b8902-f31c-4ab9-a8c9-de43228995ec
ms.openlocfilehash: cb28724ed782fc5395dc74e9c59249ebdea44ddf
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "84989823"
---
# <a name="connection-class"></a><span data-ttu-id="740c1-105">Connection クラス</span><span class="sxs-lookup"><span data-stu-id="740c1-105">Connection Class</span></span>

<span data-ttu-id="740c1-106">クラスは、 `Connection` サーバーの応答、キューの要求、およびパイプライン要求を解析します。</span><span class="sxs-lookup"><span data-stu-id="740c1-106">The `Connection` class parses server responses, queue requests, and pipeline requests.</span></span>

## <a name="syntax"></a><span data-ttu-id="740c1-107">構文</span><span class="sxs-lookup"><span data-stu-id="740c1-107">Syntax</span></span>
  
```csharp  
internal class Connection : PooledStream
```

> [!WARNING]
> <span data-ttu-id="740c1-108">`Connection`クラスは内部であり、コードで直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="740c1-108">The `Connection` class is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="740c1-109">Microsoft では、どのような状況でも、実稼働アプリケーションでのこのクラスの使用はサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="740c1-109">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="740c1-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="740c1-110">Requirements</span></span>

<span data-ttu-id="740c1-111">**名前空間:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="740c1-111">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="740c1-112">**アセンブリ:** システム (System.dll)</span><span class="sxs-lookup"><span data-stu-id="740c1-112">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="740c1-113">**.NET Framework のバージョン:** 2.0 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="740c1-113">**.NET Framework versions:** Available since 2.0.</span></span>
