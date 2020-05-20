---
title: 'IXCLRDataProcess:: EnumModule メソッド'
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::EnumModule Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::EnumModule Method
helpviewer.keywords:
- IXCLRDataProcess::EnumModule Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 5caadcfe091393a8ff79106d57a50a532c349829
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420777"
---
# <a name="ixclrdataprocessenummodule-method"></a><span data-ttu-id="fba72-102">IXCLRDataProcess:: EnumModule メソッド</span><span class="sxs-lookup"><span data-stu-id="fba72-102">IXCLRDataProcess::EnumModule Method</span></span>

<span data-ttu-id="fba72-103">このプロセスのモジュールを列挙します。</span><span class="sxs-lookup"><span data-stu-id="fba72-103">Enumerates the modules of this process.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="fba72-104">構文</span><span class="sxs-lookup"><span data-stu-id="fba72-104">Syntax</span></span>

```cpp
HRESULT EnumModule(
    [in, out] CLRDATA_ENUM  *handle,
    [out] IXCLRDataModule  **mod
);
```

## <a name="parameters"></a><span data-ttu-id="fba72-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fba72-105">Parameters</span></span>

`handle`\
<span data-ttu-id="fba72-106">[入力、出力]モジュールを列挙するハンドル。</span><span class="sxs-lookup"><span data-stu-id="fba72-106">[in, out] A handle for enumerating the modules.</span></span>

`mod`\
<span data-ttu-id="fba72-107">入出力列挙されたモジュール。</span><span class="sxs-lookup"><span data-stu-id="fba72-107">[out] The enumerated module.</span></span>

## <a name="remarks"></a><span data-ttu-id="fba72-108">解説</span><span class="sxs-lookup"><span data-stu-id="fba72-108">Remarks</span></span>

<span data-ttu-id="fba72-109">指定されたメソッドはインターフェイスの一部で `IXCLRDataProcess` あり、仮想メソッドテーブルの25スロットに対応します。</span><span class="sxs-lookup"><span data-stu-id="fba72-109">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 25th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="fba72-110">要件</span><span class="sxs-lookup"><span data-stu-id="fba72-110">Requirements</span></span>

<span data-ttu-id="fba72-111">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fba72-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="fba72-112">**ヘッダー:** 存在</span><span class="sxs-lookup"><span data-stu-id="fba72-112">**Header:** None</span></span>  
<span data-ttu-id="fba72-113">**ライブラリ:** 存在</span><span class="sxs-lookup"><span data-stu-id="fba72-113">**Library:** None</span></span>  
<span data-ttu-id="fba72-114">**.NET Framework のバージョン:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="fba72-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="fba72-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="fba72-115">See also</span></span>

- [<span data-ttu-id="fba72-116">CLRDataSourceType 列挙型</span><span class="sxs-lookup"><span data-stu-id="fba72-116">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="fba72-117">デバッグ</span><span class="sxs-lookup"><span data-stu-id="fba72-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="fba72-118">IXCLRDataModule インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fba72-118">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)
- [<span data-ttu-id="fba72-119">IXCLRDataProcess インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fba72-119">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
