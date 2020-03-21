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
ms.openlocfilehash: 8ebc97112d2044efca85520ee942ed0f587529ee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79156156"
---
# <a name="connectiongroup-class"></a><span data-ttu-id="233ea-102">ConnectionGroup クラス</span><span class="sxs-lookup"><span data-stu-id="233ea-102">ConnectionGroup Class</span></span>

<span data-ttu-id="233ea-103">この`ConnectionGroup`クラスは、コンテキスト内の接続の<xref:System.Net.ServicePoint>リストをグループ化し、ネットワーク リソース (プロキシやクライアントの分離など) のコンテキストを維持するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="233ea-103">The `ConnectionGroup` class groups a list of connections within the <xref:System.Net.ServicePoint> context and is used to maintain context for network resources (for example, proxies and separate clients).</span></span>

## <a name="syntax"></a><span data-ttu-id="233ea-104">構文</span><span class="sxs-lookup"><span data-stu-id="233ea-104">Syntax</span></span>
  
```csharp  
internal class ConnectionGroup
```

> [!WARNING]
> <span data-ttu-id="233ea-105">クラス`ConnectionGroup`は内部クラスであり、コード内で直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="233ea-105">The `ConnectionGroup` class is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="233ea-106">マイクロソフトでは、どのような状況でも、運用環境のアプリケーションでこのクラスを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="233ea-106">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="233ea-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="233ea-107">Requirements</span></span>

<span data-ttu-id="233ea-108">**名前空間:**<xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="233ea-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="233ea-109">**アセンブリ:** システム (システム.dll 内)</span><span class="sxs-lookup"><span data-stu-id="233ea-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="233ea-110">**.NET フレームワークのバージョン:** 2.0 以降で利用可能。</span><span class="sxs-lookup"><span data-stu-id="233ea-110">**.NET Framework versions:** Available since 2.0.</span></span>
