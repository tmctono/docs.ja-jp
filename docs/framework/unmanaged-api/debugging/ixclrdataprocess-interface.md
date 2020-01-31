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
ms.openlocfilehash: a5d707d61513b030e5968af28db3c2a606e4419b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790371"
---
# <a name="ixclrdataprocess-interface"></a><span data-ttu-id="d5331-102">IXCLRDataProcess インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d5331-102">IXCLRDataProcess Interface</span></span>

<span data-ttu-id="d5331-103">プロセスに関する情報を照会するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="d5331-103">Provides methods for querying information about a process.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="d5331-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="d5331-104">Methods</span></span>

| <span data-ttu-id="d5331-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="d5331-105">Method</span></span>                                                                                                                                               | <span data-ttu-id="d5331-106">説明</span><span class="sxs-lookup"><span data-stu-id="d5331-106">Description</span></span>                                                                                     |
| ---------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="d5331-107">GetAppDomainByUniqueId</span><span class="sxs-lookup"><span data-stu-id="d5331-107">GetAppDomainByUniqueId</span></span>](ixclrdataprocess-getappdomainbyuniqueid-method.md)                       | <span data-ttu-id="d5331-108">プロセス内の一意の id によって `AppDomain` を取得します。</span><span class="sxs-lookup"><span data-stu-id="d5331-108">Gets an `AppDomain` in a process by its unique id.</span></span>                                              |
| [<span data-ttu-id="d5331-109">StartEnumModules</span><span class="sxs-lookup"><span data-stu-id="d5331-109">StartEnumModules</span></span>](ixclrdataprocess-startenummodules-method.md)                                   | <span data-ttu-id="d5331-110">プロセスのモジュールを列挙するハンドルを提供します。</span><span class="sxs-lookup"><span data-stu-id="d5331-110">Provides a handle to enumerate the modules of a process.</span></span>                                        |
| [<span data-ttu-id="d5331-111">EnumModule</span><span class="sxs-lookup"><span data-stu-id="d5331-111">EnumModule</span></span>](ixclrdataprocess-enummodule-method.md)                                               | <span data-ttu-id="d5331-112">このプロセスのモジュールを列挙します。</span><span class="sxs-lookup"><span data-stu-id="d5331-112">Enumerates the modules of this process.</span></span>                                                         |
| [<span data-ttu-id="d5331-113">EndEnumModules</span><span class="sxs-lookup"><span data-stu-id="d5331-113">EndEnumModules</span></span>](ixclrdataprocess-endenummodules-method.md)                                       | <span data-ttu-id="d5331-114">モジュールの列挙中に使用される内部反復子によって使用されるリソースを解放します。</span><span class="sxs-lookup"><span data-stu-id="d5331-114">Releases the resources used by internal iterators used during module enumeration.</span></span>               |
| [<span data-ttu-id="d5331-115">StartEnumMethodInstancesByAddress</span><span class="sxs-lookup"><span data-stu-id="d5331-115">StartEnumMethodInstancesByAddress</span></span>](ixclrdataprocess-startenummethodinstancesbyaddress-method.md) | <span data-ttu-id="d5331-116">指定されたアドレスから始まる `AppDomain` のメソッドインスタンスを列挙するハンドルを提供します。</span><span class="sxs-lookup"><span data-stu-id="d5331-116">Provides a handle to enumerate the method instances of `AppDomain` starting at a given address.</span></span> |
| [<span data-ttu-id="d5331-117">EnumMethodInstanceByAddress</span><span class="sxs-lookup"><span data-stu-id="d5331-117">EnumMethodInstanceByAddress</span></span>](ixclrdataprocess-enummethodinstancebyaddress-method.md)             | <span data-ttu-id="d5331-118">このプロセスのメソッドインスタンスを、アドレスオフセットを開始位置として列挙します。</span><span class="sxs-lookup"><span data-stu-id="d5331-118">Enumerates the method instances of this process starting at an address offset.</span></span>                  |
| [<span data-ttu-id="d5331-119">EndEnumMethodInstancesByAddress</span><span class="sxs-lookup"><span data-stu-id="d5331-119">EndEnumMethodInstancesByAddress</span></span>](ixclrdataprocess-endenummethodinstancesbyaddress-method.md)     | <span data-ttu-id="d5331-120">インスタンスの列挙中に使用される内部反復子によって使用されるリソースを解放します。</span><span class="sxs-lookup"><span data-stu-id="d5331-120">Releases the resources used by internal iterators used during instance enumeration.</span></span>             |

## <a name="remarks"></a><span data-ttu-id="d5331-121">コメント</span><span class="sxs-lookup"><span data-stu-id="d5331-121">Remarks</span></span>

<span data-ttu-id="d5331-122">このインターフェイスはランタイム内に存在し、ヘッダーまたはライブラリファイルを介して公開されることはありません。</span><span class="sxs-lookup"><span data-stu-id="d5331-122">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="d5331-123">ただし、これは、通常の COM 機構を通じて取得できる GUID `5c552ab6-fc09-4cb3-8e36-22fa03c798b7` を `IUnknown` から派生する COM インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="d5331-123">However, it's a COM interface that derives from `IUnknown` with GUID `5c552ab6-fc09-4cb3-8e36-22fa03c798b7` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="d5331-124">要件</span><span class="sxs-lookup"><span data-stu-id="d5331-124">Requirements</span></span>

<span data-ttu-id="d5331-125">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5331-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>   
<span data-ttu-id="d5331-126">**ヘッダー:** 存在</span><span class="sxs-lookup"><span data-stu-id="d5331-126">**Header:** None</span></span>  
<span data-ttu-id="d5331-127">**ライブラリ:** 存在</span><span class="sxs-lookup"><span data-stu-id="d5331-127">**Library:** None</span></span>  
<span data-ttu-id="d5331-128">**.NET Framework のバージョン:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="d5331-128">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="d5331-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="d5331-129">See also</span></span>

- [<span data-ttu-id="d5331-130">デバッグ</span><span class="sxs-lookup"><span data-stu-id="d5331-130">Debugging</span></span>](index.md)
- [<span data-ttu-id="d5331-131">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d5331-131">Debugging Interfaces</span></span>](debugging-interfaces.md)
