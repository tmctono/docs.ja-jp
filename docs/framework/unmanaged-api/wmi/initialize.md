---
title: Initialize 関数 (アンマネージ API リファレンス)
description: Initialize 関数は、WMI の初期化を実行します。
ms.date: 11/06/2017
api_name:
- Initialize
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Initialize
helpviewer_keywords:
- Initialize function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: b1f96b6285911b12d72ac136127d736b75d44023
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127392"
---
# <a name="initialize-function"></a><span data-ttu-id="8863c-103">Initialize 関数</span><span class="sxs-lookup"><span data-stu-id="8863c-103">Initialize function</span></span>

<span data-ttu-id="8863c-104">WMI の初期化が実行されます。</span><span class="sxs-lookup"><span data-stu-id="8863c-104">Performs WMI initialization.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="8863c-105">構文</span><span class="sxs-lookup"><span data-stu-id="8863c-105">Syntax</span></span>

```cpp
HRESULT Initialize(
   [in] boolean bAllowIManagementObjectQI
);
```

## <a name="parameters"></a><span data-ttu-id="8863c-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8863c-106">Parameters</span></span>

`bAllowIManagementObjectQI`

<span data-ttu-id="8863c-107">[in] WMI オブジェクトの QueryInterface の呼び出しが許可されていることを示す `true` ます。それ以外の場合は `false`。</span><span class="sxs-lookup"><span data-stu-id="8863c-107">[in] `true` to indicate that calls to QueryInterface on WMI objects are allowed; `false` otherwise.</span></span>

## <a name="return-value"></a><span data-ttu-id="8863c-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="8863c-108">Return value</span></span>

<span data-ttu-id="8863c-109">関数は常に `S_OK` (0) を返します。</span><span class="sxs-lookup"><span data-stu-id="8863c-109">The function always returns `S_OK` (0).</span></span>

## <a name="requirements"></a><span data-ttu-id="8863c-110">［要件］</span><span class="sxs-lookup"><span data-stu-id="8863c-110">Requirements</span></span>

<span data-ttu-id="8863c-111">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8863c-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="8863c-112">**ヘッダー:** WMINet_Utils</span><span class="sxs-lookup"><span data-stu-id="8863c-112">**Header:** WMINet_Utils.def</span></span>

<span data-ttu-id="8863c-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="8863c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="8863c-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="8863c-114">See also</span></span>

- [<span data-ttu-id="8863c-115">WMI およびパフォーマンスカウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="8863c-115">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
