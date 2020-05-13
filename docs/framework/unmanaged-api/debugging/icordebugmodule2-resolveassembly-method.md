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
ms.openlocfilehash: e64e39d10d20f63430ffe9d2c4df8643e286a677
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210036"
---
# <a name="icordebugmodule2resolveassembly-method"></a><span data-ttu-id="3b005-102">ICorDebugModule2::ResolveAssembly メソッド</span><span class="sxs-lookup"><span data-stu-id="3b005-102">ICorDebugModule2::ResolveAssembly Method</span></span>

<span data-ttu-id="3b005-103">指定したメタデータトークンによって参照されるアセンブリを解決します。</span><span class="sxs-lookup"><span data-stu-id="3b005-103">Resolves the assembly referenced by the specified metadata token.</span></span>

## <a name="syntax"></a><span data-ttu-id="3b005-104">構文</span><span class="sxs-lookup"><span data-stu-id="3b005-104">Syntax</span></span>

```cpp
HRESULT ResolveAssembly (
    [in]  mdToken             tkAssemblyRef,
    [out] ICorDebugAssembly   **ppAssembly
);
```

## <a name="parameters"></a><span data-ttu-id="3b005-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3b005-105">Parameters</span></span>

`tkAssemblyRef`\
<span data-ttu-id="3b005-106">から`mdToken`アセンブリを参照する値。</span><span class="sxs-lookup"><span data-stu-id="3b005-106">[in] An `mdToken` value that references the assembly.</span></span>

`ppAssembly`\
<span data-ttu-id="3b005-107">入出力アセンブリを表す、オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="3b005-107">[out] A pointer to the address of an ICorDebugAssembly object that represents the assembly.</span></span>

## <a name="remarks"></a><span data-ttu-id="3b005-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="3b005-108">Remarks</span></span>

<span data-ttu-id="3b005-109">が呼び出されたときにアセンブリがまだ読み込まれていない場合は `ResolveAssembly` 、CORDBG_E_CANNOT_RESOLVE_ASSEMBLY の HRESULT 値が返されます。</span><span class="sxs-lookup"><span data-stu-id="3b005-109">If the assembly is not already loaded when `ResolveAssembly` is called, an HRESULT value of CORDBG_E_CANNOT_RESOLVE_ASSEMBLY is returned.</span></span>

## <a name="requirements"></a><span data-ttu-id="3b005-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="3b005-110">Requirements</span></span>

<span data-ttu-id="3b005-111">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b005-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="3b005-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3b005-112">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="3b005-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3b005-113">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="3b005-114">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b005-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
