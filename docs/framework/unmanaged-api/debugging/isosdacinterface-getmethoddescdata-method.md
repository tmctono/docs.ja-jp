---
title: 'ISOSDacInterface:: GetMethodDescData メソッド'
ms.date: 01/16/2019
api.name:
- ISOSDacInterface::GetMethodDescData Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- ISOSDacInterface::GetMethodDescData Method
helpviewer.keywords:
- ISOSDacInterface::GetMethodDescData Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 105149d0abf312c33a8498e7428e3a8b23d6ae7d
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421021"
---
# <a name="isosdacinterfacegetmethoddescdata-method"></a><span data-ttu-id="4a225-102">ISOSDacInterface:: GetMethodDescData メソッド</span><span class="sxs-lookup"><span data-stu-id="4a225-102">ISOSDacInterface::GetMethodDescData Method</span></span>

<span data-ttu-id="4a225-103">指定された MethodDesc ポインターのデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="4a225-103">Gets the data for the given MethodDesc pointer.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="4a225-104">構文</span><span class="sxs-lookup"><span data-stu-id="4a225-104">Syntax</span></span>

```cpp
HRESULT GetMethodDescData(
    CLRDATA_ADDRESS            methodDesc,
    CLRDATA_ADDRESS            ip,
    DacpMethodDescData *data,
    ULONG                      cRevertedRejitVersions,
    DacpReJitData      *rgRevertedRejitData,
    void                      *pcNeededRevertedRejitData
);
```

## <a name="parameters"></a><span data-ttu-id="4a225-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4a225-105">Parameters</span></span>

`methodDesc`\
<span data-ttu-id="4a225-106">からMethodDesc のアドレス。</span><span class="sxs-lookup"><span data-stu-id="4a225-106">[in] The address of the MethodDesc.</span></span>

`ip`\
<span data-ttu-id="4a225-107">からメソッドの IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="4a225-107">[in] The IP address of the method.</span></span>

`data`\
<span data-ttu-id="4a225-108">入出力内部 Api から返される MethodDesc に関連付けられたデータ。</span><span class="sxs-lookup"><span data-stu-id="4a225-108">[out] The data associated with the MethodDesc as returned from the internal APIs.</span></span>

`cRevertedRejitVersions`\
<span data-ttu-id="4a225-109">入出力戻された再 jit バージョンの数。</span><span class="sxs-lookup"><span data-stu-id="4a225-109">[out] The number of reverted rejit versions.</span></span>

`rgRevertedRejitData`\
<span data-ttu-id="4a225-110">入出力内部 Api から返された、元に戻された rejit バージョンに関連付けられたデータ。</span><span class="sxs-lookup"><span data-stu-id="4a225-110">[out] The data associated with the reverted rejit versions as returned from the internal APIs.</span></span>

`pcNeededRevertedRejitData`\
<span data-ttu-id="4a225-111">入出力戻された ReJit バージョンに関連付けられたデータを格納するために必要なバイト数。</span><span class="sxs-lookup"><span data-stu-id="4a225-111">[out] The number of bytes required to store the data associated with the reverted ReJit versions.</span></span>

## <a name="remarks"></a><span data-ttu-id="4a225-112">解説</span><span class="sxs-lookup"><span data-stu-id="4a225-112">Remarks</span></span>

<span data-ttu-id="4a225-113">指定されたメソッドはインターフェイスの一部で `ISOSDacInterface` あり、仮想メソッドテーブルの21スロットに対応します。</span><span class="sxs-lookup"><span data-stu-id="4a225-113">The provided method is part of the `ISOSDacInterface` interface and corresponds to the 21st slot of the virtual method table.</span></span> <span data-ttu-id="4a225-114">これらを使用できるようにするには、を [`CLRDATA_ADDRESS`](../common-data-types-unmanaged-api-reference.md) 64 ビット符号なし整数として定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a225-114">To be able to use them, [`CLRDATA_ADDRESS`](../common-data-types-unmanaged-api-reference.md) must be defined as a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="4a225-115">要件</span><span class="sxs-lookup"><span data-stu-id="4a225-115">Requirements</span></span>

<span data-ttu-id="4a225-116">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a225-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="4a225-117">**ヘッダー:** 存在</span><span class="sxs-lookup"><span data-stu-id="4a225-117">**Header:** None</span></span>  
<span data-ttu-id="4a225-118">**ライブラリ:** 存在</span><span class="sxs-lookup"><span data-stu-id="4a225-118">**Library:** None</span></span>  
<span data-ttu-id="4a225-119">**.NET Framework のバージョン:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="4a225-119">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="4a225-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="4a225-120">See also</span></span>

- [<span data-ttu-id="4a225-121">デバッグ</span><span class="sxs-lookup"><span data-stu-id="4a225-121">Debugging</span></span>](index.md)
- [<span data-ttu-id="4a225-122">ISOSDacInterface インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4a225-122">ISOSDacInterface Interface</span></span>](isosdacinterface-interface.md)
