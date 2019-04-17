---
title: IXCLRDataProcess::EndEnumModules メソッド
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
ms.openlocfilehash: de30384b4c12c4fcac3eafe580484685f8a43fa4
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2019
ms.locfileid: "59611433"
---
# <a name="ixclrdataprocessendenummodules-method"></a><span data-ttu-id="4a04e-102">IXCLRDataProcess::EndEnumModules メソッド</span><span class="sxs-lookup"><span data-stu-id="4a04e-102">IXCLRDataProcess::EndEnumModules Method</span></span>

<span data-ttu-id="4a04e-103">モジュールの列挙中に使用される内部の反復子によって使用されるリソースを解放します。</span><span class="sxs-lookup"><span data-stu-id="4a04e-103">Releases the resources used by internal iterators used during module enumeration.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="4a04e-104">構文</span><span class="sxs-lookup"><span data-stu-id="4a04e-104">Syntax</span></span>

```cpp
HRESULT EndEnumModules(
    [in] CLRDATA_ENUM handle
);
```

## <a name="parameters"></a><span data-ttu-id="4a04e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4a04e-105">Parameters</span></span>

`handle`\
<span data-ttu-id="4a04e-106">[out]モジュールを列挙するためのハンドル。</span><span class="sxs-lookup"><span data-stu-id="4a04e-106">[out] A handle for enumerating the modules.</span></span>

## <a name="remarks"></a><span data-ttu-id="4a04e-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="4a04e-107">Remarks</span></span>

<span data-ttu-id="4a04e-108">指定されたメソッドは、`IXCLRDataProcess`インターフェイスし、仮想メソッド テーブルの 26 のスロットに対応しています。</span><span class="sxs-lookup"><span data-stu-id="4a04e-108">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 26th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="4a04e-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="4a04e-109">Requirements</span></span>

<span data-ttu-id="4a04e-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a04e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>
<span data-ttu-id="4a04e-111">**ヘッダー:** None**ライブラリ。** None **.NET Framework のバージョン。** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="4a04e-111">**Header:** None **Library:** None **.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="4a04e-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="4a04e-112">See also</span></span>

- [<span data-ttu-id="4a04e-113">デバッグ</span><span class="sxs-lookup"><span data-stu-id="4a04e-113">Debugging</span></span>](index.md)
- [<span data-ttu-id="4a04e-114">IXCLRDataProcess インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4a04e-114">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
