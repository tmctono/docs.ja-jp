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
ms.openlocfilehash: 25861b2635605042acc1bf81f3f7a4739e678522
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645449"
---
# <a name="icordebugassemblyenumnext-method"></a><span data-ttu-id="7d495-102">ICorDebugAssemblyEnum::Next メソッド</span><span class="sxs-lookup"><span data-stu-id="7d495-102">ICorDebugAssemblyEnum::Next Method</span></span>
<span data-ttu-id="7d495-103">現在のカーソル位置から、コレクションから指定した数のアセンブリを取得します。</span><span class="sxs-lookup"><span data-stu-id="7d495-103">Gets the specified number of assemblies from the collection, starting at the current cursor position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d495-104">構文</span><span class="sxs-lookup"><span data-stu-id="7d495-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugAssembly *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7d495-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7d495-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="7d495-106">[in]取得するアセンブリの数。</span><span class="sxs-lookup"><span data-stu-id="7d495-106">[in] The number of assemblies to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="7d495-107">[out]アセンブリを表す ICorDebugAssembly オブジェクトを指す各ポインターの配列。</span><span class="sxs-lookup"><span data-stu-id="7d495-107">[out] An array of pointers, each of which points to an ICorDebugAssembly object that represents an assembly.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="7d495-108">[out]実際に返されるアセンブリの数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="7d495-108">[out] A pointer to the number of assemblies actually returned.</span></span> <span data-ttu-id="7d495-109">この値は null になる場合`celt`は 1 つです。</span><span class="sxs-lookup"><span data-stu-id="7d495-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d495-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="7d495-110">Requirements</span></span>  
 <span data-ttu-id="7d495-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d495-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d495-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7d495-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7d495-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7d495-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7d495-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d495-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
