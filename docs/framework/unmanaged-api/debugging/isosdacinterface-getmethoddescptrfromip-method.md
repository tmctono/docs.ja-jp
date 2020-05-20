---
title: 'ISOSDacInterface:: GetMethodDescPtrFromIP メソッド'
ms.date: 02/01/2019
api.name:
- ISOSDacInterface::GetMethodDescPtrFromIP Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- ISOSDacInterface::GetMethodDescPtrFromIP Method
helpviewer.keywords:
- ISOSDacInterface::GetMethodDescPtrFromIP Method [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: c3de9e5ffe23a13c126343c6f74f042bf1239609
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421008"
---
# <a name="isosdacinterfacegetmethoddescptrfromip-method"></a><span data-ttu-id="2d1a6-102">ISOSDacInterface:: GetMethodDescPtrFromIP メソッド</span><span class="sxs-lookup"><span data-stu-id="2d1a6-102">ISOSDacInterface::GetMethodDescPtrFromIP Method</span></span>

<span data-ttu-id="2d1a6-103">指定されたネイティブ命令アドレスを格納しているメソッドに対応する MethodDesc のポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="2d1a6-103">Retrieves the pointer of the MethodDesc corresponding the method containing the given native instruction address.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="2d1a6-104">構文</span><span class="sxs-lookup"><span data-stu-id="2d1a6-104">Syntax</span></span>

```cpp
HRESULT GetMethodDescPtrFromIP(
    CLRDATA_ADDRESS ip,
    CLRDATA_ADDRESS * ppMD
);
```

## <a name="parameters"></a><span data-ttu-id="2d1a6-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2d1a6-105">Parameters</span></span>

`ip`\
<span data-ttu-id="2d1a6-106">から実行時のメソッド内のアドレス。</span><span class="sxs-lookup"><span data-stu-id="2d1a6-106">[in] An address within the method at runtime.</span></span>

`ppMD`\
<span data-ttu-id="2d1a6-107">入出力`MethodDesc`特定のメソッドののアドレス。</span><span class="sxs-lookup"><span data-stu-id="2d1a6-107">[out] The address of the `MethodDesc` for the particular method.</span></span>

## <a name="remarks"></a><span data-ttu-id="2d1a6-108">解説</span><span class="sxs-lookup"><span data-stu-id="2d1a6-108">Remarks</span></span>

<span data-ttu-id="2d1a6-109">指定されたメソッドは[ `ISOSDacInterface` インターフェイス](isosdacinterface-interface.md)の一部であり、仮想メソッドテーブルの22スロットに対応します。</span><span class="sxs-lookup"><span data-stu-id="2d1a6-109">The provided method is part of the [`ISOSDacInterface` interface](isosdacinterface-interface.md) and corresponds to the 22nd slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="2d1a6-110">要件</span><span class="sxs-lookup"><span data-stu-id="2d1a6-110">Requirements</span></span>

<span data-ttu-id="2d1a6-111">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d1a6-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="2d1a6-112">**ヘッダー:** 存在</span><span class="sxs-lookup"><span data-stu-id="2d1a6-112">**Header:** None</span></span>  
<span data-ttu-id="2d1a6-113">**ライブラリ:** 存在</span><span class="sxs-lookup"><span data-stu-id="2d1a6-113">**Library:** None</span></span>  
<span data-ttu-id="2d1a6-114">**.NET Framework のバージョン:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="2d1a6-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="2d1a6-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="2d1a6-115">See also</span></span>

- [<span data-ttu-id="2d1a6-116">デバッグ</span><span class="sxs-lookup"><span data-stu-id="2d1a6-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="2d1a6-117">ISOSDacInterface インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2d1a6-117">ISOSDacInterface Interface</span></span>](isosdacinterface-interface.md)
