---
title: Initialize 関数 (アンマネージ API リファレンス)
description: 初期化関数は、WMI の初期化を実行します。
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7c71b2b6d6f102d19d30d480ee9bafcac3c204be
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2019
ms.locfileid: "59611082"
---
# <a name="initialize-function"></a><span data-ttu-id="f6142-103">Initialize 関数</span><span class="sxs-lookup"><span data-stu-id="f6142-103">Initialize function</span></span>

<span data-ttu-id="f6142-104">WMI の初期化が実行されます。</span><span class="sxs-lookup"><span data-stu-id="f6142-104">Performs WMI initialization.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="f6142-105">構文</span><span class="sxs-lookup"><span data-stu-id="f6142-105">Syntax</span></span>

```cpp
HRESULT Initialize(
   [in] boolean bAllowIManagementObjectQI
);
```

## <a name="parameters"></a><span data-ttu-id="f6142-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f6142-106">Parameters</span></span>

`bAllowIManagementObjectQI`

<span data-ttu-id="f6142-107">[in]`true` WMI オブジェクトの queryinterface 呼び出しが許可されることを示す`false`それ以外の場合。</span><span class="sxs-lookup"><span data-stu-id="f6142-107">[in] `true` to indicate that calls to QueryInterface on WMI objects are allowed; `false` otherwise.</span></span>

## <a name="return-value"></a><span data-ttu-id="f6142-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="f6142-108">Return value</span></span>

<span data-ttu-id="f6142-109">関数は常に返します`S_OK`(0)。</span><span class="sxs-lookup"><span data-stu-id="f6142-109">The function always returns `S_OK` (0).</span></span>

## <a name="requirements"></a><span data-ttu-id="f6142-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="f6142-110">Requirements</span></span>

<span data-ttu-id="f6142-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6142-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="f6142-112">**ヘッダー:** WMINet_Utils.def</span><span class="sxs-lookup"><span data-stu-id="f6142-112">**Header:** WMINet_Utils.def</span></span>

<span data-ttu-id="f6142-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="f6142-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="f6142-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="f6142-114">See also</span></span>

- [<span data-ttu-id="f6142-115">WMI およびパフォーマンス カウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="f6142-115">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
