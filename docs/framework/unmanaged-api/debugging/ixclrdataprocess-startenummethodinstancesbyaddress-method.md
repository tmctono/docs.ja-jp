---
title: 'IXCLRDataProcess:: StartEnumMethodInstancesByAddress メソッド'
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::StartEnumMethodInstancesByAddress Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::StartEnumMethodInstancesByAddress Method
helpviewer.keywords:
- IXCLRDataProcess::StartEnumMethodInstancesByAddress Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 52d533f1c86b34b7b9febade8590e7ab58d8221e
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420735"
---
# <a name="ixclrdataprocessstartenummethodinstancesbyaddress-method"></a><span data-ttu-id="230c2-102">IXCLRDataProcess:: StartEnumMethodInstancesByAddress メソッド</span><span class="sxs-lookup"><span data-stu-id="230c2-102">IXCLRDataProcess::StartEnumMethodInstancesByAddress Method</span></span>

<span data-ttu-id="230c2-103">指定されたアドレスから開始するのメソッドインスタンスを列挙するハンドルを提供し `AppDomain` ます。</span><span class="sxs-lookup"><span data-stu-id="230c2-103">Provides a handle to enumerate the method instances of `AppDomain` starting at a given address.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="230c2-104">構文</span><span class="sxs-lookup"><span data-stu-id="230c2-104">Syntax</span></span>

```cpp
HRESULT StartEnumMethodInstancesByAddress(
    [in] CLRDATA_ADDRESS     address,
    [in] IXCLRDataAppDomain *appDomain,
    [out] CLRDATA_ENUM      *handle
);
```

## <a name="parameters"></a><span data-ttu-id="230c2-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="230c2-105">Parameters</span></span>

`address`\
<span data-ttu-id="230c2-106">から最初のメソッドインスタンスのアドレス。</span><span class="sxs-lookup"><span data-stu-id="230c2-106">[in] The address of the first method instance.</span></span>

`appDomain`\
<span data-ttu-id="230c2-107">からメソッドインスタンスの AppDomain。</span><span class="sxs-lookup"><span data-stu-id="230c2-107">[in] The AppDomain of the method instances.</span></span>

`handle`\
<span data-ttu-id="230c2-108">入出力メソッドインスタンスを列挙するハンドル。</span><span class="sxs-lookup"><span data-stu-id="230c2-108">[out] A handle for enumerating the method instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="230c2-109">解説</span><span class="sxs-lookup"><span data-stu-id="230c2-109">Remarks</span></span>

<span data-ttu-id="230c2-110">指定されたメソッドはインターフェイスの一部で `IXCLRDataProcess` あり、仮想メソッドテーブルの28番目のスロットに対応します。</span><span class="sxs-lookup"><span data-stu-id="230c2-110">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 28th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="230c2-111">要件</span><span class="sxs-lookup"><span data-stu-id="230c2-111">Requirements</span></span>

<span data-ttu-id="230c2-112">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="230c2-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="230c2-113">**ヘッダー:** 存在</span><span class="sxs-lookup"><span data-stu-id="230c2-113">**Header:** None</span></span>  
<span data-ttu-id="230c2-114">**ライブラリ:** 存在</span><span class="sxs-lookup"><span data-stu-id="230c2-114">**Library:** None</span></span>  
<span data-ttu-id="230c2-115">**.NET Framework のバージョン:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="230c2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="230c2-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="230c2-116">See also</span></span>

- [<span data-ttu-id="230c2-117">CLRDataSourceType 列挙型</span><span class="sxs-lookup"><span data-stu-id="230c2-117">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="230c2-118">デバッグ</span><span class="sxs-lookup"><span data-stu-id="230c2-118">Debugging</span></span>](index.md)
- [<span data-ttu-id="230c2-119">IXCLRDataProcess インターフェイス</span><span class="sxs-lookup"><span data-stu-id="230c2-119">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
