---
title: 'ISOSDacInterface:: GetModuleData メソッド'
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
ms.openlocfilehash: 14e0eb812c84a0042150345d039451adf178caf1
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396925"
---
# <a name="isosdacinterfacegetmoduledata-method"></a><span data-ttu-id="b20a0-102">ISOSDacInterface:: GetModuleData メソッド</span><span class="sxs-lookup"><span data-stu-id="b20a0-102">ISOSDacInterface::GetModuleData Method</span></span>

<span data-ttu-id="b20a0-103">指定したアドレスに読み込まれたモジュールに対応するデータをフェッチします。</span><span class="sxs-lookup"><span data-stu-id="b20a0-103">Fetches the data corresponding to the module loaded at a given address.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="b20a0-104">構文</span><span class="sxs-lookup"><span data-stu-id="b20a0-104">Syntax</span></span>

```cpp
HRESULT GetModuleData(
    CLRDATA_ADDRESS moduleAddr,
    DacpModuleData *data
);
```

## <a name="parameters"></a><span data-ttu-id="b20a0-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b20a0-105">Parameters</span></span>

`moduleAddr`\
<span data-ttu-id="b20a0-106">から情報を取得するモジュールのアドレス。</span><span class="sxs-lookup"><span data-stu-id="b20a0-106">[in] The address of the module to retrieve information for.</span></span>

`data`\
<span data-ttu-id="b20a0-107">入出力読み込まれたモジュールの情報を保持する[Dacpmoduledata 構造体](dacpmoduledata-structure.md)。</span><span class="sxs-lookup"><span data-stu-id="b20a0-107">[out] The [DacpModuleData structure](dacpmoduledata-structure.md) to hold the information of the loaded module.</span></span>

## <a name="remarks"></a><span data-ttu-id="b20a0-108">解説</span><span class="sxs-lookup"><span data-stu-id="b20a0-108">Remarks</span></span>

<span data-ttu-id="b20a0-109">指定されたメソッドはインターフェイスの一部で `ISOSDacInterface` あり、仮想メソッドテーブルの14番目のスロットに対応します。</span><span class="sxs-lookup"><span data-stu-id="b20a0-109">The provided method is part of the `ISOSDacInterface` interface and corresponds to the 14th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="b20a0-110">要件</span><span class="sxs-lookup"><span data-stu-id="b20a0-110">Requirements</span></span>

<span data-ttu-id="b20a0-111">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b20a0-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="b20a0-112">**ヘッダー:** 存在</span><span class="sxs-lookup"><span data-stu-id="b20a0-112">**Header:** None</span></span>  
<span data-ttu-id="b20a0-113">**ライブラリ:** 存在</span><span class="sxs-lookup"><span data-stu-id="b20a0-113">**Library:** None</span></span>  
<span data-ttu-id="b20a0-114">**.NET Framework のバージョン:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b20a0-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="b20a0-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="b20a0-115">See also</span></span>

- [<span data-ttu-id="b20a0-116">デバッグ</span><span class="sxs-lookup"><span data-stu-id="b20a0-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="b20a0-117">ISOSDacInterface インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b20a0-117">ISOSDacInterface Interface</span></span>](isosdacinterface-interface.md)
