---
title: 'IXCLRDataProcess:: StartEnumModules メソッド'
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::StartEnumModules Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::StartEnumModules Method
helpviewer.keywords:
- IXCLRDataProcess::StartEnumModules Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: d55b07ea3fada73237919bf677163a9096d5ad04
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420722"
---
# <a name="ixclrdataprocessstartenummodules-method"></a><span data-ttu-id="fb3f7-102">IXCLRDataProcess:: StartEnumModules メソッド</span><span class="sxs-lookup"><span data-stu-id="fb3f7-102">IXCLRDataProcess::StartEnumModules Method</span></span>

<span data-ttu-id="fb3f7-103">プロセスのモジュールを列挙するハンドルを提供します。</span><span class="sxs-lookup"><span data-stu-id="fb3f7-103">Provides a handle to enumerate the modules of a process.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="fb3f7-104">構文</span><span class="sxs-lookup"><span data-stu-id="fb3f7-104">Syntax</span></span>

```cpp
HRESULT StartEnumModules(
    [out] CLRDATA_ENUM *handle
);
```

## <a name="parameters"></a><span data-ttu-id="fb3f7-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fb3f7-105">Parameters</span></span>

`handle`\
<span data-ttu-id="fb3f7-106">入出力モジュールを列挙するハンドル。</span><span class="sxs-lookup"><span data-stu-id="fb3f7-106">[out] A handle for enumerating the modules.</span></span>

## <a name="remarks"></a><span data-ttu-id="fb3f7-107">解説</span><span class="sxs-lookup"><span data-stu-id="fb3f7-107">Remarks</span></span>

<span data-ttu-id="fb3f7-108">指定されたメソッドはインターフェイスの一部で `IXCLRDataProcess` あり、仮想メソッドテーブルの24番のスロットに対応します。</span><span class="sxs-lookup"><span data-stu-id="fb3f7-108">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 24th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="fb3f7-109">要件</span><span class="sxs-lookup"><span data-stu-id="fb3f7-109">Requirements</span></span>

<span data-ttu-id="fb3f7-110">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb3f7-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="fb3f7-111">**ヘッダー:** 存在</span><span class="sxs-lookup"><span data-stu-id="fb3f7-111">**Header:** None</span></span>  
<span data-ttu-id="fb3f7-112">**ライブラリ:** 存在</span><span class="sxs-lookup"><span data-stu-id="fb3f7-112">**Library:** None</span></span>  
<span data-ttu-id="fb3f7-113">**.NET Framework のバージョン:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="fb3f7-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="fb3f7-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="fb3f7-114">See also</span></span>

- [<span data-ttu-id="fb3f7-115">CLRDataSourceType 列挙型</span><span class="sxs-lookup"><span data-stu-id="fb3f7-115">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="fb3f7-116">デバッグ</span><span class="sxs-lookup"><span data-stu-id="fb3f7-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="fb3f7-117">IXCLRDataProcess インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fb3f7-117">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
