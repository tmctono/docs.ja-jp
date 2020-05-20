---
title: 'IXCLRDataProcess:: EndEnumModules メソッド'
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::EndEnumModules Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::EndEnumModules Method
helpviewer.keywords:
- IXCLRDataProcess::EndEnumModules Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 9a7a23e53f5c2bc7d643046830cf335fec780f11
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420839"
---
# <a name="ixclrdataprocessendenummodules-method"></a><span data-ttu-id="10af7-102">IXCLRDataProcess:: EndEnumModules メソッド</span><span class="sxs-lookup"><span data-stu-id="10af7-102">IXCLRDataProcess::EndEnumModules Method</span></span>

<span data-ttu-id="10af7-103">モジュールの列挙中に使用される内部反復子によって使用されるリソースを解放します。</span><span class="sxs-lookup"><span data-stu-id="10af7-103">Releases the resources used by internal iterators used during module enumeration.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="10af7-104">構文</span><span class="sxs-lookup"><span data-stu-id="10af7-104">Syntax</span></span>

```cpp
HRESULT EndEnumModules(
    [in] CLRDATA_ENUM handle
);
```

## <a name="parameters"></a><span data-ttu-id="10af7-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="10af7-105">Parameters</span></span>

`handle`\
<span data-ttu-id="10af7-106">入出力モジュールを列挙するハンドル。</span><span class="sxs-lookup"><span data-stu-id="10af7-106">[out] A handle for enumerating the modules.</span></span>

## <a name="remarks"></a><span data-ttu-id="10af7-107">解説</span><span class="sxs-lookup"><span data-stu-id="10af7-107">Remarks</span></span>

<span data-ttu-id="10af7-108">指定されたメソッドはインターフェイスの一部で `IXCLRDataProcess` あり、仮想メソッドテーブルの26日スロットに対応します。</span><span class="sxs-lookup"><span data-stu-id="10af7-108">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 26th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="10af7-109">要件</span><span class="sxs-lookup"><span data-stu-id="10af7-109">Requirements</span></span>

<span data-ttu-id="10af7-110">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10af7-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>
<span data-ttu-id="10af7-111">**ヘッダー:** None **Library:** None **.NET Framework バージョン:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="10af7-111">**Header:** None **Library:** None **.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="10af7-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="10af7-112">See also</span></span>

- [<span data-ttu-id="10af7-113">デバッグ</span><span class="sxs-lookup"><span data-stu-id="10af7-113">Debugging</span></span>](index.md)
- [<span data-ttu-id="10af7-114">IXCLRDataProcess インターフェイス</span><span class="sxs-lookup"><span data-stu-id="10af7-114">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
