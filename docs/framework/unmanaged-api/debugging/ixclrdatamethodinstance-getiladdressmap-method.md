---
title: 'IXCLRDataMethodInstance:: GetILAddressMap メソッド'
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodInstance::GetILAddressMap Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodInstance::GetILAddressMap Method
helpviewer.keywords:
- IXCLRDataMethodInstance::GetILAddressMap Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 7c4dcf59ce159434d5012120043f5bb548d49731
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396813"
---
# <a name="ixclrdatamethodinstancegetiladdressmap-method"></a><span data-ttu-id="87bca-102">IXCLRDataMethodInstance:: GetILAddressMap メソッド</span><span class="sxs-lookup"><span data-stu-id="87bca-102">IXCLRDataMethodInstance::GetILAddressMap Method</span></span>

<span data-ttu-id="87bca-103">マッピング情報をアドレス付けする IL を取得します。</span><span class="sxs-lookup"><span data-stu-id="87bca-103">Gets the IL to address mapping information.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="87bca-104">構文</span><span class="sxs-lookup"><span data-stu-id="87bca-104">Syntax</span></span>

```cpp
HRESULT GetILAddressMap(
    [in] ULONG32                                   mapLen,
    [out] ULONG32                                 *mapNeeded,
    [out, size_is(mapLen)] CLRDATA_IL_ADDRESS_MAP  maps[]
);
```

## <a name="parameters"></a><span data-ttu-id="87bca-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="87bca-105">Parameters</span></span>

`mapLen`\
<span data-ttu-id="87bca-106">から指定されたマップ配列の長さ。</span><span class="sxs-lookup"><span data-stu-id="87bca-106">[in] The length of the provided maps array.</span></span>

`mapNeeded`\
<span data-ttu-id="87bca-107">入出力メソッドが必要とするマップエントリの数。</span><span class="sxs-lookup"><span data-stu-id="87bca-107">[out] The number of map entries that the method needs.</span></span>

`maps`\
<span data-ttu-id="87bca-108">[out、size_is (mapLen)]マップエントリを格納するための配列。</span><span class="sxs-lookup"><span data-stu-id="87bca-108">[out, size_is(mapLen)] The array for storing the map entries.</span></span>

## <a name="remarks"></a><span data-ttu-id="87bca-109">解説</span><span class="sxs-lookup"><span data-stu-id="87bca-109">Remarks</span></span>

<span data-ttu-id="87bca-110">指定されたメソッドはインターフェイスの一部で `IXCLRDataMethodInstance` あり、仮想メソッドテーブルの15番目のスロットに対応します。</span><span class="sxs-lookup"><span data-stu-id="87bca-110">The provided method is part of the `IXCLRDataMethodInstance` interface and corresponds to the 15th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="87bca-111">要件</span><span class="sxs-lookup"><span data-stu-id="87bca-111">Requirements</span></span>

<span data-ttu-id="87bca-112">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="87bca-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="87bca-113">**ヘッダー:** 存在</span><span class="sxs-lookup"><span data-stu-id="87bca-113">**Header:** None</span></span>  
<span data-ttu-id="87bca-114">**ライブラリ:** 存在</span><span class="sxs-lookup"><span data-stu-id="87bca-114">**Library:** None</span></span>  
<span data-ttu-id="87bca-115">**.NET Framework のバージョン:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="87bca-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="87bca-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="87bca-116">See also</span></span>

- [<span data-ttu-id="87bca-117">デバッグ</span><span class="sxs-lookup"><span data-stu-id="87bca-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="87bca-118">IXCLRDataMethodInstance インターフェイス</span><span class="sxs-lookup"><span data-stu-id="87bca-118">IXCLRDataMethodInstance Interface</span></span>](ixclrdatamethodinstance-interface.md)
