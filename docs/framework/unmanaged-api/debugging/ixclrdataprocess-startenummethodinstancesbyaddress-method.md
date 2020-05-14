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
ms.openlocfilehash: e28fa73300e147ac07a2d325fbf517480bb73797
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "83394947"
---
# <a name="ixclrdataprocessstartenummethodinstancesbyaddress-method"></a><span data-ttu-id="0a882-102">IXCLRDataProcess:: StartEnumMethodInstancesByAddress メソッド</span><span class="sxs-lookup"><span data-stu-id="0a882-102">IXCLRDataProcess::StartEnumMethodInstancesByAddress Method</span></span>

<span data-ttu-id="0a882-103">指定されたアドレスから開始するのメソッドインスタンスを列挙するハンドルを提供し `AppDomain` ます。</span><span class="sxs-lookup"><span data-stu-id="0a882-103">Provides a handle to enumerate the method instances of `AppDomain` starting at a given address.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="0a882-104">構文</span><span class="sxs-lookup"><span data-stu-id="0a882-104">Syntax</span></span>

```cpp
HRESULT StartEnumMethodInstancesByAddress(
    [in] CLRDATA_ADDRESS     address,
    [in] IXCLRDataAppDomain *appDomain,
    [out] CLRDATA_ENUM      *handle
);
```

## <a name="parameters"></a><span data-ttu-id="0a882-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0a882-105">Parameters</span></span>

`address`\
<span data-ttu-id="0a882-106">から最初のメソッドインスタンスのアドレス。</span><span class="sxs-lookup"><span data-stu-id="0a882-106">[in] The address of the first method instance.</span></span>

`appDomain`\
<span data-ttu-id="0a882-107">からメソッドインスタンスの AppDomain。</span><span class="sxs-lookup"><span data-stu-id="0a882-107">[in] The AppDomain of the method instances.</span></span>

`handle`\
<span data-ttu-id="0a882-108">入出力メソッドインスタンスを列挙するハンドル。</span><span class="sxs-lookup"><span data-stu-id="0a882-108">[out] A handle for enumerating the method instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="0a882-109">解説</span><span class="sxs-lookup"><span data-stu-id="0a882-109">Remarks</span></span>

<span data-ttu-id="0a882-110">指定されたメソッドはインターフェイスの一部で `IXCLRDataProcess` あり、仮想メソッドテーブルの28番目のスロットに対応します。</span><span class="sxs-lookup"><span data-stu-id="0a882-110">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 28th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="0a882-111">要件</span><span class="sxs-lookup"><span data-stu-id="0a882-111">Requirements</span></span>

<span data-ttu-id="0a882-112">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0a882-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="0a882-113">**ヘッダー:** 存在</span><span class="sxs-lookup"><span data-stu-id="0a882-113">**Header:** None</span></span>  
<span data-ttu-id="0a882-114">**ライブラリ:** 存在</span><span class="sxs-lookup"><span data-stu-id="0a882-114">**Library:** None</span></span>  
<span data-ttu-id="0a882-115">**.NET Framework のバージョン:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="0a882-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="0a882-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="0a882-116">See also</span></span>

- [<span data-ttu-id="0a882-117">CLRDataSourceType 列挙型</span><span class="sxs-lookup"><span data-stu-id="0a882-117">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="0a882-118">デバッグ</span><span class="sxs-lookup"><span data-stu-id="0a882-118">Debugging</span></span>](index.md)
- [<span data-ttu-id="0a882-119">IXCLRDataProcess インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0a882-119">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
