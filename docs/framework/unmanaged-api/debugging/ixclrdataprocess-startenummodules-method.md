---
title: IXCLRDataProcess::StartEnumModules メソッド
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
ms.openlocfilehash: d871ca5dfd62dbca309f4ccc3dcedf959033a41e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57474164"
---
# <a name="ixclrdataprocessstartenummodules-method"></a><span data-ttu-id="faf46-102">IXCLRDataProcess::StartEnumModules メソッド</span><span class="sxs-lookup"><span data-stu-id="faf46-102">IXCLRDataProcess::StartEnumModules Method</span></span>

<span data-ttu-id="faf46-103">プロセスのモジュールを列挙するハンドルを提供します。</span><span class="sxs-lookup"><span data-stu-id="faf46-103">Provides a handle to enumerate the modules of a process.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="faf46-104">構文</span><span class="sxs-lookup"><span data-stu-id="faf46-104">Syntax</span></span>

```
HRESULT StartEnumModules(
    [out] CLRDATA_ENUM *handle
);
```

## <a name="parameters"></a><span data-ttu-id="faf46-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="faf46-105">Parameters</span></span>

`handle`\
<span data-ttu-id="faf46-106">[out]モジュールを列挙するためのハンドル。</span><span class="sxs-lookup"><span data-stu-id="faf46-106">[out] A handle for enumerating the modules.</span></span>

## <a name="remarks"></a><span data-ttu-id="faf46-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="faf46-107">Remarks</span></span>

<span data-ttu-id="faf46-108">指定されたメソッドは、`IXCLRDataProcess`インターフェイスし、24 のスロットの仮想メソッド テーブルに対応しています。</span><span class="sxs-lookup"><span data-stu-id="faf46-108">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 24th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="faf46-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="faf46-109">Requirements</span></span>

<span data-ttu-id="faf46-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="faf46-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="faf46-111">**ヘッダー:** なし</span><span class="sxs-lookup"><span data-stu-id="faf46-111">**Header:** None</span></span>  
<span data-ttu-id="faf46-112">**ライブラリ:** なし</span><span class="sxs-lookup"><span data-stu-id="faf46-112">**Library:** None</span></span>  
<span data-ttu-id="faf46-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="faf46-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="faf46-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="faf46-114">See also</span></span>

- [<span data-ttu-id="faf46-115">CLRDataSourceType 列挙型</span><span class="sxs-lookup"><span data-stu-id="faf46-115">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="faf46-116">デバッグ</span><span class="sxs-lookup"><span data-stu-id="faf46-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="faf46-117">IXCLRDataProcess インターフェイス</span><span class="sxs-lookup"><span data-stu-id="faf46-117">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
