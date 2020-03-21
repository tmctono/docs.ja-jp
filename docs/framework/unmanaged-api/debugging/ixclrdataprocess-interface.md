---
title: IXCLRDataProcess インターフェイス
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess Interface
helpviewer.keywords:
- IXCLRDataProcess Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: e7e53615e38d0ab76f9e7c0a753be3c13780057d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178372"
---
# <a name="ixclrdataprocess-interface"></a><span data-ttu-id="24f6b-102">IXCLRDataProcess インターフェイス</span><span class="sxs-lookup"><span data-stu-id="24f6b-102">IXCLRDataProcess Interface</span></span>

<span data-ttu-id="24f6b-103">プロセスに関する情報を照会するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="24f6b-103">Provides methods for querying information about a process.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="24f6b-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="24f6b-104">Methods</span></span>

| <span data-ttu-id="24f6b-105">Method</span><span class="sxs-lookup"><span data-stu-id="24f6b-105">Method</span></span>                                                                                                                                               | <span data-ttu-id="24f6b-106">説明</span><span class="sxs-lookup"><span data-stu-id="24f6b-106">Description</span></span>                                                                                     |
| ---------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="24f6b-107">GetAppDomainByUniqueId</span><span class="sxs-lookup"><span data-stu-id="24f6b-107">GetAppDomainByUniqueId</span></span>](ixclrdataprocess-getappdomainbyuniqueid-method.md)                       | <span data-ttu-id="24f6b-108">一意`AppDomain`の ID を使用してプロセス内の を取得します。</span><span class="sxs-lookup"><span data-stu-id="24f6b-108">Gets an `AppDomain` in a process by its unique id.</span></span>                                              |
| [<span data-ttu-id="24f6b-109">StartEnumModules</span><span class="sxs-lookup"><span data-stu-id="24f6b-109">StartEnumModules</span></span>](ixclrdataprocess-startenummodules-method.md)                                   | <span data-ttu-id="24f6b-110">プロセスのモジュールを列挙するハンドルを提供します。</span><span class="sxs-lookup"><span data-stu-id="24f6b-110">Provides a handle to enumerate the modules of a process.</span></span>                                        |
| [<span data-ttu-id="24f6b-111">EnumModule</span><span class="sxs-lookup"><span data-stu-id="24f6b-111">EnumModule</span></span>](ixclrdataprocess-enummodule-method.md)                                               | <span data-ttu-id="24f6b-112">このプロセスのモジュールを列挙します。</span><span class="sxs-lookup"><span data-stu-id="24f6b-112">Enumerates the modules of this process.</span></span>                                                         |
| [<span data-ttu-id="24f6b-113">EndEnumModules</span><span class="sxs-lookup"><span data-stu-id="24f6b-113">EndEnumModules</span></span>](ixclrdataprocess-endenummodules-method.md)                                       | <span data-ttu-id="24f6b-114">モジュールの列挙時に使用される内部反復子によって使用されるリソースを解放します。</span><span class="sxs-lookup"><span data-stu-id="24f6b-114">Releases the resources used by internal iterators used during module enumeration.</span></span>               |
| [<span data-ttu-id="24f6b-115">StartEnumMethodInstancesByAddress</span><span class="sxs-lookup"><span data-stu-id="24f6b-115">StartEnumMethodInstancesByAddress</span></span>](ixclrdataprocess-startenummethodinstancesbyaddress-method.md) | <span data-ttu-id="24f6b-116">指定したアドレス`AppDomain`から開始するメソッド インスタンスを列挙するハンドルを提供します。</span><span class="sxs-lookup"><span data-stu-id="24f6b-116">Provides a handle to enumerate the method instances of `AppDomain` starting at a given address.</span></span> |
| [<span data-ttu-id="24f6b-117">EnumMethodInstanceByAddress</span><span class="sxs-lookup"><span data-stu-id="24f6b-117">EnumMethodInstanceByAddress</span></span>](ixclrdataprocess-enummethodinstancebyaddress-method.md)             | <span data-ttu-id="24f6b-118">アドレス オフセットから開始するこのプロセスのメソッド インスタンスを列挙します。</span><span class="sxs-lookup"><span data-stu-id="24f6b-118">Enumerates the method instances of this process starting at an address offset.</span></span>                  |
| [<span data-ttu-id="24f6b-119">EndEnumMethodInstancesByAddress</span><span class="sxs-lookup"><span data-stu-id="24f6b-119">EndEnumMethodInstancesByAddress</span></span>](ixclrdataprocess-endenummethodinstancesbyaddress-method.md)     | <span data-ttu-id="24f6b-120">インスタンスの列挙時に使用される内部反復子によって使用されるリソースを解放します。</span><span class="sxs-lookup"><span data-stu-id="24f6b-120">Releases the resources used by internal iterators used during instance enumeration.</span></span>             |

## <a name="remarks"></a><span data-ttu-id="24f6b-121">解説</span><span class="sxs-lookup"><span data-stu-id="24f6b-121">Remarks</span></span>

<span data-ttu-id="24f6b-122">このインターフェイスはランタイム内に存在し、ヘッダーやライブラリ ファイルを通じて公開されません。</span><span class="sxs-lookup"><span data-stu-id="24f6b-122">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="24f6b-123">ただし、通常の COM メカニズムを通じて取得`IUnknown`できる`5c552ab6-fc09-4cb3-8e36-22fa03c798b7`GUID から派生する COM インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="24f6b-123">However, it's a COM interface that derives from `IUnknown` with GUID `5c552ab6-fc09-4cb3-8e36-22fa03c798b7` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="24f6b-124">必要条件</span><span class="sxs-lookup"><span data-stu-id="24f6b-124">Requirements</span></span>

<span data-ttu-id="24f6b-125">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24f6b-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>
<span data-ttu-id="24f6b-126">**ヘッダー:** なし</span><span class="sxs-lookup"><span data-stu-id="24f6b-126">**Header:** None</span></span>  
<span data-ttu-id="24f6b-127">**ライブラリ:** なし</span><span class="sxs-lookup"><span data-stu-id="24f6b-127">**Library:** None</span></span>  
<span data-ttu-id="24f6b-128">**.NET Framework のバージョン:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="24f6b-128">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="24f6b-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="24f6b-129">See also</span></span>

- [<span data-ttu-id="24f6b-130">デバッグ</span><span class="sxs-lookup"><span data-stu-id="24f6b-130">Debugging</span></span>](index.md)
- [<span data-ttu-id="24f6b-131">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="24f6b-131">Debugging Interfaces</span></span>](debugging-interfaces.md)
