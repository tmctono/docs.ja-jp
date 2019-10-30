---
title: ICorDebugCode::GetVersionNumber メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetVersionNumber
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetVersionNumber
helpviewer_keywords:
- GetVersionNumber method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetVersionNumber method [.NET Framework debugging]
ms.assetid: c8e02518-679f-4e9f-8a28-ba4a89a3876f
topic_type:
- apiref
ms.openlocfilehash: 646c20ca1b78ff0ce513b8a3c9b578c3b1b9a696
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125598"
---
# <a name="icordebugcodegetversionnumber-method"></a><span data-ttu-id="a56c2-102">ICorDebugCode::GetVersionNumber メソッド</span><span class="sxs-lookup"><span data-stu-id="a56c2-102">ICorDebugCode::GetVersionNumber Method</span></span>

<span data-ttu-id="a56c2-103">この "" コード "が表すコードのバージョンを識別する、1から始まる番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="a56c2-103">Gets the one-based number that identifies the version of the code that this "ICorDebugCode" represents.</span></span>

## <a name="syntax"></a><span data-ttu-id="a56c2-104">構文</span><span class="sxs-lookup"><span data-stu-id="a56c2-104">Syntax</span></span>

```cpp
HRESULT GetVersionNumber (
    [out] ULONG32    *nVersion
);
```

## <a name="parameters"></a><span data-ttu-id="a56c2-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a56c2-105">Parameters</span></span>

 `nVersion`  
 <span data-ttu-id="a56c2-106">入出力コードのバージョン番号へのポインター。</span><span class="sxs-lookup"><span data-stu-id="a56c2-106">[out] A pointer to the version number of the code.</span></span>

## <a name="remarks"></a><span data-ttu-id="a56c2-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="a56c2-107">Remarks</span></span>

 <span data-ttu-id="a56c2-108">バージョン番号は、エディットコンティニュ (EnC) 操作がコードで実行されるたびにインクリメントされます。</span><span class="sxs-lookup"><span data-stu-id="a56c2-108">The version number is incremented each time an edit-and-continue (EnC) operation is performed on the code.</span></span>

## <a name="requirements"></a><span data-ttu-id="a56c2-109">［要件］</span><span class="sxs-lookup"><span data-stu-id="a56c2-109">Requirements</span></span>

 <span data-ttu-id="a56c2-110">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a56c2-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a56c2-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a56c2-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a56c2-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a56c2-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a56c2-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a56c2-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
