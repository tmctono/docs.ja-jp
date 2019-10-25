---
title: SslState. Sslstate プロパティ (システム .Net. Security)
ms.date: 10/21/2019
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.Security.SslState.SslProtocol
- System.Net.Security.SslState.get_SslProtocol
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: 6983ac071dad29b240308031ecd0a3562a6856e4
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2019
ms.locfileid: "72847248"
---
# <a name="sslstatesslprotocol-property"></a><span data-ttu-id="8e5bf-102">SslState. Sslstate プロパティ</span><span class="sxs-lookup"><span data-stu-id="8e5bf-102">SslState.SslProtocol Property</span></span>

<span data-ttu-id="8e5bf-103">SSL プロトコルのバージョンを取得します。</span><span class="sxs-lookup"><span data-stu-id="8e5bf-103">Gets the SSL protocol versions.</span></span>

## <a name="syntax"></a><span data-ttu-id="8e5bf-104">構文</span><span class="sxs-lookup"><span data-stu-id="8e5bf-104">Syntax</span></span>

```csharp
internal SslProtocols SslProtocol { get; }
```

## <a name="property-value"></a><span data-ttu-id="8e5bf-105">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="8e5bf-105">Property value</span></span>

<xref:System.Security.Authentication.SslProtocols>  
<span data-ttu-id="8e5bf-106">SSL プロトコルのバージョンを指定する列挙値のビットごとの組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="8e5bf-106">A bitwise combination of the enumeration values that specify the SSL protocol versions.</span></span>

## <a name="remarks"></a><span data-ttu-id="8e5bf-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="8e5bf-107">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="8e5bf-108">`SslState.SslProtocol` プロパティは内部であり、コードで直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="8e5bf-108">The `SslState.SslProtocol` property is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="8e5bf-109">Microsoft では、どのような状況でも、実稼働アプリケーションでのこのプロパティの使用はサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="8e5bf-109">Microsoft does not support the use of this property in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="8e5bf-110">［要件］</span><span class="sxs-lookup"><span data-stu-id="8e5bf-110">Requirements</span></span>

<span data-ttu-id="8e5bf-111">**名前空間:** <xref:System.Net.Security></span><span class="sxs-lookup"><span data-stu-id="8e5bf-111">**Namespace:** <xref:System.Net.Security></span></span>

<span data-ttu-id="8e5bf-112">**アセンブリ:** システム (.dll 内)</span><span class="sxs-lookup"><span data-stu-id="8e5bf-112">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="8e5bf-113">**.NET Framework のバージョン:** 2.0 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="8e5bf-113">**.NET Framework versions:** Available since 2.0.</span></span>
