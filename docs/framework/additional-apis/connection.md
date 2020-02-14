---
title: Connection クラス (System.Net)
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
ms.openlocfilehash: e9e0f4eed5eb4a7efd27177ab65551afa87fb7f6
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215085"
---
# <a name="connection-class"></a><span data-ttu-id="cb1e6-102">Connection クラス</span><span class="sxs-lookup"><span data-stu-id="cb1e6-102">Connection Class</span></span>

<span data-ttu-id="cb1e6-103">`Connection` クラスは、サーバーの応答、キューの要求、およびパイプライン要求を解析します。</span><span class="sxs-lookup"><span data-stu-id="cb1e6-103">The `Connection` class parses server responses, queue requests, and pipeline requests.</span></span>

## <a name="syntax"></a><span data-ttu-id="cb1e6-104">構文</span><span class="sxs-lookup"><span data-stu-id="cb1e6-104">Syntax</span></span>
  
```csharp  
internal class Connection : PooledStream
```

> [!WARNING]
> <span data-ttu-id="cb1e6-105">`Connection` クラスは内部であり、コードで直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="cb1e6-105">The `Connection` class is internal and is not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="cb1e6-106">Microsoft では、どのような状況でも、実稼働アプリケーションでのこのクラスの使用はサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="cb1e6-106">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="cb1e6-107">要件</span><span class="sxs-lookup"><span data-stu-id="cb1e6-107">Requirements</span></span>

<span data-ttu-id="cb1e6-108">**名前空間:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="cb1e6-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="cb1e6-109">**アセンブリ:** システム (.dll 内)</span><span class="sxs-lookup"><span data-stu-id="cb1e6-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="cb1e6-110">**.NET Framework のバージョン:** 2.0 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="cb1e6-110">**.NET Framework versions:** Available since 2.0.</span></span>
