---
title: ICorDebugCode::IsIL メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugCode.IsIL
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::IsIL
helpviewer_keywords:
- ICorDebugCode::IsIL method [.NET Framework debugging]
- IsIL method [.NET Framework debugging]
ms.assetid: 132ef8cc-d938-43f3-b8f2-e3b97c0ceb33
topic_type:
- apiref
ms.openlocfilehash: 77e55c4c3644ac4bd76f5c92152f4ee86cf5fa9a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125565"
---
# <a name="icordebugcodeisil-method"></a><span data-ttu-id="0f2f7-102">ICorDebugCode::IsIL メソッド</span><span class="sxs-lookup"><span data-stu-id="0f2f7-102">ICorDebugCode::IsIL Method</span></span>

<span data-ttu-id="0f2f7-103">この "コードが、Microsoft 中間言語 (MSIL) でコンパイルされたコードを表しているかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="0f2f7-103">Gets a value that indicates whether this "ICorDebugCode" represents code that was compiled in Microsoft intermediate language (MSIL).</span></span>

## <a name="syntax"></a><span data-ttu-id="0f2f7-104">構文</span><span class="sxs-lookup"><span data-stu-id="0f2f7-104">Syntax</span></span>

```cpp
HRESULT IsIL (
    [out] BOOL       *pbIL
);
```

## <a name="parameters"></a><span data-ttu-id="0f2f7-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0f2f7-105">Parameters</span></span>

`pbIL`  
<span data-ttu-id="0f2f7-106">[out] この `ICorDebugCode` が MSIL でコンパイルされたコードを表している場合は `true`。それ以外の場合は、`false`ます。</span><span class="sxs-lookup"><span data-stu-id="0f2f7-106">[out] `true` if this `ICorDebugCode` represents code that was compiled in MSIL; otherwise, `false`.</span></span>

## <a name="requirements"></a><span data-ttu-id="0f2f7-107">［要件］</span><span class="sxs-lookup"><span data-stu-id="0f2f7-107">Requirements</span></span>

<span data-ttu-id="0f2f7-108">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f2f7-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="0f2f7-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0f2f7-109">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="0f2f7-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0f2f7-110">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="0f2f7-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f2f7-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
