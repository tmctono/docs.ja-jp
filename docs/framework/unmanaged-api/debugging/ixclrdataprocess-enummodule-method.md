---
title: IXCLRDataProcess::EnumModule メソッド
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
ms.openlocfilehash: a0398d18f9568754231082d63b4c6a2c865d8c6f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775272"
---
# <a name="ixclrdataprocessenummodule-method"></a><span data-ttu-id="9da9b-102">IXCLRDataProcess::EnumModule メソッド</span><span class="sxs-lookup"><span data-stu-id="9da9b-102">IXCLRDataProcess::EnumModule Method</span></span>

<span data-ttu-id="9da9b-103">このプロセスのモジュールを列挙します。</span><span class="sxs-lookup"><span data-stu-id="9da9b-103">Enumerates the modules of this process.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="9da9b-104">構文</span><span class="sxs-lookup"><span data-stu-id="9da9b-104">Syntax</span></span>

```
HRESULT EnumModule(
    [in, out] CLRDATA_ENUM  *handle,
    [out] IXCLRDataModule  **mod
);
```

## <a name="parameters"></a><span data-ttu-id="9da9b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9da9b-105">Parameters</span></span>

`handle`\
<span data-ttu-id="9da9b-106">[入力、出力]モジュールを列挙するためのハンドル。</span><span class="sxs-lookup"><span data-stu-id="9da9b-106">[in, out] A handle for enumerating the modules.</span></span>

`mod`\
<span data-ttu-id="9da9b-107">[out]列挙されたモジュール。</span><span class="sxs-lookup"><span data-stu-id="9da9b-107">[out] The enumerated module.</span></span>

## <a name="remarks"></a><span data-ttu-id="9da9b-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="9da9b-108">Remarks</span></span>

<span data-ttu-id="9da9b-109">指定されたメソッドは、`IXCLRDataProcess`インターフェイスし、仮想メソッド テーブルの 25 のスロットに対応しています。</span><span class="sxs-lookup"><span data-stu-id="9da9b-109">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 25th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="9da9b-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="9da9b-110">Requirements</span></span>

<span data-ttu-id="9da9b-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9da9b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="9da9b-112">**ヘッダー:** なし</span><span class="sxs-lookup"><span data-stu-id="9da9b-112">**Header:** None</span></span>  
<span data-ttu-id="9da9b-113">**ライブラリ:** なし</span><span class="sxs-lookup"><span data-stu-id="9da9b-113">**Library:** None</span></span>  
<span data-ttu-id="9da9b-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="9da9b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="9da9b-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="9da9b-115">See also</span></span>

- [<span data-ttu-id="9da9b-116">CLRDataSourceType 列挙型</span><span class="sxs-lookup"><span data-stu-id="9da9b-116">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="9da9b-117">デバッグ</span><span class="sxs-lookup"><span data-stu-id="9da9b-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="9da9b-118">IXCLRDataModule インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9da9b-118">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)
- [<span data-ttu-id="9da9b-119">IXCLRDataProcess インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9da9b-119">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
