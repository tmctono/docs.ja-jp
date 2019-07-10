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
ms.openlocfilehash: 40ab90a3218d4309cda709004a191e9440fe505d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67769576"
---
# <a name="ixclrdataprocessenummodule-method"></a><span data-ttu-id="675a3-102">IXCLRDataProcess::EnumModule メソッド</span><span class="sxs-lookup"><span data-stu-id="675a3-102">IXCLRDataProcess::EnumModule Method</span></span>

<span data-ttu-id="675a3-103">このプロセスのモジュールを列挙します。</span><span class="sxs-lookup"><span data-stu-id="675a3-103">Enumerates the modules of this process.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="675a3-104">構文</span><span class="sxs-lookup"><span data-stu-id="675a3-104">Syntax</span></span>

```cpp
HRESULT EnumModule(
    [in, out] CLRDATA_ENUM  *handle,
    [out] IXCLRDataModule  **mod
);
```

## <a name="parameters"></a><span data-ttu-id="675a3-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="675a3-105">Parameters</span></span>

`handle`\
<span data-ttu-id="675a3-106">[入力、出力]モジュールを列挙するためのハンドル。</span><span class="sxs-lookup"><span data-stu-id="675a3-106">[in, out] A handle for enumerating the modules.</span></span>

`mod`\
<span data-ttu-id="675a3-107">[out]列挙されたモジュール。</span><span class="sxs-lookup"><span data-stu-id="675a3-107">[out] The enumerated module.</span></span>

## <a name="remarks"></a><span data-ttu-id="675a3-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="675a3-108">Remarks</span></span>

<span data-ttu-id="675a3-109">指定されたメソッドは、`IXCLRDataProcess`インターフェイスし、仮想メソッド テーブルの 25 のスロットに対応しています。</span><span class="sxs-lookup"><span data-stu-id="675a3-109">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 25th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="675a3-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="675a3-110">Requirements</span></span>

<span data-ttu-id="675a3-111">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="675a3-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="675a3-112">**ヘッダー:** なし</span><span class="sxs-lookup"><span data-stu-id="675a3-112">**Header:** None</span></span>  
<span data-ttu-id="675a3-113">**ライブラリ:** なし</span><span class="sxs-lookup"><span data-stu-id="675a3-113">**Library:** None</span></span>  
<span data-ttu-id="675a3-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="675a3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="675a3-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="675a3-115">See also</span></span>

- [<span data-ttu-id="675a3-116">CLRDataSourceType 列挙型</span><span class="sxs-lookup"><span data-stu-id="675a3-116">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="675a3-117">デバッグ</span><span class="sxs-lookup"><span data-stu-id="675a3-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="675a3-118">IXCLRDataModule インターフェイス</span><span class="sxs-lookup"><span data-stu-id="675a3-118">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)
- [<span data-ttu-id="675a3-119">IXCLRDataProcess インターフェイス</span><span class="sxs-lookup"><span data-stu-id="675a3-119">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
