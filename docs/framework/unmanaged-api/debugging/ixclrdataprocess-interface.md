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
ms.openlocfilehash: 6a6def8fc10f04b89aa8d8c735025b01f9b6ddfb
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420761"
---
# <a name="ixclrdataprocess-interface"></a><span data-ttu-id="2f7e2-102">IXCLRDataProcess インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2f7e2-102">IXCLRDataProcess Interface</span></span>

<span data-ttu-id="2f7e2-103">プロセスに関する情報を照会するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="2f7e2-103">Provides methods for querying information about a process.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="2f7e2-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="2f7e2-104">Methods</span></span>

| <span data-ttu-id="2f7e2-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="2f7e2-105">Method</span></span>                                                                                                                                               | <span data-ttu-id="2f7e2-106">説明</span><span class="sxs-lookup"><span data-stu-id="2f7e2-106">Description</span></span>                                                                                     |
| ---------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="2f7e2-107">GetAppDomainByUniqueId</span><span class="sxs-lookup"><span data-stu-id="2f7e2-107">GetAppDomainByUniqueId</span></span>](ixclrdataprocess-getappdomainbyuniqueid-method.md)                       | <span data-ttu-id="2f7e2-108">`AppDomain`プロセス内のを一意の id で取得します。</span><span class="sxs-lookup"><span data-stu-id="2f7e2-108">Gets an `AppDomain` in a process by its unique id.</span></span>                                              |
| [<span data-ttu-id="2f7e2-109">StartEnumModules</span><span class="sxs-lookup"><span data-stu-id="2f7e2-109">StartEnumModules</span></span>](ixclrdataprocess-startenummodules-method.md)                                   | <span data-ttu-id="2f7e2-110">プロセスのモジュールを列挙するハンドルを提供します。</span><span class="sxs-lookup"><span data-stu-id="2f7e2-110">Provides a handle to enumerate the modules of a process.</span></span>                                        |
| [<span data-ttu-id="2f7e2-111">EnumModule</span><span class="sxs-lookup"><span data-stu-id="2f7e2-111">EnumModule</span></span>](ixclrdataprocess-enummodule-method.md)                                               | <span data-ttu-id="2f7e2-112">このプロセスのモジュールを列挙します。</span><span class="sxs-lookup"><span data-stu-id="2f7e2-112">Enumerates the modules of this process.</span></span>                                                         |
| [<span data-ttu-id="2f7e2-113">EndEnumModules</span><span class="sxs-lookup"><span data-stu-id="2f7e2-113">EndEnumModules</span></span>](ixclrdataprocess-endenummodules-method.md)                                       | <span data-ttu-id="2f7e2-114">モジュールの列挙中に使用される内部反復子によって使用されるリソースを解放します。</span><span class="sxs-lookup"><span data-stu-id="2f7e2-114">Releases the resources used by internal iterators used during module enumeration.</span></span>               |
| [<span data-ttu-id="2f7e2-115">StartEnumMethodInstancesByAddress</span><span class="sxs-lookup"><span data-stu-id="2f7e2-115">StartEnumMethodInstancesByAddress</span></span>](ixclrdataprocess-startenummethodinstancesbyaddress-method.md) | <span data-ttu-id="2f7e2-116">指定されたアドレスから開始するのメソッドインスタンスを列挙するハンドルを提供し `AppDomain` ます。</span><span class="sxs-lookup"><span data-stu-id="2f7e2-116">Provides a handle to enumerate the method instances of `AppDomain` starting at a given address.</span></span> |
| [<span data-ttu-id="2f7e2-117">EnumMethodInstanceByAddress</span><span class="sxs-lookup"><span data-stu-id="2f7e2-117">EnumMethodInstanceByAddress</span></span>](ixclrdataprocess-enummethodinstancebyaddress-method.md)             | <span data-ttu-id="2f7e2-118">このプロセスのメソッドインスタンスを、アドレスオフセットを開始位置として列挙します。</span><span class="sxs-lookup"><span data-stu-id="2f7e2-118">Enumerates the method instances of this process starting at an address offset.</span></span>                  |
| [<span data-ttu-id="2f7e2-119">EndEnumMethodInstancesByAddress</span><span class="sxs-lookup"><span data-stu-id="2f7e2-119">EndEnumMethodInstancesByAddress</span></span>](ixclrdataprocess-endenummethodinstancesbyaddress-method.md)     | <span data-ttu-id="2f7e2-120">インスタンスの列挙中に使用される内部反復子によって使用されるリソースを解放します。</span><span class="sxs-lookup"><span data-stu-id="2f7e2-120">Releases the resources used by internal iterators used during instance enumeration.</span></span>             |

## <a name="remarks"></a><span data-ttu-id="2f7e2-121">解説</span><span class="sxs-lookup"><span data-stu-id="2f7e2-121">Remarks</span></span>

<span data-ttu-id="2f7e2-122">このインターフェイスはランタイム内に存在し、ヘッダーまたはライブラリファイルを介して公開されることはありません。</span><span class="sxs-lookup"><span data-stu-id="2f7e2-122">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="2f7e2-123">ただし、これは、 `IUnknown` `5c552ab6-fc09-4cb3-8e36-22fa03c798b7` 通常の com 機構を通じて取得できる GUID を使用してから派生する com インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="2f7e2-123">However, it's a COM interface that derives from `IUnknown` with GUID `5c552ab6-fc09-4cb3-8e36-22fa03c798b7` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="2f7e2-124">要件</span><span class="sxs-lookup"><span data-stu-id="2f7e2-124">Requirements</span></span>

<span data-ttu-id="2f7e2-125">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f7e2-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>
<span data-ttu-id="2f7e2-126">**ヘッダー:** 存在</span><span class="sxs-lookup"><span data-stu-id="2f7e2-126">**Header:** None</span></span>  
<span data-ttu-id="2f7e2-127">**ライブラリ:** 存在</span><span class="sxs-lookup"><span data-stu-id="2f7e2-127">**Library:** None</span></span>  
<span data-ttu-id="2f7e2-128">**.NET Framework のバージョン:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="2f7e2-128">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="2f7e2-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="2f7e2-129">See also</span></span>

- [<span data-ttu-id="2f7e2-130">デバッグ</span><span class="sxs-lookup"><span data-stu-id="2f7e2-130">Debugging</span></span>](index.md)
- [<span data-ttu-id="2f7e2-131">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="2f7e2-131">Debugging Interfaces</span></span>](debugging-interfaces.md)
