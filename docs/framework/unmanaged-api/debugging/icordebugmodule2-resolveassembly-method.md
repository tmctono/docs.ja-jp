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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fd899422287d34407778f67e5b4dfd2f33ffd00c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61994826"
---
# <a name="icordebugmodule2resolveassembly-method"></a><span data-ttu-id="f4c65-102">ICorDebugModule2::ResolveAssembly メソッド</span><span class="sxs-lookup"><span data-stu-id="f4c65-102">ICorDebugModule2::ResolveAssembly Method</span></span>

<span data-ttu-id="f4c65-103">指定したメタデータ トークンによって参照されるアセンブリを解決します。</span><span class="sxs-lookup"><span data-stu-id="f4c65-103">Resolves the assembly referenced by the specified metadata token.</span></span>

## <a name="syntax"></a><span data-ttu-id="f4c65-104">構文</span><span class="sxs-lookup"><span data-stu-id="f4c65-104">Syntax</span></span>

```cpp
HRESULT ResolveAssembly (
    [in]  mdToken             tkAssemblyRef,
    [out] ICorDebugAssembly   **ppAssembly
);
```

## <a name="parameters"></a><span data-ttu-id="f4c65-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f4c65-105">Parameters</span></span>

`tkAssemblyRef`\
<span data-ttu-id="f4c65-106">[in]`mdToken`アセンブリを参照する値。</span><span class="sxs-lookup"><span data-stu-id="f4c65-106">[in] An `mdToken` value that references the assembly.</span></span>

`ppAssembly`\
<span data-ttu-id="f4c65-107">[out]アセンブリを表す ICorDebugAssembly オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="f4c65-107">[out] A pointer to the address of an ICorDebugAssembly object that represents the assembly.</span></span>

## <a name="remarks"></a><span data-ttu-id="f4c65-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="f4c65-108">Remarks</span></span>

<span data-ttu-id="f4c65-109">場合は、アセンブリが既に読み込まれていない場合に`ResolveAssembly`が呼び出され、HRESULT CORDBG_E_CANNOT_RESOLVE_ASSEMBLY の値が返されます。</span><span class="sxs-lookup"><span data-stu-id="f4c65-109">If the assembly is not already loaded when `ResolveAssembly` is called, an HRESULT value of CORDBG_E_CANNOT_RESOLVE_ASSEMBLY is returned.</span></span>

## <a name="requirements"></a><span data-ttu-id="f4c65-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="f4c65-110">Requirements</span></span>

<span data-ttu-id="f4c65-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4c65-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="f4c65-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f4c65-112">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="f4c65-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f4c65-113">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="f4c65-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4c65-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
