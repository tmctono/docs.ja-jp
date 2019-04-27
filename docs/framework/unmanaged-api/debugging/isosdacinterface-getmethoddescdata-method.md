---
title: ISOSDacInterface::GetMethodDescData メソッド
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
ms.openlocfilehash: 4e32facc65162c4deb853cd507a00126e5f786e7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61914876"
---
# <a name="isosdacinterfacegetmethoddescdata-method"></a><span data-ttu-id="14449-102">ISOSDacInterface::GetMethodDescData メソッド</span><span class="sxs-lookup"><span data-stu-id="14449-102">ISOSDacInterface::GetMethodDescData Method</span></span>

<span data-ttu-id="14449-103">指定した MethodDesc ポインターのデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="14449-103">Gets the data for the given MethodDesc pointer.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="14449-104">構文</span><span class="sxs-lookup"><span data-stu-id="14449-104">Syntax</span></span>

```
HRESULT GetMethodDescData(
    CLRDATA_ADDRESS            methodDesc,
    CLRDATA_ADDRESS            ip,
    DacpMethodDescData *data,
    ULONG                      cRevertedRejitVersions,
    DacpReJitData      *rgRevertedRejitData,
    void                      *pcNeededRevertedRejitData
);
```

## <a name="parameters"></a><span data-ttu-id="14449-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="14449-105">Parameters</span></span>

`methodDesc`\
<span data-ttu-id="14449-106">[in]MethodDesc アドレス。</span><span class="sxs-lookup"><span data-stu-id="14449-106">[in] The address of the MethodDesc.</span></span>

`ip`\
<span data-ttu-id="14449-107">[in]メソッドの IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="14449-107">[in] The IP address of the method.</span></span>

`data`\
<span data-ttu-id="14449-108">[out]関連付けられている、MethodDesc 内部 Api から返されるデータ。</span><span class="sxs-lookup"><span data-stu-id="14449-108">[out] The data associated with the MethodDesc as returned from the internal APIs.</span></span>

`cRevertedRejitVersions`\
<span data-ttu-id="14449-109">[out]元に戻された rejit バージョンの数。</span><span class="sxs-lookup"><span data-stu-id="14449-109">[out] The number of reverted rejit versions.</span></span>

`rgRevertedRejitData`\
<span data-ttu-id="14449-110">[out]内部 Api から返されるように、元に戻された rejit バージョンに関連付けられたデータ。</span><span class="sxs-lookup"><span data-stu-id="14449-110">[out] The data associated with the reverted rejit versions as returned from the internal APIs.</span></span>

`pcNeededRevertedRejitData`\
<span data-ttu-id="14449-111">[out]元に戻された ReJit バージョンに関連付けられたデータを格納するために必要なバイト数。</span><span class="sxs-lookup"><span data-stu-id="14449-111">[out] The number of bytes required to store the data associated with the reverted ReJit versions.</span></span>

## <a name="remarks"></a><span data-ttu-id="14449-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="14449-112">Remarks</span></span>

<span data-ttu-id="14449-113">指定されたメソッドは、`ISOSDacInterface`インターフェイスし、仮想メソッド テーブルの 20 のスロットに対応しています。</span><span class="sxs-lookup"><span data-stu-id="14449-113">The provided method is part of the `ISOSDacInterface` interface and corresponds to the 20th slot of the virtual method table.</span></span> <span data-ttu-id="14449-114">それを使用できる[ `CLRDATA_ADDRESS` ](../common-data-types-unmanaged-api-reference.md) 64 ビット符号なし整数として定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="14449-114">To be able to use them, [`CLRDATA_ADDRESS`](../common-data-types-unmanaged-api-reference.md) must be defined as a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="14449-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="14449-115">Requirements</span></span>

<span data-ttu-id="14449-116">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="14449-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="14449-117">**ヘッダー:** なし</span><span class="sxs-lookup"><span data-stu-id="14449-117">**Header:** None</span></span>  
<span data-ttu-id="14449-118">**ライブラリ:** なし</span><span class="sxs-lookup"><span data-stu-id="14449-118">**Library:** None</span></span>  
<span data-ttu-id="14449-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="14449-119">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="14449-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="14449-120">See also</span></span>

- [<span data-ttu-id="14449-121">デバッグ</span><span class="sxs-lookup"><span data-stu-id="14449-121">Debugging</span></span>](index.md)
- [<span data-ttu-id="14449-122">ISOSDacInterface インターフェイス</span><span class="sxs-lookup"><span data-stu-id="14449-122">ISOSDacInterface Interface</span></span>](isosdacinterface-interface.md)