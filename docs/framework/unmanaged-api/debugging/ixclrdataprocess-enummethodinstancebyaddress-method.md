---
title: 'IXCLRDataProcess:: EnumMethodInstanceByAddress メソッド'
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::EnumMethodInstanceByAddress Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::EnumMethodInstanceByAddress Method
helpviewer.keywords:
- IXCLRDataProcess::EnumMethodInstanceByAddress Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 142099ae5cf9637cc28e8c82aabcd831cc8f0f52
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420800"
---
# <a name="ixclrdataprocessenummethodinstancebyaddress-method"></a><span data-ttu-id="e6255-102">IXCLRDataProcess:: EnumMethodInstanceByAddress メソッド</span><span class="sxs-lookup"><span data-stu-id="e6255-102">IXCLRDataProcess::EnumMethodInstanceByAddress Method</span></span>

<span data-ttu-id="e6255-103">このプロセスのメソッドインスタンスを、アドレスオフセットを開始位置として列挙します。</span><span class="sxs-lookup"><span data-stu-id="e6255-103">Enumerates the method instances of this process starting at an address offset.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="e6255-104">構文</span><span class="sxs-lookup"><span data-stu-id="e6255-104">Syntax</span></span>

```cpp
HRESULT EnumMethodInstanceByAddress(
    [in] CLRDATA_ENUM              *handle,
    [out] IXCLRDataMethodInstance **method
);
```

## <a name="parameters"></a><span data-ttu-id="e6255-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e6255-105">Parameters</span></span>

`handle`\
<span data-ttu-id="e6255-106">からメソッドインスタンスを列挙するハンドル。</span><span class="sxs-lookup"><span data-stu-id="e6255-106">[in] A handle for enumerating the method instances.</span></span>

`mod`\
<span data-ttu-id="e6255-107">入出力列挙されたメソッドインスタンス。</span><span class="sxs-lookup"><span data-stu-id="e6255-107">[out] The enumerated method instance.</span></span>

## <a name="remarks"></a><span data-ttu-id="e6255-108">解説</span><span class="sxs-lookup"><span data-stu-id="e6255-108">Remarks</span></span>

<span data-ttu-id="e6255-109">指定されたメソッドはインターフェイスの一部で `IXCLRDataProcess` あり、仮想メソッドテーブルの29スロットに対応します。</span><span class="sxs-lookup"><span data-stu-id="e6255-109">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 29th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="e6255-110">要件</span><span class="sxs-lookup"><span data-stu-id="e6255-110">Requirements</span></span>

<span data-ttu-id="e6255-111">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e6255-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>
<span data-ttu-id="e6255-112">**ヘッダー:** None **Library:** None **.NET Framework バージョン:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e6255-112">**Header:** None **Library:** None **.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="e6255-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="e6255-113">See also</span></span>

- [<span data-ttu-id="e6255-114">CLRDataSourceType 列挙型</span><span class="sxs-lookup"><span data-stu-id="e6255-114">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="e6255-115">デバッグ</span><span class="sxs-lookup"><span data-stu-id="e6255-115">Debugging</span></span>](index.md)
- [<span data-ttu-id="e6255-116">IXCLRDataProcess インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e6255-116">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
