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
ms.openlocfilehash: e4c44379d9db0f5e98f3ca66ec0486961ec2df3a
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396943"
---
# <a name="isosdacinterfacegetmethoddescdata-method"></a><span data-ttu-id="5759b-102">ISOSDacInterface:: GetMethodDescData メソッド</span><span class="sxs-lookup"><span data-stu-id="5759b-102">ISOSDacInterface::GetMethodDescData Method</span></span>

<span data-ttu-id="5759b-103">指定された MethodDesc ポインターのデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="5759b-103">Gets the data for the given MethodDesc pointer.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="5759b-104">構文</span><span class="sxs-lookup"><span data-stu-id="5759b-104">Syntax</span></span>

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

## <a name="parameters"></a><span data-ttu-id="5759b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5759b-105">Parameters</span></span>

`methodDesc`\
<span data-ttu-id="5759b-106">からMethodDesc のアドレス。</span><span class="sxs-lookup"><span data-stu-id="5759b-106">[in] The address of the MethodDesc.</span></span>

`ip`\
<span data-ttu-id="5759b-107">からメソッドの IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="5759b-107">[in] The IP address of the method.</span></span>

`data`\
<span data-ttu-id="5759b-108">入出力内部 Api から返される MethodDesc に関連付けられたデータ。</span><span class="sxs-lookup"><span data-stu-id="5759b-108">[out] The data associated with the MethodDesc as returned from the internal APIs.</span></span>

`cRevertedRejitVersions`\
<span data-ttu-id="5759b-109">入出力戻された再 jit バージョンの数。</span><span class="sxs-lookup"><span data-stu-id="5759b-109">[out] The number of reverted rejit versions.</span></span>

`rgRevertedRejitData`\
<span data-ttu-id="5759b-110">入出力内部 Api から返された、元に戻された rejit バージョンに関連付けられたデータ。</span><span class="sxs-lookup"><span data-stu-id="5759b-110">[out] The data associated with the reverted rejit versions as returned from the internal APIs.</span></span>

`pcNeededRevertedRejitData`\
<span data-ttu-id="5759b-111">入出力戻された ReJit バージョンに関連付けられたデータを格納するために必要なバイト数。</span><span class="sxs-lookup"><span data-stu-id="5759b-111">[out] The number of bytes required to store the data associated with the reverted ReJit versions.</span></span>

## <a name="remarks"></a><span data-ttu-id="5759b-112">解説</span><span class="sxs-lookup"><span data-stu-id="5759b-112">Remarks</span></span>

<span data-ttu-id="5759b-113">指定されたメソッドはインターフェイスの一部で `ISOSDacInterface` あり、仮想メソッドテーブルの21スロットに対応します。</span><span class="sxs-lookup"><span data-stu-id="5759b-113">The provided method is part of the `ISOSDacInterface` interface and corresponds to the 21st slot of the virtual method table.</span></span> <span data-ttu-id="5759b-114">これらを使用できるようにするには、を [`CLRDATA_ADDRESS`](../common-data-types-unmanaged-api-reference.md) 64 ビット符号なし整数として定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5759b-114">To be able to use them, [`CLRDATA_ADDRESS`](../common-data-types-unmanaged-api-reference.md) must be defined as a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="5759b-115">要件</span><span class="sxs-lookup"><span data-stu-id="5759b-115">Requirements</span></span>

<span data-ttu-id="5759b-116">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5759b-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="5759b-117">**ヘッダー:** 存在</span><span class="sxs-lookup"><span data-stu-id="5759b-117">**Header:** None</span></span>  
<span data-ttu-id="5759b-118">**ライブラリ:** 存在</span><span class="sxs-lookup"><span data-stu-id="5759b-118">**Library:** None</span></span>  
<span data-ttu-id="5759b-119">**.NET Framework のバージョン:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="5759b-119">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="5759b-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="5759b-120">See also</span></span>

- [<span data-ttu-id="5759b-121">デバッグ</span><span class="sxs-lookup"><span data-stu-id="5759b-121">Debugging</span></span>](index.md)
- [<span data-ttu-id="5759b-122">ISOSDacInterface インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5759b-122">ISOSDacInterface Interface</span></span>](isosdacinterface-interface.md)
