---
title: ISOSDacInterface::GetModuleData メソッド
ms.date: 02/01/2019
api.name:
- ISOSDacInterface::GetModuleData Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- ISOSDacInterface::GetModuleData Method
helpviewer.keywords:
- ISOSDacInterface::GetModuleData Method [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: 97b297def9fba329ff6d9573f7b2e7cc811273f8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67764722"
---
# <a name="isosdacinterfacegetmoduledata-method"></a><span data-ttu-id="ad21d-102">ISOSDacInterface::GetModuleData メソッド</span><span class="sxs-lookup"><span data-stu-id="ad21d-102">ISOSDacInterface::GetModuleData Method</span></span>

<span data-ttu-id="ad21d-103">指定したアドレスに読み込まれたモジュールに対応するデータをフェッチします。</span><span class="sxs-lookup"><span data-stu-id="ad21d-103">Fetches the data corresponding to the module loaded at a given address.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="ad21d-104">構文</span><span class="sxs-lookup"><span data-stu-id="ad21d-104">Syntax</span></span>

```cpp
HRESULT GetModuleData(
    CLRDATA_ADDRESS moduleAddr,
    DacpModuleData *data
);
```

## <a name="parameters"></a><span data-ttu-id="ad21d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ad21d-105">Parameters</span></span>

`moduleAddr`\
<span data-ttu-id="ad21d-106">[in]情報を取得するモジュールのアドレス。</span><span class="sxs-lookup"><span data-stu-id="ad21d-106">[in] The address of the module to retrieve information for.</span></span>

`data`\
<span data-ttu-id="ad21d-107">[out][DacpModuleData 構造](dacpmoduledata-structure.md)読み込まれたモジュールの情報を保持します。</span><span class="sxs-lookup"><span data-stu-id="ad21d-107">[out] The [DacpModuleData structure](dacpmoduledata-structure.md) to hold the information of the loaded module.</span></span>

## <a name="remarks"></a><span data-ttu-id="ad21d-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="ad21d-108">Remarks</span></span>

<span data-ttu-id="ad21d-109">指定されたメソッドは、`ISOSDacInterface`インターフェイスし、仮想メソッド テーブルの 13 のスロットに対応しています。</span><span class="sxs-lookup"><span data-stu-id="ad21d-109">The provided method is part of the `ISOSDacInterface` interface and corresponds to the 13th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="ad21d-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="ad21d-110">Requirements</span></span>

<span data-ttu-id="ad21d-111">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ad21d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="ad21d-112">**ヘッダー:** なし</span><span class="sxs-lookup"><span data-stu-id="ad21d-112">**Header:** None</span></span>  
<span data-ttu-id="ad21d-113">**ライブラリ:** なし</span><span class="sxs-lookup"><span data-stu-id="ad21d-113">**Library:** None</span></span>  
<span data-ttu-id="ad21d-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ad21d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="ad21d-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="ad21d-115">See also</span></span>

- [<span data-ttu-id="ad21d-116">デバッグ</span><span class="sxs-lookup"><span data-stu-id="ad21d-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="ad21d-117">ISOSDacInterface インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ad21d-117">ISOSDacInterface Interface</span></span>](isosdacinterface-interface.md)
