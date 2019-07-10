---
title: ICorDebugAssemblyEnum::Next メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugAssemblyEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssemblyEnum::Next method
helpviewer_keywords:
- ICorDebugAssemblyEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugAssemblyEnum interface [.NET Framework debugging]
ms.assetid: b3e7d0c2-3baa-4ef8-8e3f-b865cf252940
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 00adc852a0940766cdd4188ffa5d6be2b472e51f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744876"
---
# <a name="icordebugassemblyenumnext-method"></a><span data-ttu-id="df936-102">ICorDebugAssemblyEnum::Next メソッド</span><span class="sxs-lookup"><span data-stu-id="df936-102">ICorDebugAssemblyEnum::Next Method</span></span>
<span data-ttu-id="df936-103">現在のカーソル位置から、コレクションから指定した数のアセンブリを取得します。</span><span class="sxs-lookup"><span data-stu-id="df936-103">Gets the specified number of assemblies from the collection, starting at the current cursor position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df936-104">構文</span><span class="sxs-lookup"><span data-stu-id="df936-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugAssembly *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="df936-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="df936-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="df936-106">[in]取得するアセンブリの数。</span><span class="sxs-lookup"><span data-stu-id="df936-106">[in] The number of assemblies to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="df936-107">[out]アセンブリを表す ICorDebugAssembly オブジェクトを指す各ポインターの配列。</span><span class="sxs-lookup"><span data-stu-id="df936-107">[out] An array of pointers, each of which points to an ICorDebugAssembly object that represents an assembly.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="df936-108">[out]実際に返されるアセンブリの数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="df936-108">[out] A pointer to the number of assemblies actually returned.</span></span> <span data-ttu-id="df936-109">この値は null になる場合`celt`は 1 つです。</span><span class="sxs-lookup"><span data-stu-id="df936-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df936-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="df936-110">Requirements</span></span>  
 <span data-ttu-id="df936-111">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="df936-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df936-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="df936-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="df936-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="df936-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="df936-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df936-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
