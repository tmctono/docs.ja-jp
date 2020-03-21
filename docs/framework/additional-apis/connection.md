---
title: 接続クラス (System.Net)
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
ms.openlocfilehash: dc0a594f7ae2bb9fc1883ec7ef672805bbc08778
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79156182"
---
# <a name="connection-class"></a><span data-ttu-id="564b7-102">Connection クラス</span><span class="sxs-lookup"><span data-stu-id="564b7-102">Connection Class</span></span>

<span data-ttu-id="564b7-103">この`Connection`クラスは、サーバーの応答、キュー要求、およびパイプライン要求を解析します。</span><span class="sxs-lookup"><span data-stu-id="564b7-103">The `Connection` class parses server responses, queue requests, and pipeline requests.</span></span>

## <a name="syntax"></a><span data-ttu-id="564b7-104">構文</span><span class="sxs-lookup"><span data-stu-id="564b7-104">Syntax</span></span>
  
```csharp  
internal class Connection : PooledStream
```

> [!WARNING]
> <span data-ttu-id="564b7-105">クラス`Connection`は内部クラスであり、コード内で直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="564b7-105">The `Connection` class is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="564b7-106">マイクロソフトでは、どのような状況でも、運用環境のアプリケーションでこのクラスを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="564b7-106">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="564b7-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="564b7-107">Requirements</span></span>

<span data-ttu-id="564b7-108">**名前空間:**<xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="564b7-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="564b7-109">**アセンブリ:** システム (システム.dll 内)</span><span class="sxs-lookup"><span data-stu-id="564b7-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="564b7-110">**.NET フレームワークのバージョン:** 2.0 以降で利用可能。</span><span class="sxs-lookup"><span data-stu-id="564b7-110">**.NET Framework versions:** Available since 2.0.</span></span>
