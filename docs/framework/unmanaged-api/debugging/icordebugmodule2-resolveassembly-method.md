---
title: ICorDebugModule2::ResolveAssembly メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugModule2.ResolveAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2::ResolveAssembly
helpviewer_keywords:
- ICorDebugModule2::ResolveAssembly method [.NET Framework debugging]
- ResolveAssembly method [.NET Framework debugging]
ms.assetid: ddf9085c-7161-44bd-9609-cd2732b9009f
topic_type:
- apiref
ms.openlocfilehash: 0809a149a5a5a5e9adea059140d7b4b456337ef3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125307"
---
# <a name="icordebugmodule2resolveassembly-method"></a><span data-ttu-id="5cf75-102">ICorDebugModule2::ResolveAssembly メソッド</span><span class="sxs-lookup"><span data-stu-id="5cf75-102">ICorDebugModule2::ResolveAssembly Method</span></span>

<span data-ttu-id="5cf75-103">指定したメタデータトークンによって参照されるアセンブリを解決します。</span><span class="sxs-lookup"><span data-stu-id="5cf75-103">Resolves the assembly referenced by the specified metadata token.</span></span>

## <a name="syntax"></a><span data-ttu-id="5cf75-104">構文</span><span class="sxs-lookup"><span data-stu-id="5cf75-104">Syntax</span></span>

```cpp
HRESULT ResolveAssembly (
    [in]  mdToken             tkAssemblyRef,
    [out] ICorDebugAssembly   **ppAssembly
);
```

## <a name="parameters"></a><span data-ttu-id="5cf75-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5cf75-105">Parameters</span></span>

`tkAssemblyRef`\
<span data-ttu-id="5cf75-106">からアセンブリを参照する `mdToken` 値。</span><span class="sxs-lookup"><span data-stu-id="5cf75-106">[in] An `mdToken` value that references the assembly.</span></span>

`ppAssembly`\
<span data-ttu-id="5cf75-107">入出力アセンブリを表す、オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="5cf75-107">[out] A pointer to the address of an ICorDebugAssembly object that represents the assembly.</span></span>

## <a name="remarks"></a><span data-ttu-id="5cf75-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="5cf75-108">Remarks</span></span>

<span data-ttu-id="5cf75-109">`ResolveAssembly` が呼び出されたときにアセンブリがまだ読み込まれていない場合は、HRESULT 値 CORDBG_E_CANNOT_RESOLVE_ASSEMBLY が返されます。</span><span class="sxs-lookup"><span data-stu-id="5cf75-109">If the assembly is not already loaded when `ResolveAssembly` is called, an HRESULT value of CORDBG_E_CANNOT_RESOLVE_ASSEMBLY is returned.</span></span>

## <a name="requirements"></a><span data-ttu-id="5cf75-110">［要件］</span><span class="sxs-lookup"><span data-stu-id="5cf75-110">Requirements</span></span>

<span data-ttu-id="5cf75-111">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5cf75-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="5cf75-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5cf75-112">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="5cf75-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5cf75-113">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="5cf75-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5cf75-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
